# Kiểm soát truy cập C5 & Nhận diện cho các thành phần và người dùng AI

## Mục tiêu Kiểm soát

Kiểm soát truy cập hiệu quả cho các hệ thống AI đòi hỏi quản lý định danh vững chắc, cấp phép dựa trên ngữ cảnh và thực thi trong thời gian chạy theo các nguyên tắc không tin cậy. Các biện pháp kiểm soát này đảm bảo rằng con người, dịch vụ và các tác nhân tự động chỉ tương tác với mô hình, dữ liệu và tài nguyên tính toán trong phạm vi được cấp phép rõ ràng, đồng thời có khả năng xác minh liên tục và kiểm tra.

---

## C5.1 Quản lý Danh tính & Xác thực

Thiết lập danh tính được bảo vệ bằng mật mã cho tất cả các thực thể với xác thực đa yếu tố cho các thao tác đặc quyền.

|   #   | Description                                                                                                                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.1.1 | Xác minh rằng tất cả người dùng là con người và các nguyên tắc dịch vụ đều xác thực thông qua nhà cung cấp danh tính doanh nghiệp tập trung (IdP) sử dụng các giao thức OIDC/SAML với ánh xạ nhận dạng thành token duy nhất (không dùng chung tài khoản hoặc thông tin đăng nhập). |   1   | D/V  |
| 5.1.2 | Xác minh rằng các hoạt động có rủi ro cao (triển khai mô hình, xuất trọng số, truy cập dữ liệu huấn luyện, thay đổi cấu hình sản xuất) yêu cầu xác thực đa yếu tố hoặc xác thực nâng cao kèm theo xác thực lại phiên.                                                              |   1   | D/V  |
| 5.1.3 | Xác minh rằng các cán bộ mới trải qua việc xác minh danh tính phù hợp với tiêu chuẩn NIST 800-63-3 IAL-2 hoặc các tiêu chuẩn tương đương trước khi được cấp quyền truy cập hệ thống sản xuất.                                                                                      |   2   |  D   |
| 5.1.4 | Xác minh rằng các đánh giá truy cập được thực hiện hàng quý với việc phát hiện tự động các tài khoản không hoạt động, thực thi xoay vòng thông tin đăng nhập, và quy trình hủy cấp quyền.                                                                                          |   2   |  V   |
| 5.1.5 | Xác minh rằng các đại lý AI liên kết xác thực thông qua các khẳng định JWT được ký có thời hạn tối đa là 24 giờ và bao gồm bằng chứng mật mã về nguồn gốc.                                                                                                                         |   3   | D/V  |

---

## C5.2 Ủy quyền Tài nguyên & Nguyên tắc Quyền Hạn Tối Thiểu

Triển khai kiểm soát truy cập chi tiết cho tất cả các tài nguyên AI với mô hình cấp phép rõ ràng và dấu vết kiểm toán.

|   #   | Description                                                                                                                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.2.1 | Xác minh rằng mọi tài nguyên AI (bộ dữ liệu, mô hình, điểm cuối, bộ sưu tập vector, chỉ mục nhúng, các phiên bản tính toán) đều thực thi kiểm soát truy cập dựa trên vai trò với danh sách cho phép rõ ràng và chính sách từ chối mặc định.        |   1   | D/V  |
| 5.2.2 | Xác nhận rằng các nguyên tắc quyền tối thiểu được thực thi theo mặc định với các tài khoản dịch vụ, bắt đầu với quyền chỉ đọc và yêu cầu có tài liệu chứng minh lý do kinh doanh cho quyền ghi.                                                    |   1   | D/V  |
| 5.2.3 | Xác minh rằng tất cả các sửa đổi kiểm soát truy cập đều được liên kết với các yêu cầu thay đổi đã được phê duyệt và được ghi lại một cách bất biến với dấu thời gian, danh tính người thực hiện, định danh tài nguyên và sự thay đổi về quyền hạn. |   1   |  V   |
| 5.2.4 | Xác minh rằng các nhãn phân loại dữ liệu (PII, PHI, kiểm soát xuất khẩu, quyền sở hữu) tự động lan truyền đến các tài nguyên được tạo ra (nhúng, bộ nhớ đệm đề xuất, đầu ra mô hình) với việc thực thi chính sách nhất quán.                       |   2   |  D   |
| 5.2.5 | Xác minh rằng các lần cố gắng truy cập trái phép và sự kiện leo thang đặc quyền kích hoạt cảnh báo thời gian thực với siêu dữ liệu ngữ cảnh gửi đến hệ thống SIEM trong vòng 5 phút.                                                               |   2   | D/V  |

---

## C5.3 Đánh giá Chính sách Động

Triển khai các công cụ kiểm soát truy cập dựa trên thuộc tính (ABAC) để đưa ra các quyết định cấp quyền dựa trên ngữ cảnh với khả năng kiểm toán.

|   #   | Description                                                                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.3.1 | Xác minh rằng các quyết định ủy quyền được tách ra ngoài và xử lý bởi một bộ máy chính sách chuyên dụng (OPA, Cedar hoặc tương đương) có thể truy cập qua các API được xác thực với bảo vệ toàn vẹn bằng mật mã.                        |   1   | D/V  |
| 5.3.2 | Xác minh rằng các chính sách đánh giá các thuộc tính động tại thời điểm chạy bao gồm mức độ được phép của người dùng, phân loại độ nhạy cảm của tài nguyên, ngữ cảnh yêu cầu, sự cô lập giữa các khách thuê, và các giới hạn thời gian. |   1   | D/V  |
| 5.3.3 | Xác nhận rằng các định nghĩa chính sách được quản lý phiên bản, đánh giá bởi đồng nghiệp và được xác thực thông qua kiểm thử tự động trong các pipeline CI/CD trước khi triển khai vào môi trường sản xuất.                             |   2   |  D   |
| 5.3.4 | Xác minh rằng kết quả đánh giá chính sách bao gồm các lý do quyết định có cấu trúc và được truyền đến các hệ thống SIEM để phân tích tương quan và báo cáo tuân thủ.                                                                    |   2   |  V   |
| 5.3.5 | Xác minh rằng giá trị thời gian sống trong bộ nhớ đệm chính sách (TTL) không vượt quá 5 phút đối với các tài nguyên nhạy cảm cao và 1 giờ đối với các tài nguyên tiêu chuẩn có khả năng làm mới bộ nhớ đệm.                             |   3   | D/V  |

---

## C5.4 Thực thi bảo mật trong thời gian truy vấn

Triển khai các biện pháp kiểm soát bảo mật cấp cơ sở dữ liệu với bộ lọc bắt buộc và chính sách bảo mật cấp hàng.

|   #   | Description                                                                                                                                                                                                           | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.4.1 | Xác minh rằng tất cả truy vấn cơ sở dữ liệu vector và SQL bao gồm các bộ lọc bảo mật bắt buộc (ID người thuê, nhãn độ nhạy, phạm vi người dùng) được thực thi ở cấp độ động cơ cơ sở dữ liệu, không phải mã ứng dụng. |   1   | D/V  |
| 5.4.2 | Xác minh rằng các chính sách bảo mật cấp hàng (RLS) và che mặt trường dữ liệu được bật với kế thừa chính sách cho tất cả các cơ sở dữ liệu vector, chỉ mục tìm kiếm và bộ dữ liệu đào tạo.                            |   1   | D/V  |
| 5.4.3 | Xác minh rằng việc đánh giá ủy quyền không thành công sẽ ngăn chặn "tấn công đại lý nhầm lẫn" bằng cách ngay lập tức hủy bỏ các truy vấn và trả về mã lỗi ủy quyền rõ ràng thay vì trả về các tập kết quả rỗng.       |   2   |  D   |
| 5.4.4 | Xác minh rằng độ trễ đánh giá chính sách được giám sát liên tục với các cảnh báo tự động cho các điều kiện hết thời gian có thể cho phép vượt qua việc ủy quyền.                                                      |   2   |  V   |
| 5.4.5 | Xác minh rằng cơ chế thử lại truy vấn đánh giá lại các chính sách ủy quyền để tính đến các thay đổi quyền động trong các phiên người dùng đang hoạt động.                                                             |   3   | D/V  |

---

## Lọc đầu ra C5.5 & Ngăn ngừa mất dữ liệu

Triển khai các kiểm soát hậu xử lý để ngăn chặn việc tiết lộ dữ liệu không được phép trong nội dung do AI tạo ra.

|   #   | Description                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.5.1 | Xác minh rằng các cơ chế lọc sau suy luận quét và xóa thông tin nhận dạng cá nhân (PII) không được phép, thông tin phân loại và dữ liệu sở hữu trước khi cung cấp nội dung cho người yêu cầu.            |   1   | D/V  |
| 5.5.2 | Xác minh rằng các trích dẫn, tham chiếu và ghi nguồn trong kết quả mô hình được xác thực dựa trên quyền hạn của người gọi và loại bỏ nếu phát hiện truy cập trái phép.                                   |   1   | D/V  |
| 5.5.3 | Xác minh rằng các hạn chế về định dạng đầu ra (PDF đã được làm sạch, hình ảnh đã loại bỏ siêu dữ liệu, các loại tệp được phê duyệt) được thực thi dựa trên cấp độ quyền người dùng và phân loại dữ liệu. |   2   |  D   |
| 5.5.4 | Xác minh rằng các thuật toán che khuất dữ liệu là xác định trước, được kiểm soát phiên bản và duy trì nhật ký kiểm toán để hỗ trợ các cuộc điều tra tuân thủ và phân tích pháp y.                        |   2   |  V   |
| 5.5.5 | Xác minh rằng các sự kiện che dấu có rủi ro cao tạo ra các bản ghi thích ứng bao gồm các hàm băm mật mã của nội dung gốc để truy xuất pháp y mà không làm lộ dữ liệu.                                    |   3   |  V   |

---

## C5.6 Cách ly đa người thuê (Multi-Tenant Isolation)

Đảm bảo tách biệt mật mã và tách biệt logic giữa các khách thuê trong hạ tầng AI dùng chung.

|   #   | Description                                                                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.6.1 | Xác minh rằng các không gian bộ nhớ, kho nhúng, mục trong bộ đệm và các tệp tạm thời được phân tách theo không gian tên cho từng khách thuê với việc xóa bảo mật khi khách thuê bị xóa hoặc phiên làm việc kết thúc. |   1   | D/V  |
| 5.6.2 | Xác minh rằng mọi yêu cầu API đều bao gồm một định danh người thuê đã được xác thực, được xác thực bằng mã hóa đối chiếu với ngữ cảnh phiên và quyền của người dùng.                                                 |   1   | D/V  |
| 5.6.3 | Xác minh rằng các chính sách mạng thực thi các quy tắc mặc định từ chối đối với giao tiếp chéo giữa các khách thuê trong các service mesh và nền tảng điều phối container.                                           |   2   |  D   |
| 5.6.4 | Xác minh rằng các khóa mã hóa là duy nhất cho từng khách thuê với hỗ trợ khóa do khách hàng quản lý (CMK) và sự cô lập mật mã giữa các kho dữ liệu của khách thuê.                                                   |   3   |  D   |

---

## C5.7 Ủy quyền Đại lý Tự động

Kiểm soát quyền hạn cho các tác nhân AI và hệ thống tự động thông qua token khả năng giới hạn phạm vi và ủy quyền liên tục.

|   #   | Description                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 5.7.1 | Xác minh rằng các tác nhân tự trị nhận được token khả năng có phạm vi, trong đó liệt kê rõ các hành động được phép, tài nguyên có thể truy cập, giới hạn thời gian và các ràng buộc vận hành.                     |   1   | D/V  |
| 5.7.2 | Xác minh rằng các khả năng có rủi ro cao (truy cập hệ thống tệp, thực thi mã, gọi API bên ngoài, giao dịch tài chính) được tắt theo mặc định và yêu cầu các quyền rõ ràng để kích hoạt cùng với lý do kinh doanh. |   1   | D/V  |
| 5.7.3 | Xác minh rằng các token năng lực được liên kết với phiên người dùng, bao gồm bảo vệ tính toàn vẹn mật mã, và đảm bảo rằng chúng không thể được lưu trữ hoặc tái sử dụng trong các trường hợp ngoại tuyến.         |   2   |  D   |
| 5.7.4 | Xác minh rằng các hành động do đại lý khởi xướng phải trải qua xác thực thứ cấp thông qua bộ máy chính sách ABAC với đánh giá ngữ cảnh đầy đủ và ghi nhật ký kiểm toán.                                           |   2   |  V   |
| 5.7.5 | Xác minh rằng các điều kiện lỗi của đại lý và xử lý ngoại lệ bao gồm thông tin phạm vi khả năng để hỗ trợ phân tích sự cố và điều tra pháp y.                                                                     |   3   |  V   |

---

## Tài liệu tham khảo

### Tiêu chuẩn & Khung làm việc

* [NIST SP 800-63-3: Digital Identity Guidelines](https://pages.nist.gov/800-63-3/)
* [Zero Trust Architecture – NIST SP 800-207](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.800-207.pdf)
* [OWASP Application Security Verification Standard (AISVS)](https://owasp.org/www-project-application-security-verification-standard/)
  ​
### Hướng dẫn triển khai

* [Identity and Access Management in the AI Era: 2025 Guide – IDSA](https://www.idsalliance.org/blog/identity-and-access-management-in-the-ai-era-2025-guide/)
* [Attribute-Based Access Control with OPA – Permify](https://medium.com/permify-tech-blog/attribute-based-access-control-abac-implementation-with-open-policy-agent-opa-b47052248f29)
* [How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS](https://aws.amazon.com/blogs/security/how-we-designed-cedar-to-be-intuitive-to-use-fast-and-safe/)
  ​
### Bảo mật chuyên biệt cho AI

* [Row Level Security in Vector DBs for RAG – Bluetuple.ai](https://medium.com/bluetuple-ai/implementing-row-level-security-in-vector-dbs-for-rag-applications-fdbccb63d464)
* [Tenant Isolation in Multi-Tenant Systems – WorkOS](https://workos.com/blog/tenant-isolation-in-multi-tenant-systems)
* [Handling AI Agent Permissions – Stytch](https://stytch.com/blog/handling-ai-agent-permissions/)
* [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)


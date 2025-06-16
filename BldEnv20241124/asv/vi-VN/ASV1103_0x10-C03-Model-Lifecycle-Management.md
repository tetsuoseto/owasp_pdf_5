# Quản lý Vòng đời Mô hình C3 & Kiểm soát Thay đổi

## Mục tiêu Kiểm soát

Các hệ thống AI phải triển khai quy trình kiểm soát thay đổi nhằm ngăn chặn các sửa đổi mô hình không được phép hoặc không an toàn tiếp cận môi trường sản xuất. Quy trình kiểm soát này đảm bảo tính toàn vẹn của mô hình trong suốt vòng đời—từ phát triển đến triển khai và đến khi ngừng hoạt động—giúp phản ứng nhanh chóng với sự cố và duy trì trách nhiệm cho tất cả các thay đổi.

Mục tiêu bảo mật cốt lõi: Chỉ những mô hình được ủy quyền và xác thực mới được đưa vào sản xuất thông qua các quy trình kiểm soát nhằm duy trì tính toàn vẹn, khả năng truy xuất và khả năng phục hồi.

---

## C3.1 Ủy quyền và Tính toàn vẹn của Mô hình

Chỉ các mô hình được ủy quyền với tính toàn vẹn đã được xác minh mới được đưa vào môi trường sản xuất.

|   #   | Description                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.1.1 | Xác minh rằng tất cả các hiện vật mô hình (trọng số, cấu hình, bộ mã hóa từ) đều được ký kỹ thuật số bởi các thực thể được ủy quyền trước khi triển khai.                                         |   1   | D/V  |
| 3.1.2 | Xác minh rằng tính toàn vẹn của mô hình được kiểm tra khi triển khai và các lỗi xác thực chữ ký ngăn chặn việc tải mô hình.                                                                       |   1   | D/V  |
| 3.1.3 | Xác minh rằng hồ sơ nguồn gốc mô hình bao gồm danh tính của thực thể ủy quyền, bảng kiểm đối chiếu dữ liệu đào tạo, kết quả kiểm tra xác nhận với trạng thái đạt/không đạt, và dấu thời gian tạo. |   2   | D/V  |
| 3.1.4 | Xác minh rằng tất cả các mô hình mẫu sử dụng hệ phiên bản ngữ nghĩa (MAJOR.MINOR.PATCH) với các tiêu chí được ghi nhận rõ ràng xác định khi nào mỗi thành phần phiên bản sẽ tăng lên.             |   2   | D/V  |
| 3.1.5 | Xác minh rằng theo dõi phụ thuộc duy trì một kho hàng thời gian thực cho phép xác định nhanh tất cả các hệ thống tiêu thụ.                                                                        |   2   |  V   |

---

## C3.2 Xác thực và Kiểm thử Mô hình

Mô hình phải vượt qua các kiểm tra về bảo mật và an toàn đã được xác định trước khi triển khai.

|   #   | Description                                                                                                                                                                                                | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.2.1 | Xác nhận rằng các mô hình được kiểm tra an ninh tự động bao gồm kiểm tra hợp lệ đầu vào, làm sạch đầu ra và đánh giá an toàn với các ngưỡng đạt/không đạt đã được tổ chức thỏa thuận trước khi triển khai. |   1   | D/V  |
| 3.2.2 | Xác minh rằng các lỗi xác thực tự động chặn việc triển khai mô hình ngay cả sau khi có sự phê duyệt ghi đè rõ ràng từ nhân sự được ủy quyền trước, kèm theo các lý do kinh doanh đã được ghi chép.         |   1   | D/V  |
| 3.2.3 | Xác minh rằng kết quả kiểm tra được ký số bằng mật mã và liên kết bất biến với băm phiên bản mô hình cụ thể đang được xác thực.                                                                            |   2   |  V   |
| 3.2.4 | Xác minh rằng việc triển khai khẩn cấp yêu cầu phải có đánh giá rủi ro bảo mật được ghi chép và phê duyệt từ cơ quan an ninh được chỉ định trước trong khung thời gian đã thỏa thuận trước.                |   2   | D/V  |

---

## C3.3 Triển khai có kiểm soát & Quay lại phiên bản trước

Việc triển khai mô hình phải được kiểm soát, giám sát và có thể hoàn tác.

|   #   | Description                                                                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 3.3.1 | Xác nhận rằng các triển khai sản xuất thực hiện các cơ chế triển khai dần (triển khai canary, triển khai xanh-lam) với các kích hoạt hoàn tác tự động dựa trên các tỷ lệ lỗi, ngưỡng độ trễ, hoặc tiêu chí cảnh báo bảo mật đã thỏa thuận trước. |   1   |  D   |
| 3.3.2 | Xác minh rằng khả năng khôi phục lại trạng thái mô hình hoàn chỉnh (trọng số, cấu hình, phụ thuộc) được thực hiện nguyên tử trong các cửa sổ thời gian tổ chức được xác định trước.                                                              |   1   | D/V  |
| 3.3.3 | Xác minh rằng các quy trình triển khai xác thực chữ ký mật mã và tính toán kiểm tra tổng kiểm tra toàn vẹn trước khi kích hoạt mô hình, và ngừng triển khai nếu phát hiện bất kỳ sự không khớp nào.                                              |   2   | D/V  |
| 3.3.4 | Xác minh rằng các chức năng tắt mô hình khẩn cấp có thể vô hiệu hóa các điểm cuối mô hình trong khoảng thời gian phản hồi đã được xác định trước thông qua các bộ ngắt mạch tự động hoặc công tắc tắt thủ công.                                  |   2   | D/V  |
| 3.3.5 | Xác minh rằng các bản ghi phục hồi (phiên bản mô hình trước, cấu hình, phụ thuộc) được giữ lại theo chính sách tổ chức với bộ lưu trữ không thể thay đổi để phản ứng sự cố.                                                                      |   2   |  V   |

---

## C3.4 Thay đổi Trách nhiệm và Kiểm toán

Tất cả các thay đổi trong vòng đời mô hình phải có khả năng truy vết và kiểm toán.

|   #   | Description                                                                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.4.1 | Xác minh rằng tất cả các thay đổi mô hình (triển khai, cấu hình, ngừng sử dụng) đều tạo ra các bản ghi kiểm tra không thể thay đổi bao gồm dấu thời gian, danh tính tác nhân được xác thực, loại thay đổi và trạng thái trước/sau. |   1   |  V   |
| 3.4.2 | Xác minh rằng việc truy cập nhật ký kiểm toán yêu cầu có sự ủy quyền thích hợp và tất cả các lần cố gắng truy cập đều được ghi lại với danh tính người dùng và dấu thời gian.                                                      |   2   | D/V  |
| 3.4.3 | Xác minh rằng các mẫu prompt và tin nhắn hệ thống được quản lý phiên bản trong các kho git với việc xem xét mã bắt buộc và phê duyệt từ các người đánh giá được chỉ định trước khi triển khai.                                     |   2   | D/V  |
| 3.4.4 | Xác minh rằng các bản ghi kiểm toán bao gồm đủ chi tiết (băm mô hình, ảnh chụp cấu hình, phiên bản phụ thuộc) để cho phép tái tạo hoàn chỉnh trạng thái mô hình cho bất kỳ mốc thời gian nào trong khoảng thời gian lưu giữ.       |   2   |  V   |

---

## C3.5 Thực hành phát triển an toàn

Quy trình phát triển và đào tạo mô hình phải tuân theo các thực hành an toàn để ngăn chặn việc bị xâm phạm.

|   #   | Description                                                                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.5.1 | Xác minh rằng các môi trường phát triển mô hình, thử nghiệm và sản xuất được tách biệt vật lý hoặc logic. Chúng không sử dụng hạ tầng chung, có kiểm soát truy cập riêng biệt và lưu trữ dữ liệu cô lập.                                  |   1   |  D   |
| 3.5.2 | Xác minh rằng việc đào tạo và tinh chỉnh mô hình diễn ra trong các môi trường tách biệt với quyền truy cập mạng được kiểm soát.                                                                                                           |   1   |  D   |
| 3.5.3 | Xác minh rằng nguồn dữ liệu huấn luyện đã được kiểm tra tính toàn vẹn và xác thực thông qua các nguồn đáng tin cậy với chuỗi lưu giữ tài liệu trước khi sử dụng trong phát triển mô hình.                                                 |   1   | D/V  |
| 3.5.4 | Xác minh rằng các sản phẩm phát triển mô hình (siêu tham số, kịch bản huấn luyện, tập tin cấu hình) được lưu trữ trong hệ thống quản lý phiên bản và yêu cầu phê duyệt đánh giá đồng nghiệp trước khi sử dụng trong quá trình huấn luyện. |   2   |  D   |

---

## C3.6 Ngừng sử dụng và loại bỏ mô hình

Các mô hình phải được gỡ bỏ một cách an toàn khi không còn cần thiết hoặc khi các vấn đề về bảo mật được phát hiện.

|   #   | Description                                                                                                                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 3.6.1 | Xác nhận rằng quy trình nghỉ hưu mô hình tự động quét đồ thị phụ thuộc, xác định tất cả các hệ thống tiêu thụ, và cung cấp thời gian thông báo trước đã được thỏa thuận trước khi ngừng hoạt động.                                             |   1   |  D   |
| 3.6.2 | Xác minh rằng các hiện vật mô hình đã nghỉ hưu được xóa sạch một cách an toàn bằng cách sử dụng xóa mật mã hoặc ghi đè đa lần theo chính sách giữ dữ liệu được tài liệu hóa kèm theo các chứng nhận hủy tài liệu đã được xác minh.             |   1   | D/V  |
| 3.6.3 | Xác minh rằng các sự kiện nghỉ hưu mô hình được ghi lại với dấu thời gian và danh tính người thực hiện, và chữ ký mô hình bị thu hồi để ngăn chặn việc sử dụng lại.                                                                            |   2   |  V   |
| 3.6.4 | Xác minh rằng việc nghỉ hưu mô hình khẩn cấp có thể vô hiệu hóa quyền truy cập mô hình trong phạm vi thời gian phản ứng khẩn cấp đã được thiết lập trước thông qua các công tắc tắt tự động nếu phát hiện ra các lỗ hổng bảo mật nghiêm trọng. |   2   | D/V  |

---

## Tài liệu tham khảo

* [MLOps Principles](https://ml-ops.org/content/mlops-principles)
* [Securing AI/ML Ops – Cisco.com](https://sec.cloudapps.cisco.com/security/center/resources/SecuringAIMLOps)
* [Audit logs security: cryptographically signed tamper-proof logs](https://www.cossacklabs.com/blog/audit-logs-security/)
* [Machine Learning Model Versioning: Top Tools & Best Practices](https://lakefs.io/blog/model-versioning/)
* [AI Hygiene Starts with Models and Data Loaders – SEI Blog](https://insights.sei.cmu.edu/documents/6190/AI-Hygiene-Starts-with-Models-and-Data-Loaders_1G0KTRh.pdf)
* [How to handle versioning and rollback of a deployed ML model?](https://learn.microsoft.com/en-au/answers/questions/1845378/how-to-handle-versioning-and-rollback-of-a-deploye)
* [Reinforcement fine-tuning – OpenAI API](https://platform.openai.com/docs/guides/reinforcement-fine-tuning)
* [Auditing Machine Learning models: Governance, Data Security and …](https://www.linkedin.com/pulse/auditing-machine-learning-models-governance-data-security-negrete-yn81f)
* [Adversarial Training to Improve Model Robustness](https://medium.com/%40amit25173/adversarial-training-to-improve-model-robustness-5e285b516713)
* [What is AI adversarial robustness? – IBM Research](https://research.ibm.com/blog/securing-ai-workflows-with-adversarial-robustness)
* [Exploring Data Provenance: Ensuring Data Integrity and Authenticity](https://www.astera.com/type/blog/data-provenance/)
* [MITRE ATLAS](https://atlas.mitre.org/)
* [AWS Prescriptive Guidance – Best practices for retiring applications …](https://docs.aws.amazon.com/pdfs/prescriptive-guidance/latest/migration-app-retirement-best-practices/migration-app-retirement-best-practices.pdf)


# 9 Tự động điều phối & An ninh hành động tác nhân

## Mục Tiêu Kiểm Soát

Đảm bảo rằng các hệ thống AI tự động hoặc đa tác nhân chỉ có thể thực hiện các hành động được dự định rõ ràng, xác thực, có thể kiểm tra và nằm trong giới hạn chi phí và ngưỡng rủi ro đã định. Điều này giúp bảo vệ chống lại các mối đe dọa như Xâm phạm Hệ thống Tự động, Lạm dụng Công cụ, Phát hiện Vòng lặp Tác nhân, Chiếm đoạt Giao tiếp, Giả mạo Danh tính, Điều khiển Đàn và Thao túng Ý định.

---

## 9.1 Ngân sách Lập kế hoạch Nhiệm vụ Tác nhân & Đệ quy

Giới hạn các kế hoạch đệ quy và buộc các điểm kiểm tra do con người thực hiện đối với các hành động có đặc quyền.

|   #   | Description                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.1.1 | Xác minh rằng độ sâu đệ quy tối đa, độ rộng, thời gian thực tế, số lượng token và chi phí tiền tệ cho mỗi lần thực thi đại lý đều được cấu hình tập trung và kiểm soát phiên bản.                         |   1   | D/V  |
| 9.1.2 | Xác minh rằng các hành động đặc quyền hoặc không thể thu hồi (ví dụ: cam kết mã, chuyển tiền tài chính) yêu cầu sự phê duyệt rõ ràng của con người qua một kênh có thể kiểm tra được trước khi thực hiện. |   1   | D/V  |
| 9.1.3 | Xác minh rằng các bộ giám sát tài nguyên thời gian thực kích hoạt ngắt mạch đảo khi bất kỳ ngưỡng ngân sách nào bị vượt quá, ngăn chặn việc mở rộng tác vụ tiếp theo.                                     |   2   |  D   |
| 9.1.4 | Xác minh rằng các sự kiện ngắt mạch được ghi lại với ID đại lý, điều kiện kích hoạt, và trạng thái kế hoạch được ghi nhận để xem xét pháp y.                                                              |   2   | D/V  |
| 9.1.5 | Xác minh rằng các bài kiểm tra bảo mật bao phủ các kịch bản cạn kiệt ngân sách và kế hoạch chạy vượt giới hạn, xác nhận việc dừng an toàn mà không mất dữ liệu.                                           |   3   |  V   |
| 9.1.6 | Xác minh rằng các chính sách ngân sách được thể hiện dưới dạng chính sách dưới dạng mã (policy-as-code) và được thực thi trong CI/CD để ngăn chặn sự lệch cấu hình.                                       |   3   |  D   |

---

## 9.2 Cách ly Plugin Công cụ

Cô lập các tương tác công cụ để ngăn chặn truy cập hệ thống hoặc thực thi mã trái phép.

|   #   | Description                                                                                                                                                                          | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 9.2.1 | Xác minh rằng mọi công cụ/plugin đều thực thi bên trong hệ điều hành, container hoặc sandbox cấp độ WASM với các chính sách ít đặc quyền nhất về hệ thống tệp, mạng và gọi hệ thống. |   1   | D/V  |
| 9.2.2 | Xác nhận rằng các hạn mức tài nguyên sandbox (CPU, bộ nhớ, đĩa, băng thông mạng ra ngoài) và thời gian chờ thực thi được thực thi và ghi lại.                                        |   1   | D/V  |
| 9.2.3 | Xác minh rằng các nhị phân hoặc mô tả công cụ được ký số; các chữ ký được xác thực trước khi tải.                                                                                    |   2   | D/V  |
| 9.2.4 | Xác minh rằng dữ liệu telemetry từ sandbox được truyền đến hệ thống SIEM; các bất thường (ví dụ, các kết nối outbound cố gắng thực hiện) sẽ kích hoạt cảnh báo.                      |   2   |  V   |
| 9.2.5 | Xác minh rằng các plugin có nguy cơ cao được kiểm tra bảo mật và thử nghiệm xâm nhập trước khi triển khai vào môi trường sản xuất.                                                   |   3   |  V   |
| 9.2.6 | Xác minh rằng các cố gắng thoát khỏi vùng an toàn (sandbox) được tự động chặn và plugin vi phạm bị cách ly để chờ điều tra.                                                          |   3   | D/V  |

---

## 9.3 Vòng Lặp Tự Động & Giới Hạn Chi Phí

Phát hiện và ngăn chặn đệ quy không kiểm soát giữa các tác nhân và sự bùng nổ chi phí.

|   #   | Description                                                                                                                                 | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.3.1 | Xác minh rằng các cuộc gọi giữa các tác nhân bao gồm một giới hạn số bước nhảy hoặc TTL mà môi trường thực thi sẽ giảm giá trị và thực thi. |   1   | D/V  |
| 9.3.2 | Xác minh rằng các tác nhân duy trì một ID đồ thị gọi duy nhất để phát hiện tự gọi hoặc các mô hình chu kỳ.                                  |   2   |  D   |
| 9.3.3 | Xác minh rằng bộ đếm tổng hợp đơn vị tính toán và chi tiêu được theo dõi theo chuỗi yêu cầu; việc vượt quá giới hạn sẽ hủy bỏ chuỗi.        |   2   | D/V  |
| 9.3.4 | Xác minh rằng phân tích hình thức hoặc kiểm tra mô hình chứng minh không có sự đệ quy không giới hạn trong các giao thức tác nhân.          |   3   |  V   |
| 9.3.5 | Xác minh rằng các sự kiện hủy vòng lặp tạo ra cảnh báo và cung cấp các chỉ số cải tiến liên tục.                                            |   3   |  D   |

---

## 9.4 Bảo vệ chống lạm dụng trên cấp độ giao thức

Kênh giao tiếp an toàn giữa các tác nhân và hệ thống bên ngoài để ngăn chặn việc chiếm đoạt hoặc thao túng.

|   #   | Description                                                                                                                                                          | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.4.1 | Xác minh rằng tất cả các tin nhắn giữa tác nhân và công cụ cũng như giữa các tác nhân với nhau đều được xác thực (ví dụ: TLS hai chiều hoặc JWT) và mã hóa đầu cuối. |   1   | D/V  |
| 9.4.2 | Xác minh rằng các lược đồ được xác thực một cách nghiêm ngặt; các trường không xác định hoặc thông điệp bị sai định dạng sẽ bị từ chối.                              |   1   |  D   |
| 9.4.3 | Xác minh rằng các kiểm tra toàn vẹn (MAC hoặc chữ ký số) bao phủ toàn bộ phần trọng tải tin nhắn bao gồm cả các tham số công cụ.                                     |   2   | D/V  |
| 9.4.4 | Xác minh rằng tính năng chống phát lại (nonces hoặc cửa sổ dấu thời gian) được thực thi ở lớp giao thức.                                                             |   2   |  D   |
| 9.4.5 | Xác minh rằng các triển khai giao thức được tiến hành fuzzing và phân tích tĩnh để phát hiện lỗi tiêm nhiễm hoặc phân giải.                                          |   3   |  V   |

---

## 9.5 Định danh tác nhân & Bằng chứng chống giả mạo

Đảm bảo các hành động có thể truy nguyên và các sửa đổi có thể phát hiện được.

|   #   | Description                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.5.1 | Xác minh rằng mỗi thực thể tác nhân sở hữu một định danh mật mã duy nhất (cặp khóa hoặc chứng chỉ gốc phần cứng).                       |   1   | D/V  |
| 9.5.2 | Xác minh rằng tất cả các hành động của tác nhân đều được ký và đóng dấu thời gian; nhật ký bao gồm chữ ký để đảm bảo không thể chối bỏ. |   2   | D/V  |
| 9.5.3 | Xác minh rằng các bản ghi chống giả mạo được lưu trữ trong một phương tiện chỉ cho phép ghi thêm hoặc chỉ ghi một lần.                  |   2   |  V   |
| 9.5.4 | Xác minh rằng các khóa định danh được thay đổi theo lịch trình đã định và khi có dấu hiệu bị xâm phạm.                                  |   3   |  D   |
| 9.5.5 | Xác minh rằng các cố gắng giả mạo hoặc xung đột khóa kích hoạt cách ly ngay lập tức đối với tác nhân bị ảnh hưởng.                      |   3   | D/V  |

---

## 9.6 Giảm Rủi Ro Đàn Đa Tác Nhân

Giảm thiểu các nguy cơ từ hành vi tập thể thông qua cách ly và mô hình hóa an toàn chính thức.

|   #   | Description                                                                                                                                                    | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.6.1 | Xác minh rằng các tác nhân hoạt động trong các miền bảo mật khác nhau được thực thi trong các môi trường chạy biệt lập hoặc các phân đoạn mạng riêng biệt.     |   1   | D/V  |
| 9.6.2 | Xác minh rằng các hành vi bầy đàn được mô hình hóa và kiểm tra chính thức về tính sống động và an toàn trước khi triển khai.                                   |   3   |  V   |
| 9.6.3 | Xác minh rằng các bộ giám sát thời gian chạy phát hiện các mẫu nguy hiểm mới xuất hiện (ví dụ, dao động, tình trạng treo) và khởi động các hành động sửa chữa. |   3   |  D   |

---

## 9.7 Xác thực / Ủy quyền Người dùng và Công cụ

Thực hiện kiểm soát truy cập chặt chẽ cho mọi hành động được kích hoạt bởi tác nhân.

|   #   | Description                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.7.1 | Xác minh rằng các tác nhân xác thực như các chính thể hạng nhất đối với các hệ thống hạ nguồn, không bao giờ tái sử dụng thông tin xác thực của người dùng cuối. |   1   | D/V  |
| 9.7.2 | Xác minh rằng các chính sách ủy quyền chi tiết hạn chế công cụ mà đại lý có thể gọi và các tham số mà nó có thể cung cấp.                                        |   2   |  D   |
| 9.7.3 | Xác minh rằng các kiểm tra đặc quyền được đánh giá lại ở mỗi lần gọi (ủy quyền liên tục), không chỉ khi bắt đầu phiên làm việc.                                  |   2   |  V   |
| 9.7.4 | Xác minh rằng các đặc quyền được ủy quyền tự động hết hạn và yêu cầu đồng ý lại sau khi hết thời gian hoặc thay đổi phạm vi.                                     |   3   |  D   |

---

## 9.8 Bảo mật Giao tiếp giữa các Đại lý

Mã hóa và bảo vệ toàn vẹn tất cả các tin nhắn giữa các tác nhân để ngăn chặn việc nghe trộm và giả mạo.

|   #   | Description                                                                                                                                          | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.8.1 | Xác nhận rằng xác thực lẫn nhau và mã hóa bí mật chuyển tiếp hoàn hảo (ví dụ: TLS 1.3) là bắt buộc đối với các kênh đại lý.                          |   1   | D/V  |
| 9.8.2 | Xác minh rằng tính toàn vẹn và nguồn gốc của tin nhắn được xác thực trước khi xử lý; nếu không thành công sẽ phát cảnh báo và loại bỏ tin nhắn.      |   1   |  D   |
| 9.8.3 | Xác minh rằng siêu dữ liệu truyền thông (dấu thời gian, số thứ tự) được ghi lại để hỗ trợ tái tạo pháp y.                                            |   2   | D/V  |
| 9.8.4 | Xác minh rằng xác minh hình thức hoặc kiểm tra mô hình xác nhận rằng các máy trạng thái giao thức không thể bị đưa vào các trạng thái không an toàn. |   3   |  V   |

---

## 9.9 Xác minh Ý định và Thực thi Ràng buộc

Xác nhận rằng các hành động của đại lý phù hợp với ý định đã nêu của người dùng và các giới hạn của hệ thống.

|   #   | Description                                                                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.9.1 | Xác minh rằng bộ giải ràng buộc trước khi thực thi kiểm tra các hành động đề xuất dựa trên các quy tắc an toàn và chính sách được mã hóa cứng.                                                                    |   1   |  D   |
| 9.9.2 | Xác minh rằng các hành động có tác động lớn (tài chính, phá hoại, nhạy cảm về quyền riêng tư) yêu cầu xác nhận ý định rõ ràng từ người dùng khởi tạo.                                                             |   2   | D/V  |
| 9.9.3 | Xác minh rằng kiểm tra hậu điều kiện xác nhận các hành động hoàn thành đã đạt được hiệu quả dự kiến mà không có tác dụng phụ; bất kỳ sai lệch nào sẽ kích hoạt việc hoàn tác.                                     |   2   |  V   |
| 9.9.4 | Xác minh rằng các phương pháp hình thức (ví dụ: kiểm tra mô hình, chứng minh định lý) hoặc các bài kiểm tra dựa trên thuộc tính chứng minh rằng các kế hoạch của đại lý đáp ứng tất cả các ràng buộc đã khai báo. |   3   |  V   |
| 9.9.5 | Xác minh rằng các sự cố không khớp ý định hoặc vi phạm ràng buộc được đưa vào các chu trình cải tiến liên tục và chia sẻ thông tin tình báo về mối đe dọa.                                                        |   3   |  D   |

---

## 9.10 Chiến lược Lập luận của Tác nhân về An ninh

Lựa chọn và thực thi an toàn các chiến lược suy luận khác nhau bao gồm các phương pháp ReAct, Chain-of-Thought và Tree-of-Thoughts.

|   #    | Description                                                                                                                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.10.1 | Xác minh rằng việc lựa chọn chiến lược suy luận sử dụng các tiêu chí xác định (độ phức tạp đầu vào, loại nhiệm vụ, bối cảnh bảo mật) và các đầu vào giống hệt nhau tạo ra các lựa chọn chiến lược giống nhau trong cùng một bối cảnh bảo mật.                   |   1   | D/V  |
| 9.10.2 | Xác minh rằng mỗi chiến lược luận lý (ReAct, Chain-of-Thought, Tree-of-Thoughts) có xác thực đầu vào riêng biệt, làm sạch đầu ra, và giới hạn thời gian thực thi cụ thể cho phương pháp nhận thức của nó.                                                       |   1   | D/V  |
| 9.10.3 | Xác minh rằng các chuyển đổi chiến lược lập luận được ghi lại với bối cảnh đầy đủ bao gồm đặc điểm đầu vào, giá trị tiêu chí lựa chọn và siêu dữ liệu thực thi để tái tạo dấu vết kiểm toán.                                                                    |   2   | D/V  |
| 9.10.4 | Xác nhận rằng phương pháp suy luận Tree-of-Thoughts bao gồm các cơ chế cắt nhánh nhằm chấm dứt việc khám phá khi phát hiện vi phạm chính sách, giới hạn tài nguyên hoặc ranh giới an toàn.                                                                      |   2   | D/V  |
| 9.10.5 | Xác nhận rằng các chu kỳ ReAct (Lý luận-Hành động-Quan sát) bao gồm các điểm kiểm tra xác thực tại mỗi giai đoạn: xác minh bước lý luận, ủy quyền hành động và làm sạch quan sát trước khi tiếp tục.                                                            |   2   | D/V  |
| 9.10.6 | Xác minh rằng các chỉ số hiệu suất của chiến lược suy luận (thời gian thực thi, sử dụng tài nguyên, chất lượng đầu ra) được giám sát với cảnh báo tự động khi các chỉ số vượt quá ngưỡng đã cấu hình.                                                           |   3   | D/V  |
| 9.10.7 | Xác minh rằng các phương pháp suy luận lai kết hợp nhiều chiến lược duy trì việc xác thực đầu vào và các ràng buộc đầu ra của tất cả các chiến lược thành phần mà không bỏ qua bất kỳ biện pháp kiểm soát bảo mật nào.                                          |   3   | D/V  |
| 9.10.8 | Xác minh rằng việc kiểm thử bảo mật chiến lược suy luận bao gồm việc thử nghiệm fuzzing với các đầu vào bị làm sai định dạng, các lời nhắc đối kháng được thiết kế để buộc chuyển đổi chiến lược, và kiểm thử điều kiện giới hạn cho mỗi phương pháp nhận thức. |   3   | D/V  |

---

## 9.11 Quản lý trạng thái vòng đời tác nhân & Bảo mật

Khởi tạo đại lý bảo mật, chuyển đổi trạng thái và kết thúc với đường mòn kiểm toán mật mã và các quy trình phục hồi đã được định nghĩa.

|   #    | Description                                                                                                                                                                                                                                                                  | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.11.1 | Xác minh rằng việc khởi tạo tác nhân bao gồm thiết lập danh tính mật mã với chứng chỉ được hỗ trợ phần cứng và các nhật ký kiểm toán khởi động không thể thay đổi chứa ID tác nhân, dấu thời gian, băm cấu hình và các tham số khởi tạo.                                     |   1   | D/V  |
| 9.11.2 | Xác minh rằng các chuyển đổi trạng thái của đại lý được ký điện tử bằng mật mã, đóng dấu thời gian và ghi lại với ngữ cảnh đầy đủ bao gồm các sự kiện kích hoạt, băm trạng thái trước đó, băm trạng thái mới và các kiểm tra bảo mật đã thực hiện.                           |   2   | D/V  |
| 9.11.3 | Xác minh rằng các quy trình tắt agent bao gồm việc xóa bộ nhớ an toàn bằng cách xóa mật mã hoặc ghi đè nhiều lần, thu hồi chứng chỉ cùng thông báo với cơ quan cấp chứng chỉ, và tạo ra các chứng chỉ chấm dứt có khả năng phát hiện việc can thiệp.                         |   2   | D/V  |
| 9.11.4 | Xác minh rằng các cơ chế phục hồi tác nhân xác thực tính toàn vẹn của trạng thái bằng cách sử dụng các tổng kiểm tra mật mã (tối thiểu SHA-256) và hoàn nguyên về trạng thái đã biết là tốt khi phát hiện sự cố hỏng với các cảnh báo tự động và yêu cầu phê duyệt thủ công. |   3   | D/V  |
| 9.11.5 | Xác minh rằng các cơ chế duy trì trạng thái của tác nhân mã hóa dữ liệu trạng thái nhạy cảm bằng khóa AES-256 riêng cho từng tác nhân và thực hiện xoay khóa an toàn theo lịch cấu hình được (tối đa 90 ngày) với việc triển khai không gián đoạn.                           |   3   | D/V  |

---

## 9.12 Khung Bảo Mật Tích Hợp Công Cụ

Các biện pháp kiểm soát bảo mật cho việc tải công cụ động, thực thi và xác thực kết quả với các quy trình đánh giá rủi ro và phê duyệt đã được định nghĩa.

|   #    | Description                                                                                                                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 9.12.1 | Xác minh rằng mô tả công cụ bao gồm siêu dữ liệu bảo mật chỉ định các quyền cần thiết (đọc/ghi/thực thi), mức độ rủi ro (thấp/trung bình/cao), giới hạn tài nguyên (CPU, bộ nhớ, mạng) và các yêu cầu xác thực được ghi trong bản khai công cụ.            |   1   | D/V  |
| 9.12.2 | Xác minh rằng kết quả thực thi công cụ được xác thực dựa trên các sơ đồ mong đợi (JSON Schema, XML Schema) và chính sách bảo mật (lọc sạch đầu ra, phân loại dữ liệu) trước khi tích hợp với giới hạn thời gian chờ và các quy trình xử lý lỗi.            |   1   | D/V  |
| 9.12.3 | Xác minh rằng các nhật ký tương tác công cụ bao gồm ngữ cảnh bảo mật chi tiết bao gồm việc sử dụng đặc quyền, mẫu truy cập dữ liệu, thời gian thực thi, mức tiêu thụ tài nguyên và mã trả về với việc ghi nhật ký có cấu trúc để tích hợp SIEM.            |   2   | D/V  |
| 9.12.4 | Xác minh rằng các cơ chế tải công cụ động kiểm tra chữ ký số sử dụng hạ tầng PKI và thực hiện các giao thức tải an toàn với cách ly sandbox và xác minh quyền trước khi thực thi.                                                                          |   2   | D/V  |
| 9.12.5 | Xác minh rằng các đánh giá bảo mật công cụ được kích hoạt tự động cho các phiên bản mới với các cổng phê duyệt bắt buộc bao gồm phân tích tĩnh, kiểm tra động và xem xét của nhóm bảo mật với các tiêu chí phê duyệt được tài liệu hóa và các yêu cầu SLA. |   3   | D/V  |

---

### Tài liệu tham khảo

* [MITRE ATLAS tactics ML09](https://atlas.mitre.org/)
* [Circuit-breaker research for AI agents — Zou et al., 2024](https://arxiv.org/abs/2406.04313)
* [Trend Micro analysis of sandbox escapes in AI agents — Park, 2025](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/unveiling-ai-agent-vulnerabilities-code-execution)
* [Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025](https://auth0.com/blog/secure-human-in-the-loop-interactions-for-ai-agents/)
* [Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025](https://medium.com/%40foraisec/security-analysis-potential-ai-agent-hijacking-via-mcp-and-a2a-protocol-insights-cd1ec5e6045f)
* [Rapid7 fundamentals on spoofing attack prevention — 2024](https://www.rapid7.com/fundamentals/spoofing-attacks/)
* [Imperial College verification of swarm systems — Lomuscio et al.](https://sail.doc.ic.ac.uk/projects/swarms/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [WIRED security briefing on encryption best practices, 2024](https://www.wired.com/story/encryption-apps-chinese-telecom-hacking-hydra-russia-exxon)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS](https://arxiv.org/html/2506.01245v1)
* [How Is LLM Reasoning Distracted by Irrelevant Context?
  An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
* [Large Language Model Sentinel: LLM Agent for Adversarial Purification](https://arxiv.org/pdf/2405.20770)
* [Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents](https://arxiv.org/html/2504.19956v2)


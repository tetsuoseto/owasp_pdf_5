# C12 Giám sát, Ghi nhật ký & Phát hiện Dị thường

## Mục tiêu kiểm soát

Phần này cung cấp các yêu cầu để cung cấp khả năng quan sát theo thời gian thực và phân tích pháp y về những gì mô hình và các thành phần AI khác nhìn thấy, thực hiện và trả về, nhằm phát hiện, phân loại và rút ra bài học từ các mối đe dọa.

## C12.1 Ghi nhật ký Yêu cầu & Phản hồi

|   #    | Description                                                                                                                                                                                                                                           | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.1.1 | Xác nhận rằng tất cả các lời nhắc của người dùng và phản hồi của mô hình được ghi lại cùng với siêu dữ liệu thích hợp (ví dụ: dấu thời gian, ID người dùng, ID phiên, phiên bản mô hình).                                                             |   1   | D/V  |
| 12.1.2 | Xác minh rằng các bản ghi được lưu trữ trong các kho lưu trữ an toàn, có kiểm soát quyền truy cập với các chính sách lưu giữ phù hợp và quy trình sao lưu đúng đắn.                                                                                   |   1   | D/V  |
| 12.1.3 | Xác minh rằng các hệ thống lưu trữ nhật ký thực hiện mã hóa dữ liệu khi lưu trữ và trong quá trình truyền để bảo vệ thông tin nhạy cảm có trong nhật ký.                                                                                              |   1   | D/V  |
| 12.1.4 | Xác minh rằng dữ liệu nhạy cảm trong các lệnh nhắc và kết quả đầu ra được tự động che mờ hoặc mã hóa trước khi ghi nhật ký, với các quy tắc làm mờ có thể cấu hình cho thông tin nhận dạng cá nhân (PII), thông tin đăng nhập và thông tin độc quyền. |   1   | D/V  |
| 12.1.5 | Xác minh rằng các quyết định chính sách và hành động lọc an toàn được ghi lại với chi tiết đầy đủ nhằm cho phép kiểm tra và gỡ lỗi hệ thống kiểm duyệt nội dung.                                                                                      |   2   | D/V  |
| 12.1.6 | Xác minh rằng tính toàn vẹn của nhật ký được bảo vệ thông qua ví dụ như chữ ký mã hóa hoặc lưu trữ chỉ ghi.                                                                                                                                           |   2   | D/V  |

---

## C12.2 Phát hiện và Cảnh báo Lạm dụng

|   #    | Description                                                                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.2.1 | Xác minh rằng hệ thống phát hiện và cảnh báo các mẫu jailbreak đã biết, các cố gắng tiêm nhiễm prompt và các đầu vào đối kháng bằng cách sử dụng phương pháp phát hiện dựa trên chữ ký.                 |   1   | D/V  |
| 12.2.2 | Xác minh rằng hệ thống tích hợp với các nền tảng Quản lý Thông tin và Sự kiện Bảo mật (SIEM) hiện có bằng cách sử dụng các định dạng và giao thức nhật ký tiêu chuẩn.                                   |   1   | D/V  |
| 12.2.3 | Xác minh rằng các sự kiện bảo mật được tăng cường bao gồm bối cảnh đặc thù AI như các định danh mô hình, điểm độ tin cậy và quyết định bộ lọc an toàn.                                                  |   2   | D/V  |
| 12.2.4 | Xác minh rằng phát hiện bất thường hành vi nhận dạng các mẫu hội thoại bất thường, số lần thử lại quá mức hoặc các hành vi dò xét có hệ thống.                                                          |   2   | D/V  |
| 12.2.5 | Xác nhận rằng các cơ chế cảnh báo thời gian thực thông báo cho các nhóm an ninh khi phát hiện các vi phạm chính sách tiềm năng hoặc các nỗ lực tấn công.                                                |   2   | D/V  |
| 12.2.6 | Xác minh rằng các quy tắc tùy chỉnh được bao gồm để phát hiện các mẫu mối đe dọa đặc thù của AI bao gồm các nỗ lực phá rào phối hợp, chiến dịch tiêm nhắc lệnh và các cuộc tấn công trích xuất mô hình. |   2   | D/V  |
| 12.2.7 | Xác minh rằng các quy trình phản ứng sự cố tự động có thể cô lập các mô hình bị xâm phạm, chặn người dùng độc hại và nâng cao các sự kiện bảo mật quan trọng.                                           |   3   | D/V  |

---

## C12.3 Phát Hiện Sự Trôi Dạt Mô Hình

|   #    | Description                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.3.1 | Xác nhận rằng hệ thống theo dõi các chỉ số hiệu suất cơ bản như độ chính xác, điểm tin cậy, độ trễ và tỷ lệ lỗi qua các phiên bản mô hình và khoảng thời gian.                                |   1   | D/V  |
| 12.3.2 | Xác minh rằng hệ thống cảnh báo tự động được kích hoạt khi các chỉ số hiệu suất vượt quá ngưỡng suy giảm đã định trước hoặc có sự sai lệch đáng kể so với các đường cơ sở.                    |   2   | D/V  |
| 12.3.3 | Xác minh rằng các công cụ giám sát phát hiện ảo giác nhận diện và đánh dấu các trường hợp khi đầu ra của mô hình chứa thông tin không chính xác về mặt thực tế, không nhất quán hoặc giả mạo. |   2   | D/V  |

---

## C12.4 Hiệu suất & Telemetry Hành vi

|   #    | Description                                                                                                                                     | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.4.1 | Xác minh rằng các chỉ số vận hành bao gồm độ trễ yêu cầu, mức tiêu thụ token, sử dụng bộ nhớ và thông lượng được liên tục thu thập và giám sát. |   1   | D/V  |
| 12.4.2 | Xác minh rằng tỷ lệ thành công và thất bại được theo dõi với việc phân loại các loại lỗi và nguyên nhân gốc rễ của chúng.                       |   1   | D/V  |
| 12.4.3 | Xác minh rằng việc giám sát sử dụng tài nguyên bao gồm sử dụng GPU/CPU, tiêu thụ bộ nhớ và yêu cầu lưu trữ với cảnh báo khi vượt ngưỡng.        |   2   | D/V  |

---

## C12.5 Lập kế hoạch và Triển khai Ứng phó Sự cố AI

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Xác minh rằng các kế hoạch ứng phó sự cố đặc biệt đề cập đến các sự kiện bảo mật liên quan đến AI bao gồm việc xâm phạm mô hình, đầu độc dữ liệu và các cuộc tấn công đối kháng. |   1   | D/V  |
| 12.5.2 | Xác minh rằng các nhóm ứng phó sự cố có quyền truy cập vào các công cụ pháp y chuyên biệt cho AI và chuyên môn để điều tra hành vi mô hình và các vectơ tấn công.                |   2   | D/V  |
| 12.5.3 | Xác minh rằng phân tích sau sự cố bao gồm các cân nhắc về huấn luyện lại mô hình, cập nhật bộ lọc an toàn, và tích hợp bài học kinh nghiệm vào các biện pháp kiểm soát bảo mật.  |   3   | D/V  |

---

## C12.5 Phát hiện sự suy giảm hiệu năng AI

Giám sát và phát hiện suy giảm trong hiệu suất và chất lượng của mô hình AI theo thời gian.

|   #    | Description                                                                                                                                                | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.5.1 | Xác minh rằng độ chính xác, độ chính xác (precision), độ hồi tưởng (recall) và điểm F1 của mô hình được liên tục theo dõi và so sánh với các ngưỡng cơ sở. |   1   | D/V  |
| 12.5.2 | Xác minh rằng việc phát hiện trôi dữ liệu giám sát sự thay đổi trong phân phối đầu vào có thể ảnh hưởng đến hiệu suất mô hình.                             |   1   | D/V  |
| 12.5.3 | Xác minh rằng phát hiện trôi khái niệm có thể nhận diện các thay đổi trong mối quan hệ giữa đầu vào và đầu ra dự kiến.                                     |   2   | D/V  |
| 12.5.4 | Xác minh rằng sự suy giảm hiệu suất kích hoạt cảnh báo tự động và khởi động các quy trình tái huấn luyện hoặc thay thế mô hình.                            |   2   | D/V  |
| 12.5.5 | Xác nhận rằng phân tích nguyên nhân gốc rễ suy giảm liên kết sự sụt giảm hiệu suất với các thay đổi dữ liệu, sự cố hạ tầng hoặc các yếu tố bên ngoài.      |   3   |  V   |

---

## C12.6 Hình ảnh DAG & Bảo mật Quy trình làm việc

Bảo vệ hệ thống trực quan hóa quy trình làm việc khỏi rò rỉ thông tin và các tấn công thao túng.

|   #    | Description                                                                                                                                                                            | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.6.1 | Xác minh rằng dữ liệu trực quan hóa DAG được làm sạch để loại bỏ thông tin nhạy cảm trước khi lưu trữ hoặc truyền tải.                                                                 |   1   | D/V  |
| 12.6.2 | Xác minh rằng các kiểm soát truy cập trực quan hóa luồng công việc đảm bảo chỉ những người dùng được ủy quyền mới có thể xem đường đi quyết định của tác nhân và các dấu vết lập luận. |   1   | D/V  |
| 12.6.3 | Xác minh rằng tính toàn vẹn dữ liệu DAG được bảo vệ thông qua chữ ký mật mã và các cơ chế lưu trữ chống giả mạo.                                                                       |   2   | D/V  |
| 12.6.4 | Xác minh rằng hệ thống trực quan hóa quy trình làm việc thực hiện xác thực đầu vào để ngăn chặn các cuộc tấn công chèn mã thông qua các dữ liệu nút hoặc cạnh được tạo thủ công.       |   2   | D/V  |
| 12.6.5 | Xác minh rằng việc cập nhật DAG theo thời gian thực được giới hạn tốc độ và xác thực để ngăn chặn các cuộc tấn công từ chối dịch vụ vào hệ thống trực quan hóa.                        |   3   | D/V  |

---

## C12.7 Giám sát Hành vi An ninh Chủ động

Phát hiện và ngăn chặn các mối đe dọa bảo mật thông qua phân tích hành vi đại lý chủ động.

|   #    | Description                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 12.7.1 | Xác minh rằng các hành vi của tác nhân chủ động đã được kiểm chứng về an ninh trước khi thực thi với tích hợp đánh giá rủi ro.   |   1   | D/V  |
| 12.7.2 | Xác nhận rằng các tác nhân khởi xướng tự động bao gồm đánh giá bối cảnh bảo mật và đánh giá cảnh quan mối đe dọa.                |   2   | D/V  |
| 12.7.3 | Xác minh rằng các mẫu hành vi chủ động được phân tích để đánh giá các tác động bảo mật tiềm năng và các hậu quả không mong muốn. |   2   | D/V  |
| 12.7.4 | Xác minh rằng các hành động chủ động quan trọng về bảo mật yêu cầu chuỗi phê duyệt rõ ràng kèm theo dấu vết kiểm tra.            |   3   | D/V  |
| 12.7.5 | Xác minh rằng phát hiện bất thường hành vi xác định những sai lệch trong các mẫu tác nhân chủ động có thể chỉ ra sự xâm phạm.    |   3   | D/V  |

---

## Tài liệu tham khảo

* [NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6](https://www.iso.org/standard/81230.html)
* [EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689)


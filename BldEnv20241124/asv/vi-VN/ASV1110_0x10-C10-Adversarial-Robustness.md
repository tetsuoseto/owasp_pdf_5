# 10 Độ Bền Chống Đối Kháng & Phòng Thủ Quyền Riêng Tư

## Mục tiêu Kiểm soát

Đảm bảo rằng các mô hình AI vẫn đáng tin cậy, bảo vệ quyền riêng tư và chống lạm dụng khi đối mặt với các cuộc tấn công né tránh, suy luận, trích xuất hoặc đầu độc.

---

## 10.1 Căn chỉnh Mô hình & An toàn

Phòng tránh các đầu ra có hại hoặc vi phạm chính sách.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.1.1 | Xác minh rằng bộ kiểm tra sự phù hợp (các lời nhắc đội đỏ, các truy vấn vượt rào, nội dung bị cấm) được quản lý phiên bản và chạy trên mỗi lần phát hành mô hình. |   1   | D/V  |
| 10.1.2 | Xác minh rằng các biện pháp từ chối và bảo vệ hoàn thành an toàn được thực thi.                                                                                   |   1   |  D   |
| 10.1.3 | Xác minh rằng một bộ đánh giá tự động đo tỷ lệ nội dung gây hại và báo hiệu các sự suy giảm vượt quá ngưỡng đã đặt.                                               |   2   | D/V  |
| 10.1.4 | Xác minh rằng việc đào tạo chống vượt ngục được ghi chép và có thể tái hiện.                                                                                      |   2   |  D   |
| 10.1.5 | Xác minh rằng các bằng chứng tuân thủ chính sách chính thức hoặc giám sát được chứng nhận bao phủ các lĩnh vực quan trọng.                                        |   3   |  V   |

---

## 10.2 Củng cố chống lại ví dụ đối kháng

Tăng cường khả năng chống chịu trước các đầu vào bị thao túng. Huấn luyện đối kháng mạnh mẽ và đánh giá điểm chuẩn hiện là thực tiễn tốt nhất.

|   #    | Description                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.2.1 | Xác minh rằng các kho lưu trữ dự án bao gồm các cấu hình huấn luyện đối kháng với các hạt giống có thể tái tạo.                              |   1   |  D   |
| 10.2.2 | Xác minh rằng việc phát hiện các ví dụ đối kháng phát ra cảnh báo chặn trong các quy trình sản xuất.                                         |   2   | D/V  |
| 10.2.4 | Xác minh rằng các bằng chứng chắc chắn về độ bền được chứng nhận hoặc chứng chỉ giới hạn khoảng bao phủ ít nhất các lớp quan trọng hàng đầu. |   3   |  V   |
| 10.2.5 | Xác minh rằng các bài kiểm tra hồi quy sử dụng các cuộc tấn công thích ứng để xác nhận không có sự giảm độ bền đo được.                      |   3   |  V   |

---

## 10.3 Giảm thiểu rò rỉ thông tin thành viên (Membership-Inference)

Giới hạn khả năng quyết định xem một bản ghi có nằm trong dữ liệu đào tạo hay không. Bảo mật vi phân và che dấu điểm tin cậy vẫn là các phương pháp phòng thủ hiệu quả nhất được biết đến.

|   #    | Description                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 10.3.1 | Xác minh rằng việc điều chuẩn entropy theo từng truy vấn hoặc điều chỉnh nhiệt độ giảm các dự đoán quá tự tin.     |   1   |  D   |
| 10.3.2 | Xác nhận rằng việc đào tạo sử dụng tối ưu hóa bảo mật vi phân giới hạn bởi ε cho các bộ dữ liệu nhạy cảm.          |   2   |  D   |
| 10.3.3 | Xác minh rằng các mô phỏng tấn công (mô hình bóng hoặc hộp đen) cho thấy AUC tấn công ≤ 0,60 trên dữ liệu giữ lại. |   2   |  V   |

---

## 10.4 Kháng Chống Đảo Ngược Mô Hình

Ngăn chặn việc tái tạo các thuộc tính riêng tư. Các khảo sát gần đây nhấn mạnh việc cắt ngắn đầu ra và đảm bảo DP như các biện pháp phòng thủ thực tiễn.

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.4.1 | Xác minh rằng các thuộc tính nhạy cảm không bao giờ được xuất trực tiếp; khi cần, hãy sử dụng các nhóm hoặc biến đổi một chiều. |   1   |  D   |
| 10.4.2 | Xác minh rằng giới hạn tần suất truy vấn kiểm soát các truy vấn thích ứng lặp lại từ cùng một chủ thể.                          |   1   | D/V  |
| 10.4.3 | Xác nhận rằng mô hình được huấn luyện với nhiễu bảo vệ quyền riêng tư.                                                          |   2   |  D   |

---

## 10.5 Phòng chống trích xuất mô hình

Phát hiện và ngăn chặn việc sao chép trái phép. Nên sử dụng kỹ thuật đóng dấu (watermarking) và phân tích mẫu truy vấn.

|   #    | Description                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.5.1 | Xác minh rằng các cổng suy luận thực thi giới hạn tỷ lệ toàn cầu và trên từng khóa API được điều chỉnh phù hợp với ngưỡng ghi nhớ của mô hình. |   1   |  D   |
| 10.5.2 | Xác minh rằng thống kê entropy-truy vấn và đa dạng đầu vào cung cấp dữ liệu cho bộ phát hiện trích xuất tự động.                               |   2   | D/V  |
| 10.5.3 | Xác minh rằng các watermark dễ vỡ hoặc xác suất có thể được chứng minh với p < 0,01 trong ≤ 1.000 truy vấn chống lại một bản sao nghi ngờ.     |   2   |  V   |
| 10.5.4 | Xác minh rằng các khóa watermark và bộ kích hoạt được lưu trữ trong mô-đun bảo mật phần cứng và được thay đổi mỗi năm.                         |   3   |  D   |
| 10.5.5 | Xác minh rằng các sự kiện cảnh báo trích xuất bao gồm các truy vấn vi phạm và được tích hợp với sách hướng dẫn ứng phó sự cố.                  |   3   |  V   |

---

## 10.6 Phát hiện dữ liệu đầu vào bị nhiễm độc vào thời điểm suy luận

Xác định và trung hòa các đầu vào có cửa hậu hoặc bị đầu độc.

|   #    | Description                                                                                                                                       | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.6.1 | Xác minh rằng các đầu vào được chuyển qua bộ phát hiện bất thường (ví dụ: STRIP, điểm số nhất quán) trước khi suy luận mô hình.                   |   1   |  D   |
| 10.6.2 | Xác minh rằng các ngưỡng bộ phát hiện được điều chỉnh trên các bộ dữ liệu xác thực sạch/đã bị nhiễm độc để đạt được tỷ lệ dương tính giả dưới 5%. |   1   |  V   |
| 10.6.3 | Xác minh rằng các đầu vào bị đánh dấu là bị nhiễm độc kích hoạt việc chặn mềm và quy trình xem xét của con người.                                 |   2   |  D   |
| 10.6.4 | Xác minh rằng các bộ phát hiện được kiểm tra độ bền với các cuộc tấn công cửa hậu không kích hoạt thích ứng.                                      |   2   |  V   |
| 10.6.5 | Xác minh rằng các chỉ số hiệu quả phát hiện được ghi lại và định kỳ đánh giá lại với thông tin tình báo về mối đe dọa mới.                        |   3   |  D   |

---

## 10.7 Điều chỉnh Chính sách Bảo mật Động

Cập nhật chính sách bảo mật theo thời gian thực dựa trên thông tin tình báo mối đe dọa và phân tích hành vi.

|   #    | Description                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.7.1 | Xác minh rằng các chính sách bảo mật có thể được cập nhật động mà không cần khởi động lại agent đồng thời duy trì tính toàn vẹn của phiên bản chính sách. |   1   | D/V  |
| 10.7.2 | Xác minh rằng các cập nhật chính sách được ký bằng mật mã bởi nhân viên an ninh có thẩm quyền và được xác thực trước khi áp dụng.                         |   2   | D/V  |
| 10.7.3 | Xác minh rằng các thay đổi chính sách động được ghi lại với toàn bộ hồ sơ kiểm toán bao gồm lý do, chuỗi phê duyệt và quy trình hoàn tác.                 |   2   | D/V  |
| 10.7.4 | Xác minh rằng các cơ chế bảo mật thích ứng điều chỉnh độ nhạy phát hiện mối đe dọa dựa trên bối cảnh rủi ro và các mẫu hành vi.                           |   3   | D/V  |
| 10.7.5 | Xác minh rằng các quyết định điều chỉnh chính sách có thể giải thích được và bao gồm dấu vết bằng chứng để nhóm bảo mật xem xét.                          |   3   | D/V  |

---

## 10.8 Phân tích Bảo mật Dựa trên Phản chiếu

Xác thực bảo mật thông qua phản ánh tự động của tác nhân và phân tích siêu nhận thức.

|   #    | Description                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.8.1 | Xác minh rằng các cơ chế phản chiếu của đại lý bao gồm việc tự đánh giá các quyết định và hành động với trọng tâm an ninh.                              |   1   | D/V  |
| 10.8.2 | Xác minh rằng các đầu ra phản chiếu được kiểm tra để ngăn chặn việc thao túng các cơ chế tự đánh giá bởi các đầu vào đối kháng.                         |   2   | D/V  |
| 10.8.3 | Xác minh rằng phân tích bảo mật siêu nhận thức xác định được sự thiên vị tiềm ẩn, thao túng hoặc sự xâm phạm trong các quá trình lập luận của tác nhân. |   2   | D/V  |
| 10.8.4 | Xác minh rằng các cảnh báo bảo mật dựa trên phản chiếu kích hoạt giám sát nâng cao và các quy trình can thiệp của con người tiềm năng.                  |   3   | D/V  |
| 10.8.5 | Xác minh rằng việc học liên tục từ các phản ánh về bảo mật cải thiện phát hiện mối đe dọa mà không làm giảm chức năng hợp lệ.                           |   3   | D/V  |

---

## 10.9 An ninh Tiến hóa & Tự Cải thiện

Kiểm soát an ninh cho các hệ thống tác nhân có khả năng tự sửa đổi và tiến hóa.

|   #    | Description                                                                                                                     | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 10.9.1 | Xác minh rằng khả năng tự chỉnh sửa bị giới hạn trong các khu vực an toàn được chỉ định với các ranh giới xác minh chính thức.  |   1   | D/V  |
| 10.9.2 | Xác minh rằng các đề xuất phát triển được tiến hành đánh giá tác động bảo mật trước khi triển khai.                             |   2   | D/V  |
| 10.9.3 | Xác minh rằng các cơ chế tự cải tiến bao gồm khả năng phục hồi với việc kiểm tra tính toàn vẹn.                                 |   2   | D/V  |
| 10.9.4 | Xác minh rằng bảo mật meta-learning ngăn chặn việc thao túng đối nghịch các thuật toán cải tiến.                                |   3   | D/V  |
| 10.9.5 | Xác minh rằng việc tự cải tiến đệ quy bị giới hạn bởi các ràng buộc an toàn hình thức với các chứng minh toán học về sự hội tụ. |   3   | D/V  |

---

### Tài liệu tham khảo

* [MITRE ATLAS adversary tactics for ML](https://atlas.mitre.org/)
* [NIST AI Risk Management Framework 1.0, 2023](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [OWASP Top 10 for LLM Applications, 2025](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Adversarial Training: A Survey — Zhao et al., 2024](https://arxiv.org/abs/2410.15042)
* [RobustBench adversarial-robustness benchmark](https://robustbench.github.io/)
* [Membership-Inference & Model-Inversion Risk Survey, 2025](https://www.sciencedirect.com/science/article/abs/pii/S0950705125003867)
* [PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023](https://ojs.aaai.org/index.php/AAAI/article/view/26289)
* [Model-Inversion Attacks & Defenses Survey — AI Review, 2025](https://link.springer.com/article/10.1007/s10462-025-11248-0)
* [Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024](https://doi.org/10.1109/TDSC.2023.3261327)
* [Fragile Model Watermarking Survey — 2025](https://www.sciencedirect.com/science/article/abs/pii/S0165168425002026)
* [Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025](https://arxiv.org/abs/2503.22759)
* [BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024](https://arxiv.org/abs/2405.15269)


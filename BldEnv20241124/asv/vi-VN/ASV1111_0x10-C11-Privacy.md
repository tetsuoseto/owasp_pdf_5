# 11 Bảo vệ quyền riêng tư & Quản lý dữ liệu cá nhân

## Mục tiêu Kiểm soát

Duy trì các cam kết bảo mật nghiêm ngặt suốt toàn bộ vòng đời AI — từ thu thập, đào tạo, suy luận đến phản ứng sự cố — để dữ liệu cá nhân chỉ được xử lý khi có sự đồng ý rõ ràng, phạm vi cần thiết tối thiểu, khả năng chứng minh việc xóa dữ liệu và các đảm bảo bảo mật chính thức.

---

## 11.1 Ẩn danh & Tối thiểu hóa dữ liệu

|   #    | Description                                                                                                                                            | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.1.1 | Xác minh rằng các nhận dạng trực tiếp và nhận dạng gần đúng đã được loại bỏ hoặc băm.                                                                  |   1   | D/V  |
| 11.1.2 | Xác minh rằng các cuộc kiểm toán tự động đo lường k-ẩn danh/l-đa dạng và cảnh báo khi các ngưỡng giảm xuống dưới chính sách.                           |   2   | D/V  |
| 11.1.3 | Xác minh rằng các báo cáo tầm quan trọng tính năng của mô hình chứng minh không có rò rỉ định danh vượt quá ε = 0,01 thông tin hỗ tương.               |   2   |  V   |
| 11.1.4 | Xác minh rằng các bằng chứng chính thức hoặc chứng nhận dữ liệu tổng hợp cho thấy rủi ro tái nhận dạng ≤ 0,05 ngay cả dưới các cuộc tấn công liên kết. |   3   |  V   |

---

## 11.2 Quyền được Xóa và Thực thi Xóa dữ liệu

|   #    | Description                                                                                                                                                                                 | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.2.1 | Xác minh rằng các yêu cầu xóa dữ liệu của đối tượng được truyền đến các bộ dữ liệu thô, điểm kiểm tra, nhúng, nhật ký và các bản sao lưu trong phạm vi thỏa thuận cấp dịch vụ dưới 30 ngày. |   1   | D/V  |
| 11.2.2 | Xác minh rằng các quy trình "machine-unlearning" thực sự tái đào tạo hoặc xấp xỉ loại bỏ bằng cách sử dụng các thuật toán unlearning đã được chứng nhận.                                    |   2   |  D   |
| 11.2.3 | Xác minh rằng đánh giá mô hình bóng chứng minh các bản ghi đã quên ảnh hưởng dưới 1% các kết quả sau khi học lại.                                                                           |   2   |  V   |
| 11.2.4 | Xác minh rằng các sự kiện xóa được ghi lại một cách không thể thay đổi và có thể kiểm tra đối với các nhà quản lý.                                                                          |   3   |  V   |

---

## 11.3 Các Biện pháp Bảo vệ Quyền Riêng tư Khác biệt

|   #    | Description                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.3.1 | Xác minh rằng bảng điều khiển theo dõi mất mát quyền riêng tư cảnh báo khi ε tích lũy vượt quá ngưỡng chính sách. |   2   | D/V  |
| 11.3.2 | Xác minh rằng các cuộc kiểm toán quyền riêng tư hộp đen ước lượng ε̂ trong phạm vi 10% so với giá trị đã công bố. |   2   |  V   |
| 11.3.3 | Xác nhận rằng các chứng minh hình thức bao gồm tất cả các việc tinh chỉnh sau khi đào tạo và các biểu diễn nhúng. |   3   |  V   |

---

## 11.4 Hạn chế Mục đích & Bảo vệ khỏi Tràn Phạm vi

|   #    | Description                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.4.1 | Xác minh rằng mọi bộ dữ liệu và điểm kiểm tra mô hình đều mang thẻ mục đích có thể đọc được bằng máy, phù hợp với sự đồng thuận ban đầu. |   1   |  D   |
| 11.4.2 | Xác minh rằng các bộ giám sát thời gian chạy phát hiện các truy vấn không nhất quán với mục đích đã công bố và kích hoạt từ chối mềm.    |   1   | D/V  |
| 11.4.3 | Xác minh rằng các cổng chính sách dưới dạng mã ngăn chặn việc triển khai lại các mô hình sang các miền mới mà không có đánh giá DPIA.    |   3   |  D   |
| 11.4.4 | Xác minh rằng các bằng chứng truy xuất nguồn gốc chính thức cho thấy mọi vòng đời dữ liệu cá nhân đều nằm trong phạm vi đã được đồng ý.  |   3   |  V   |

---

## 11.5 Quản lý sự đồng ý & theo dõi cơ sở hợp pháp

|   #    | Description                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 11.5.1 | Xác minh rằng Nền tảng Quản lý Đồng ý (CMP) ghi lại trạng thái đồng ý, mục đích và thời gian lưu trữ của từng cá nhân dữ liệu. |   1   | D/V  |
| 11.5.2 | Xác minh rằng các API phô bày token đồng thuận; các mô hình phải xác thực phạm vi token trước khi suy diễn.                    |   2   |  D   |
| 11.5.3 | Xác minh rằng việc từ chối hoặc rút lại sự đồng ý sẽ dừng các quy trình xử lý trong vòng 24 giờ.                               |   2   | D/V  |

---

## 11.6 Học Liên Liền với Các Kiểm Soát Quyền Riêng Tư

|   #    | Description                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 11.6.1 | Xác minh rằng các cập nhật của khách hàng sử dụng thêm nhiễu bảo mật vi sai cục bộ trước khi tổng hợp.                                             |   1   |  D   |
| 11.6.2 | Xác minh rằng các chỉ số huấn luyện tuân thủ ưu tiên tuyệt đối về quyền riêng tư và không bao giờ tiết lộ tổn thất của từng khách hàng riêng biệt. |   2   | D/V  |
| 11.6.3 | Xác nhận rằng phương pháp tổng hợp chống đầu độc (ví dụ, Krum/Trimmed-Mean) đã được kích hoạt.                                                     |   2   |  V   |
| 11.6.4 | Xác minh rằng các chứng minh hình thức trình bày tổng ngân sách ε với mức mất mát tiện ích dưới 5.                                                 |   3   |  V   |

---

### Tài liệu tham khảo

* [GDPR & AI Compliance Best Practices](https://www.exabeam.com/explainers/gdpr-compliance/the-intersection-of-gdpr-and-ai-and-6-compliance-best-practices/)
* [EU Parliament Study on GDPR & AI, 2020](https://www.europarl.europa.eu/RegData/etudes/STUD/2020/641530/EPRS_STU%282020%29641530_EN.pdf)
* [ISO 31700-1:2023 — Privacy by Design for Consumer Products](https://www.iso.org/standard/84977.html)
* [NIST Privacy Framework 1.1 (2025 Draft)](https://www.nist.gov/privacy-framework)
* [Machine Unlearning: Right-to-Be-Forgotten Techniques](https://www.kaggle.com/code/tamlhp/machine-unlearning-the-right-to-be-forgotten)
* [A Survey of Machine Unlearning, 2024](https://arxiv.org/html/2209.02299v6)
* [Auditing DP-SGD — ArXiv 2024](https://arxiv.org/html/2405.14106v4)
* [DP-SGD Explained — PyTorch Blog](https://medium.com/pytorch/differential-privacy-series-part-1-dp-sgd-algorithm-explained-12512c3959a3)
* [Purpose-Limitation for AI — IJLIT 2025](https://academic.oup.com/ijlit/article/doi/10.1093/ijlit/eaaf003/8121663)
* [Data-Protection Considerations for AI — URM Consulting](https://www.urmconsulting.com/blog/data-protection-considerations-for-artificial-intelligence-ai)
* [Top Consent-Management Platforms, 2025](https://www.enzuzo.com/blog/best-consent-management-platforms)
* [Secure Aggregation in DP Federated Learning — ArXiv 2024](https://arxiv.org/abs/2407.19286)


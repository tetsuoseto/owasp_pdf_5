# C13 Giám sát Con người, Trách nhiệm & Quản trị

## Mục tiêu kiểm soát

Chương này cung cấp các yêu cầu để duy trì sự giám sát của con người và các chuỗi trách nhiệm rõ ràng trong các hệ thống AI, đảm bảo khả năng giải thích, minh bạch và quản lý đạo đức xuyên suốt vòng đời của AI.

---

## C13.1 Cơ chế Ngắt Kết nối và Ghi đè

Cung cấp các phương án tắt hoặc quay lại khi phát hiện hành vi không an toàn của hệ thống AI.

|   #    | Description                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.1.1 | Xác minh rằng có cơ chế công tắc ngắt thủ công để ngay lập tức dừng việc suy diễn và đầu ra của mô hình AI.                |   1   | D/V  |
| 13.1.2 | Xác minh rằng các kiểm soát ghi đè chỉ có thể truy cập được bởi nhân sự được ủy quyền.                                     |   1   |  D   |
| 13.1.3 | Xác minh rằng các quy trình hoàn tác có thể khôi phục về các phiên bản mô hình trước đó hoặc các hoạt động chế độ an toàn. |   3   | D/V  |
| 13.1.4 | Xác minh rằng các cơ chế ghi đè được kiểm tra thường xuyên.                                                                |   3   |  V   |

---

## C13.2 Các Điểm Kiểm Tra Quyết Định Có Con Người Tham Gia

Yêu cầu phê duyệt của con người khi mức độ rủi ro vượt qua ngưỡng đã định trước.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.2.1 | Xác minh rằng các quyết định AI có rủi ro cao cần được sự duyệt xét rõ ràng của con người trước khi thực hiện.                                                    |   1   | D/V  |
| 13.2.2 | Xác minh rằng ngưỡng rủi ro được định nghĩa rõ ràng và tự động kích hoạt các quy trình xem xét của con người.                                                     |   1   |  D   |
| 13.2.3 | Xác minh rằng các quyết định nhạy cảm về thời gian có quy trình dự phòng khi không thể nhận được sự phê duyệt của con người trong khoảng thời gian yêu cầu.       |   2   |  D   |
| 13.2.4 | Xác minh rằng các quy trình leo thang đã định nghĩa rõ ràng các cấp độ thẩm quyền cho các loại quyết định khác nhau hoặc các danh mục rủi ro, nếu có thể áp dụng. |   3   | D/V  |

---

## C13.3 Chuỗi Trách Nhiệm & Khả Năng Kiểm Toán

Ghi lại các hành động của người vận hành và các quyết định của mô hình.

|   #    | Description                                                                                                                                                      | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.3.1 | Xác minh rằng tất cả các quyết định của hệ thống AI và các can thiệp của con người đều được ghi lại với dấu thời gian, danh tính người dùng và lý do quyết định. |   1   | D/V  |
| 13.3.2 | Xác minh rằng các nhật ký kiểm toán không thể bị làm giả và bao gồm các cơ chế xác minh tính toàn vẹn.                                                           |   2   |  D   |

---

## C13.4 Kỹ thuật AI Có thể Giải thích được

Tầm quan trọng của đặc trưng bề mặt, các phản thực, và giải thích cục bộ.

|   #    | Description                                                                                                                                                                                               | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.4.1 | Xác minh rằng các hệ thống AI cung cấp các giải thích cơ bản cho quyết định của chúng dưới định dạng dễ đọc đối với con người.                                                                            |   1   | D/V  |
| 13.4.2 | Xác minh rằng chất lượng giải thích được xác nhận thông qua các nghiên cứu đánh giá của con người và các chỉ số.                                                                                          |   2   |  V   |
| 13.4.3 | Xác minh rằng các điểm quan trọng của đặc trưng hoặc các phương pháp gán thuộc tính (SHAP, LIME, v.v.) có sẵn cho các quyết định quan trọng.                                                              |   3   | D/V  |
| 13.4.4 | Xác minh rằng các giải thích phản thực (counterfactual explanations) cho thấy cách các đầu vào có thể được điều chỉnh để thay đổi kết quả, nếu áp dụng được cho trường hợp sử dụng và lĩnh vực tương ứng. |   3   |  V   |

---

## C13.5 Thẻ Mô Hình & Công Bố Sử Dụng

Duy trì thẻ mô hình cho mục đích sử dụng, các chỉ số hiệu suất và các cân nhắc đạo đức.

|   #    | Description                                                                                                                                                                           | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.5.1 | Xác minh rằng các thẻ mô hình ghi lại các trường hợp sử dụng dự kiến, giới hạn và các chế độ lỗi đã biết.                                                                             |   1   |  D   |
| 13.5.2 | Xác minh rằng các chỉ số hiệu suất trong các trường hợp sử dụng áp dụng khác nhau đã được công bố.                                                                                    |   1   | D/V  |
| 13.5.3 | Xác minh rằng các cân nhắc đạo đức, đánh giá thiên vị, đánh giá công bằng, đặc điểm dữ liệu tập huấn, và các hạn chế dữ liệu tập huấn đã biết được ghi chép và cập nhật thường xuyên. |   2   |  D   |
| 13.5.4 | Xác minh rằng thẻ mô hình được kiểm soát phiên bản và duy trì trong suốt vòng đời của mô hình với việc theo dõi thay đổi.                                                             |   2   | D/V  |

---

## C13.6 Định lượng bất định

Truyền đạt điểm tin cậy hoặc các đo lường entropy trong các phản hồi.

|   #    | Description                                                                                                                 | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.6.1 | Xác minh rằng các hệ thống AI cung cấp điểm tin cậy hoặc các thước đo độ không chắc chắn cùng với kết quả đầu ra của chúng. |   1   |  D   |
| 13.6.2 | Xác minh rằng các ngưỡng không chắc chắn kích hoạt việc đánh giá thêm bởi con người hoặc các con đường quyết định thay thế. |   2   | D/V  |
| 13.6.3 | Xác minh rằng các phương pháp lượng hóa không chắc chắn đã được hiệu chuẩn và xác thực dựa trên dữ liệu thực tế.            |   2   |  V   |
| 13.6.4 | Xác minh rằng sự lan truyền bất định được duy trì qua các quy trình làm việc AI đa bước.                                    |   3   | D/V  |

---

## C13.7 Báo Cáo Minh Bạch Hướng Đến Người Dùng

Cung cấp các báo cáo định kỳ về các sự cố, sự thay đổi (drift), và việc sử dụng dữ liệu.

|   #    | Description                                                                                                                               | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 13.7.1 | Xác minh rằng các chính sách sử dụng dữ liệu và thực hành quản lý sự đồng ý của người dùng được truyền đạt rõ ràng đến các bên liên quan. |   1   | D/V  |
| 13.7.2 | Xác minh rằng các đánh giá tác động AI được tiến hành và kết quả được bao gồm trong báo cáo.                                              |   2   | D/V  |
| 13.7.3 | Xác minh rằng các báo cáo minh bạch được công bố định kỳ tiết lộ các sự cố AI và các chỉ số hoạt động một cách chi tiết hợp lý.           |   2   | D/V  |

### Tài liệu tham khảo

* [EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj)
* [ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management](https://www.iso.org/standard/77304.html)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [NIST SP 800-53 Revision 5 — Security and Privacy Controls](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r5.pdf)
* [A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)](https://arxiv.org/abs/1705.07874)
* [Model Cards for Model Reporting (Mitchell et al., 2018)](https://arxiv.org/abs/1810.03993)
* [Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)](https://arxiv.org/abs/1506.02142)
* [ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods](https://www.iso.org/standard/79804.html)
* [IEEE 7001-2021 — Transparency of Autonomous Systems](https://standards.ieee.org/ieee/7001/6929/)
* [GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX%3A32016R0679)
* [Human Oversight under Article 14 of the EU AI Act (Fink, 2025)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5147196)


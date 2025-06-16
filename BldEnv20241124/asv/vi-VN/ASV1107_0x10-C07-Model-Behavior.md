# Hành vi mô hình C7, Kiểm soát đầu ra và Đảm bảo an toàn

## Mục tiêu kiểm soát

Đầu ra của mô hình phải được cấu trúc, đáng tin cậy, an toàn, có thể giải thích và được giám sát liên tục trong môi trường sản xuất. Việc này giúp giảm thiểu các ảo giác, rò rỉ thông tin riêng tư, nội dung gây hại và các hành động ngoài dự kiến, đồng thời tăng cường sự tin tưởng của người dùng và tuân thủ các quy định.

---

## C7.1 Thực thi định dạng đầu ra

Các sơ đồ nghiêm ngặt, giải mã hạn chế và xác thực hạ nguồn ngăn chặn nội dung bị lỗi hoặc độc hại trước khi nó lan truyền.

|   #   | Description                                                                                                                                                                                       | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.1.1 | Xác minh rằng các sơ đồ phản hồi (ví dụ: JSON Schema) được cung cấp trong lời nhắc hệ thống và mọi đầu ra đều được tự động xác thực; các đầu ra không phù hợp sẽ kích hoạt sửa chữa hoặc từ chối. |   1   | D/V  |
| 7.1.2 | Xác minh rằng giải mã có giới hạn (token dừng, regex, tối đa token) được bật để ngăn ngừa tràn bộ đệm hoặc các kênh bên của việc tiêm lệnh vào prompt.                                            |   1   | D/V  |
| 7.1.3 | Xác minh rằng các thành phần hạ nguồn coi các đầu ra là không được tin cậy và kiểm tra chúng dựa trên các sơ đồ hoặc bộ giải tuần tự hóa an toàn chống chèn mã.                                   |   2   | D/V  |
| 7.1.4 | Xác minh rằng các sự kiện đầu ra không đúng được ghi lại, giới hạn tần suất và hiển thị lên hệ thống giám sát.                                                                                    |   3   |  V   |

---

## C7.2 Phát hiện và Giảm thiểu Ảo giác

Ước lượng độ không chắc chắn và các chiến lược dự phòng giúp giảm thiểu các câu trả lời bịa đặt.

|   #   | Description                                                                                                                                                                                      | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 7.2.1 | Xác minh rằng xác suất log cấp token, độ nhất quán nội bộ của tập hợp mô hình, hoặc các bộ phát hiện ảo tưởng được tinh chỉnh đều gán điểm tin cậy cho từng câu trả lời.                         |   1   | D/V  |
| 7.2.2 | Xác nhận rằng các phản hồi dưới ngưỡng độ tin cậy có thể cấu hình kích hoạt quy trình làm việc dự phòng (ví dụ: tạo câu trả lời tăng cường truy xuất, mô hình phụ, hoặc đánh giá bởi con người). |   1   | D/V  |
| 7.2.3 | Xác minh rằng các sự cố ảo giác được gắn thẻ với siêu dữ liệu nguyên nhân gốc rễ và được đưa vào các quy trình phân tích sau sự kiện và tinh chỉnh.                                              |   2   | D/V  |
| 7.2.4 | Xác minh rằng các ngưỡng và bộ dò được hiệu chuẩn lại sau các cập nhật lớn về mô hình hoặc cơ sở tri thức.                                                                                       |   3   | D/V  |
| 7.2.5 | Xác minh rằng các trực quan trên bảng điều khiển theo dõi tỷ lệ ảo giác.                                                                                                                         |   3   |  V   |

---

## C7.3 Lọc An toàn & Bảo mật Đầu ra

Bộ lọc chính sách và phạm vi kiểm tra đội đỏ bảo vệ người dùng và dữ liệu bí mật.

|   #   | Description                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.3.1 | Xác minh rằng các bộ phân loại trước và sau khi tạo chặn các nội dung gây thù hận, quấy rối, tự làm hại, cực đoan và nội dung khiêu dâm phù hợp với chính sách. |   1   | D/V  |
| 7.3.2 | Xác minh rằng việc phát hiện PII/PCI và tự động làm mờ được thực hiện trên mọi phản hồi; các vi phạm sẽ kích hoạt một sự cố về quyền riêng tư.                  |   1   | D/V  |
| 7.3.3 | Xác minh rằng các thẻ bảo mật (ví dụ: bí mật thương mại) được lan truyền qua các chế độ khác nhau để ngăn ngừa rò rỉ trong văn bản, hình ảnh hoặc mã.           |   2   |  D   |
| 7.3.4 | Xác minh rằng các cố gắng vượt qua bộ lọc hoặc các phân loại rủi ro cao yêu cầu phê duyệt phụ hoặc xác thực người dùng lại.                                     |   3   | D/V  |
| 7.3.5 | Xác minh rằng các ngưỡng lọc phản ánh vùng pháp lý và bối cảnh độ tuổi/vai trò của người dùng.                                                                  |   3   | D/V  |

---

## C7.4 Giới hạn Đầu ra & Hành động

Giới hạn tần suất và cổng phê duyệt ngăn ngừa việc lạm dụng và quyền tự trị quá mức.

|   #   | Description                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.4.1 | Xác minh rằng hạn mức cho từng người dùng và từng khóa API giới hạn yêu cầu, token và chi phí với cơ chế tăng thời gian chờ theo cấp số nhân khi gặp lỗi 429.                     |   1   |  D   |
| 7.4.2 | Xác minh rằng các hành động đặc quyền (ghi tập tin, thực thi mã, gọi mạng) yêu cầu sự phê duyệt dựa trên chính sách hoặc có sự can thiệp của con người trong quá trình thực hiện. |   1   | D/V  |
| 7.4.3 | Xác minh rằng các kiểm tra nhất quán đa phương thức đảm bảo hình ảnh, mã và văn bản được tạo ra cho cùng một yêu cầu không thể được sử dụng để buôn lậu nội dung độc hại.         |   2   | D/V  |
| 7.4.4 | Xác minh rằng độ sâu ủy quyền đại lý, giới hạn đệ quy và danh sách công cụ được phép được cấu hình rõ ràng.                                                                       |   2   |  D   |
| 7.4.5 | Xác minh rằng việc vi phạm giới hạn phát ra các sự kiện bảo mật có cấu trúc để tiếp nhận vào hệ thống SIEM.                                                                       |   3   |  V   |

---

## C7.5 Giải thích Đầu ra

Các tín hiệu minh bạch cải thiện sự tin tưởng của người dùng và hỗ trợ gỡ lỗi nội bộ.

|   #   | Description                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.5.1 | Xác minh rằng các điểm số độ tin cậy đối với người dùng hoặc các bản tóm tắt lý do ngắn gọn được hiển thị khi đánh giá rủi ro cho là phù hợp. |   2   | D/V  |
| 7.5.2 | Xác minh rằng các giải thích được tạo ra không tiết lộ các lời nhắc hệ thống nhạy cảm hoặc dữ liệu sở hữu độc quyền.                          |   2   | D/V  |
| 7.5.3 | Xác minh rằng hệ thống ghi lại xác suất log ở cấp độ token hoặc bản đồ chú ý và lưu trữ chúng để kiểm tra có thẩm quyền.                      |   3   |  D   |
| 7.5.4 | Xác minh rằng các tài liệu giải thích được quản lý phiên bản cùng với các bản phát hành mô hình để đảm bảo khả năng kiểm tra.                 |   3   |  V   |

---

## C7.6 Tích hợp giám sát

Khả năng quan sát thời gian thực kết nối vòng lặp giữa phát triển và sản xuất.

|   #   | Description                                                                                                                                                       | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.6.1 | Xác minh rằng các chỉ số (vi phạm lược đồ, tỷ lệ ảo giác, độ độc hại, rò rỉ thông tin cá nhân, độ trễ, chi phí) được truyền đến một nền tảng giám sát trung tâm.  |   1   |  D   |
| 7.6.2 | Xác nhận rằng các ngưỡng cảnh báo được định nghĩa cho từng chỉ số an toàn, kèm theo các con đường leo thang trong ca trực.                                        |   1   |  V   |
| 7.6.3 | Xác minh rằng các bảng điều khiển liên kết các điểm bất thường đầu ra với mô hình/phiên bản, cờ tính năng và các thay đổi dữ liệu nguồn cấp.                      |   2   |  V   |
| 7.6.4 | Xác minh rằng dữ liệu giám sát được phản hồi vào quá trình tái đào tạo, điều chỉnh tinh chỉnh, hoặc cập nhật quy tắc trong một quy trình MLOps được tài liệu hóa. |   2   | D/V  |
| 7.6.5 | Xác minh rằng các pipeline giám sát đã được kiểm tra xâm nhập và kiểm soát truy cập để tránh rò rỉ các nhật ký nhạy cảm.                                          |   3   |  V   |

---

## 7.7 Biện pháp bảo vệ truyền thông tạo sinh

Đảm bảo rằng hệ thống AI không tạo ra nội dung phương tiện bất hợp pháp, có hại hoặc không được phép bằng cách thực thi các giới hạn chính sách, xác thực đầu ra và khả năng truy xuất nguồn gốc.

|   #   | Description                                                                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 7.7.1 | Xác minh rằng các lời nhắc hệ thống và hướng dẫn người dùng rõ ràng cấm việc tạo ra các phương tiện deepfake bất hợp pháp, có hại hoặc không có sự đồng thuận (ví dụ: hình ảnh, video, âm thanh).                               |   1   | D/V  |
| 7.7.2 | Xác minh rằng các câu lệnh được lọc để ngăn chặn các cố gắng tạo ra các bản giả mạo, deepfake mang tính khiêu dâm, hoặc các phương tiện truyền thông mô tả cá nhân thật mà không có sự đồng ý.                                  |   2   | D/V  |
| 7.7.3 | Xác minh rằng hệ thống sử dụng băm nhận thức, phát hiện watermark, hoặc gán dấu vân tay để ngăn chặn việc sao chép trái phép các phương tiện có bản quyền.                                                                      |   2   |  V   |
| 7.7.4 | Xác minh rằng tất cả các phương tiện được tạo ra đều được ký số mật mã, đóng dấu bản quyền, hoặc nhúng metadata nguồn gốc chống giả mạo để đảm bảo khả năng truy xuất nguồn gốc trong quá trình xử lý tiếp theo.                |   3   | D/V  |
| 7.7.5 | Xác minh rằng các nỗ lực vượt qua (ví dụ: làm rối câu lệnh đầu vào, sử dụng tiếng lóng, cách diễn đạt đối nghịch) được phát hiện, ghi lại và giới hạn tần suất; lạm dụng lặp đi lặp lại được báo cáo cho các hệ thống giám sát. |   3   |  V   |

## Tài liệu tham khảo

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [ISO/IEC 42001:2023 – AI Management System](https://www.iso.org/obp/ui/en/)
* [OWASP Top-10 for Large Language Model Applications (2025)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
* [Improper Output Handling – OWASP LLM05:2025](https://genai.owasp.org/llmrisk/llm052025-improper-output-handling/)
* [Practical Techniques to Constrain LLM Output](https://mychen76.medium.com/practical-techniques-to-constraint-llm-output-in-json-format-e3e72396c670)
* [Dataiku – Structured Text Generation Guide](https://blog.dataiku.com/your-guide-to-structured-text-generation)
* [VL-Uncertainty: Detecting Hallucinations](https://arxiv.org/abs/2411.11919)
* [HaDeMiF: Hallucination Detection & Mitigation](https://openreview.net/forum?id=VwOYxPScxB)
* [Building Confidence in LLM Outputs](https://www.alkymi.io/data-science-room/building-confidence-in-llm-outputs)
* [Explainable AI & LLMs](https://duncsand.medium.com/explainable-ai-140912d31b3b)
* [LLM Red-Teaming Guide](https://www.confident-ai.com/blog/red-teaming-llms-a-step-by-step-guide)
* [Sensitive Information Disclosure in LLMs](https://virtualcyberlabs.com/llm-sensitive-information-disclosure/)
* [LangChain – Chat Model Rate Limiting](https://python.langchain.com/docs/how_to/chat_model_rate_limiting/)
* [OpenAI Rate-Limit & Exponential Back-off](https://hackernoon.com/openais-rate-limit-a-guide-to-exponential-backoff-for-llm-evaluation)
* [Arize AI – LLM Observability Platform](https://arize.com/)


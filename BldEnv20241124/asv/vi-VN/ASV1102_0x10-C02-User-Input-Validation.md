# Xác thực đầu vào của người dùng C2

## Mục tiêu kiểm soát

Xác thực đầu vào của người dùng một cách chặt chẽ là lá chắn phòng thủ hàng đầu chống lại một số cuộc tấn công gây hại nhất đối với các hệ thống AI. Các cuộc tấn công chèn prompt có thể ghi đè các lệnh hệ thống, rò rỉ dữ liệu nhạy cảm hoặc điều khiển mô hình theo hướng hành vi không được phép. Trừ khi có các bộ lọc chuyên dụng và cấu trúc chỉ dẫn phân cấp được thiết lập, nghiên cứu cho thấy các phương pháp jailbreak "đa lần" khai thác cửa sổ ngữ cảnh rất dài sẽ hiệu quả. Ngoài ra, các cuộc tấn công gây nhiễu đối kháng tinh vi — như việc hoán đổi ký tự giống hình dạng (homoglyph) hoặc ngôn ngữ leetspeak — có thể âm thầm thay đổi các quyết định của mô hình.

---

## Phòng thủ Tiêm nhiễm Lệnh (Prompt Injection Defense) C2.1

Tấn công chèn đoạn lệnh (prompt injection) là một trong những rủi ro hàng đầu đối với các hệ thống AI. Các biện pháp phòng vệ chống lại chiến thuật này sử dụng sự kết hợp giữa bộ lọc mẫu tĩnh, bộ phân loại động và việc thực thi thứ bậc hướng dẫn.

|   #   | Description                                                                                                                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.1.1 | Xác minh rằng các đầu vào của người dùng được kiểm tra dựa trên một thư viện liên tục được cập nhật các mẫu tấn công chèn lệnh (từ khóa jailbreak, "bỏ qua trước đó", chuỗi nhập vai, các cuộc tấn công gián tiếp qua HTML/URL).                                         |   1   | D/V  |
| 2.1.2 | Xác minh rằng hệ thống thi hành một cấu trúc hướng dẫn theo thứ bậc trong đó các thông điệp của hệ thống hoặc nhà phát triển ghi đè lên các hướng dẫn của người dùng, ngay cả sau khi mở rộng cửa sổ ngữ cảnh.                                                           |   1   | D/V  |
| 2.1.3 | Xác minh rằng các bài kiểm tra đánh giá đối kháng (ví dụ, các lệnh nhắc "nhiều lần" của Đội Đỏ) được thực hiện trước mỗi lần phát hành mô hình hoặc mẫu lời nhắc, kèm theo các ngưỡng tỷ lệ thành công và các cơ chế chặn tự động cho các trường hợp suy giảm hiệu suất. |   2   | D/V  |
| 2.1.4 | Xác minh rằng các câu lệnh xuất phát từ nội dung bên thứ ba (trang web, tệp PDF, email) được làm sạch trong một ngữ cảnh phân tích riêng biệt trước khi được nối vào câu lệnh chính.                                                                                     |   2   |  D   |
| 2.1.5 | Xác minh rằng tất cả các cập nhật quy tắc lọc prompt, các phiên bản mô hình phân loại và các thay đổi danh sách chặn đều được quản lý phiên bản và có thể kiểm tra được.                                                                                                 |   3   | D/V  |

---

## C2.2 Kháng lại Ví dụ Đối kháng

Mô hình Xử lý Ngôn ngữ Tự nhiên (NLP) vẫn dễ bị tổn thương bởi các biến động tinh vi ở cấp độ ký tự hoặc từ mà con người thường bỏ qua nhưng mô hình có xu hướng phân loại sai.

|   #   | Description                                                                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.2.1 | Xác minh rằng các bước chuẩn hóa đầu vào cơ bản (Unicode NFC, ánh xạ homoglyph, cắt khoảng trắng) được thực hiện trước khi phân tích từ.                                                                         |   1   |  D   |
| 2.2.2 | Xác minh rằng phát hiện dị thường thống kê đánh dấu các đầu vào có khoảng cách chỉnh sửa cao bất thường so với chuẩn ngôn ngữ, số lượng token lặp lại quá mức, hoặc khoảng cách nhúng bất thường.                |   2   | D/V  |
| 2.2.3 | Xác nhận rằng quy trình suy luận hỗ trợ các biến thể mô hình được gia cố bằng huấn luyện đối kháng tùy chọn hoặc các lớp phòng thủ (ví dụ, ngẫu nhiên hóa, chưng cất phòng thủ) cho các điểm cuối có rủi ro cao. |   2   |  D   |
| 2.2.4 | Xác minh rằng các đầu vào nghi ngờ là tấn công đối thủ được cách ly, ghi lại cùng với toàn bộ dữ liệu (sau khi đã loại bỏ thông tin cá nhân nhạy cảm).                                                           |   2   |  V   |
| 2.2.5 | Xác minh rằng các chỉ số độ bền (tỷ lệ thành công của các bộ công cụ tấn công đã biết) được theo dõi theo thời gian và các suy giảm hiệu suất gây ra việc chặn phát hành.                                        |   3   | D/V  |

---

## C2.3 Xác thực Lược đồ, Kiểu dữ liệu & Độ dài

Các cuộc tấn công AI sử dụng dữ liệu đầu vào bị lỗi định dạng hoặc quá cỡ có thể gây ra lỗi phân tích cú pháp, tràn dữ liệu trong các trường, và cạn kiệt tài nguyên. Việc thực thi nghiêm ngặt sơ đồ cấu trúc (schema) cũng là điều kiện tiên quyết khi thực hiện các cuộc gọi công cụ có tính xác định.

|   #   | Description                                                                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.3.1 | Xác minh rằng mọi điểm cuối gọi API hoặc hàm đều định nghĩa một schema đầu vào rõ ràng (JSON Schema, Protobuf hoặc tương đương đa mô hình) và rằng các đầu vào được kiểm tra hợp lệ trước khi tạo prompt. |   1   |  D   |
| 2.3.2 | Xác minh rằng các đầu vào vượt quá giới hạn tối đa về token hoặc byte đều bị từ chối với lỗi an toàn và không bao giờ bị cắt bớt một cách im lặng.                                                        |   1   | D/V  |
| 2.3.3 | Xác minh rằng các kiểm tra kiểu (ví dụ: phạm vi số, giá trị enum, loại MIME cho hình ảnh/âm thanh) được thực thi phía máy chủ, không chỉ trong mã phía khách.                                             |   2   | D/V  |
| 2.3.4 | Xác minh rằng các bộ kiểm tra ngữ nghĩa (ví dụ: JSON Schema) chạy trong thời gian không đổi để ngăn chặn tấn công từ chối dịch vụ thuật toán (DoS).                                                       |   2   |  D   |
| 2.3.5 | Xác minh rằng các lỗi xác thực được ghi lại với các đoạn tải trọng đã được che khuất và mã lỗi rõ ràng để hỗ trợ phân loại sự cố bảo mật.                                                                 |   3   |  V   |

---

## C2.4 Sàng lọc Nội dung & Chính sách

Các nhà phát triển nên có khả năng phát hiện các lời nhắc hợp lệ về mặt cú pháp nhưng yêu cầu nội dung bị cấm (chẳng hạn như hướng dẫn bất hợp pháp, ngôn ngữ thù địch và văn bản có bản quyền) và ngăn chặn chúng lan truyền.

|   #   | Description                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.4.1 | Xác minh rằng bộ phân loại nội dung (zero shot hoặc đã tinh chỉnh) chấm điểm từng đầu vào về các yếu tố bạo lực, tự làm hại bản thân, thù hận, nội dung tình dục và yêu cầu bất hợp pháp, với các ngưỡng có thể cấu hình được. |   1   |  D   |
| 2.4.2 | Xác minh rằng các đầu vào vi phạm chính sách sẽ nhận được phản hồi từ chối chuẩn hóa hoặc hoàn thành an toàn để chúng không lan truyền đến các cuộc gọi LLM tiếp theo.                                                         |   1   | D/V  |
| 2.4.3 | Xác nhận rằng mô hình sàng lọc hoặc bộ quy tắc được đào tạo lại/cập nhật ít nhất hàng quý, bao gồm các mẫu bỏ qua chính sách hoặc jailbreak mới được quan sát.                                                                 |   2   |  D   |
| 2.4.4 | Xác minh rằng việc sàng lọc tuân thủ các chính sách riêng của người dùng (độ tuổi, các hạn chế pháp lý theo vùng) thông qua các quy tắc dựa trên thuộc tính được giải quyết tại thời điểm yêu cầu.                             |   2   |  D   |
| 2.4.5 | Xác minh rằng nhật ký sàng lọc bao gồm điểm tin cậy của bộ phân loại và thẻ danh mục chính sách để tương quan SOC và phát lại nhóm đỏ trong tương lai.                                                                         |   3   |  V   |

---

## C2.5 Giới hạn tốc độ đầu vào & Ngăn chặn lạm dụng

Các nhà phát triển nên ngăn chặn việc lạm dụng, cạn kiệt tài nguyên và các cuộc tấn công tự động vào hệ thống AI bằng cách giới hạn tốc độ đầu vào và phát hiện các mẫu sử dụng bất thường.

|   #   | Description                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.5.1 | Xác minh rằng giới hạn tốc độ theo người dùng, theo địa chỉ IP và theo khóa API được thực thi cho tất cả các điểm đầu vào.                                    |   1   | D/V  |
| 2.5.2 | Xác minh rằng các giới hạn tốc độ đỉnh và duy trì được điều chỉnh để ngăn ngừa các cuộc tấn công từ chối dịch vụ (DoS) và tấn công dò mật khẩu (brute force). |   2   | D/V  |
| 2.5.3 | Xác minh rằng các mẫu sử dụng bất thường (ví dụ: yêu cầu liên tục nhanh, đầu vào tràn ngập) kích hoạt các chặn tự động hoặc tăng cấp.                         |   2   | D/V  |
| 2.5.4 | Xác minh rằng các bản ghi phòng chống lạm dụng được lưu giữ và xem xét để phát hiện các mô hình tấn công mới xuất hiện.                                       |   3   |  V   |

---

## C2.6 Xác thực đầu vào đa phương thức

Hệ thống AI nên bao gồm kiểm tra xác thực mạnh mẽ cho các đầu vào phi văn bản (hình ảnh, âm thanh, tệp tin) để ngăn chặn việc tiêm nhiễm, né tránh hoặc lạm dụng tài nguyên.

|   #   | Description                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.6.1 | Xác nhận rằng tất cả các đầu vào không phải văn bản (hình ảnh, âm thanh, tập tin) đều được kiểm tra về loại, kích thước và định dạng trước khi xử lý. |   1   |  D   |
| 2.6.2 | Xác minh rằng các tệp được quét để phát hiện phần mềm độc hại và tải payload ẩn (steganographic) trước khi nhập dữ liệu.                              |   2   | D/V  |
| 2.6.3 | Xác minh rằng các đầu vào hình ảnh / âm thanh được kiểm tra các nhiễu loạn gây đối kháng hoặc các mẫu tấn công đã biết.                               |   2   | D/V  |
| 2.6.4 | Xác minh rằng các lỗi xác thực đầu vào đa phương thức được ghi lại và kích hoạt cảnh báo để điều tra.                                                 |   3   |  V   |

---

## C2.7 Nguồn Gốc Dữ Liệu Đầu Vào & Ghi Công

Các hệ thống AI nên hỗ trợ kiểm toán, theo dõi lạm dụng và tuân thủ bằng cách giám sát và gắn thẻ nguồn gốc của tất cả các đầu vào của người dùng.

|   #   | Description                                                                                                                                                        | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 2.7.1 | Xác minh rằng tất cả các đầu vào của người dùng đều được gắn thẻ với siêu dữ liệu (ID người dùng, phiên làm việc, nguồn, dấu thời gian, địa chỉ IP) khi tiếp nhận. |   1   | D/V  |
| 2.7.2 | Xác minh rằng siêu dữ liệu nguồn gốc được giữ lại và có thể kiểm tra được cho tất cả các đầu vào đã xử lý.                                                         |   2   | D/V  |
| 2.7.3 | Xác minh rằng các nguồn đầu vào bất thường hoặc không tin cậy được đánh dấu và chịu sự kiểm tra nghiêm ngặt hơn hoặc bị chặn.                                      |   2   | D/V  |

---

## C2.8 Phát hiện mối đe dọa thích ứng theo thời gian thực

Các nhà phát triển nên sử dụng các hệ thống phát hiện mối đe dọa tiên tiến cho AI, có khả năng thích ứng với các mẫu tấn công mới và cung cấp bảo vệ thời gian thực với phương pháp so khớp mẫu biên dịch.

|   #   | Description                                                                                                                                                                                           | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.8.1 | Xác minh rằng các mẫu phát hiện mối đe dọa được biên dịch thành các bộ máy regex tối ưu hóa để lọc thời gian thực hiệu suất cao với tác động độ trễ tối thiểu.                                        |   1   | D/V  |
| 2.8.2 | Xác minh rằng các hệ thống phát hiện mối đe dọa duy trì các thư viện mẫu riêng biệt cho các loại mối đe dọa khác nhau (chèn lệnh gợi ý, nội dung gây hại, dữ liệu nhạy cảm, lệnh hệ thống).           |   1   | D/V  |
| 2.8.3 | Xác minh rằng việc phát hiện mối đe dọa thích ứng bao gồm các mô hình học máy cập nhật độ nhạy mối đe dọa dựa trên tần suất và tỷ lệ thành công của các cuộc tấn công.                                |   2   | D/V  |
| 2.8.4 | Xác minh rằng các nguồn dữ liệu thông tin tình báo mối đe dọa theo thời gian thực tự động cập nhật thư viện mẫu với các chữ ký tấn công và các Chỉ báo Xâm nhập (IOCs) mới.                           |   2   | D/V  |
| 2.8.5 | Xác minh rằng tỷ lệ dương tính giả trong phát hiện mối đe dọa được theo dõi liên tục và tính đặc hiệu của mẫu được tự động điều chỉnh để giảm thiểu sự cản trở trong các trường hợp sử dụng hợp pháp. |   3   | D/V  |
| 2.8.6 | Xác minh rằng phân tích mối đe dọa theo ngữ cảnh xem xét nguồn đầu vào, các mẫu hành vi người dùng và lịch sử phiên để cải thiện độ chính xác trong việc phát hiện.                                   |   3   | D/V  |
| 2.8.7 | Xác nhận rằng các chỉ số hiệu suất phát hiện mối đe dọa (tỷ lệ phát hiện, độ trễ xử lý, sử dụng tài nguyên) được giám sát và tối ưu hóa theo thời gian thực.                                          |   3   | D/V  |

---

## C2.9 Quy trình xác thực bảo mật đa phương thức

Các nhà phát triển nên cung cấp xác thực bảo mật cho văn bản, hình ảnh, âm thanh và các loại đầu vào AI khác với các loại phát hiện mối đe dọa cụ thể và cách ly tài nguyên.

|   #   | Description                                                                                                                                                                                                                                  | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 2.9.1 | Xác minh rằng mỗi phương thức đầu vào đều có các bộ kiểm tra bảo mật chuyên dụng với các mẫu mối đe dọa được tài liệu hóa (văn bản: tiêm lệnh nhắc, hình ảnh: ẩn hình, âm thanh: tấn công phổ tần) và các ngưỡng phát hiện.                  |   1   | D/V  |
| 2.9.2 | Xác minh rằng các đầu vào đa phương thức được xử lý trong các vùng cách ly riêng biệt với giới hạn tài nguyên xác định (bộ nhớ, CPU, thời gian xử lý) cụ thể cho từng loại phương thức và được ghi chép trong các chính sách bảo mật.        |   2   | D/V  |
| 2.9.3 | Xác minh rằng phát hiện tấn công đa phương thức có thể nhận diện các cuộc tấn công phối hợp trên nhiều loại đầu vào khác nhau (ví dụ, payload ẩn trong ảnh kết hợp với chèn lệnh trong văn bản) bằng các quy tắc tương quan và tạo cảnh báo. |   2   | D/V  |
| 2.9.4 | Xác minh rằng các lỗi xác thực đa phương thức kích hoạt ghi nhật ký chi tiết bao gồm tất cả các phương thức đầu vào, kết quả xác thực, điểm mối đe dọa và phân tích tương quan với định dạng nhật ký có cấu trúc để tích hợp SIEM.           |   3   | D/V  |
| 2.9.5 | Xác minh rằng các bộ phân loại nội dung theo loại phương thức đã được cập nhật theo lịch trình đã được ghi lại (ít nhất hàng quý) với các mẫu mối đe dọa mới, ví dụ đối kháng, và các chuẩn hiệu suất duy trì trên ngưỡng cơ bản.            |   3   | D/V  |

---

## Tài liệu tham khảo

* [LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)
* [Generative AI's Biggest Security Flaw Is Not Easy to Fix](https://www.wired.com/story/generative-ai-prompt-injection-hacking)
* [Many-shot jailbreaking \ Anthropic](https://www.anthropic.com/research/many-shot-jailbreaking)
* [$PDF$ OpenAI GPT-4.5 System Card](https://cdn.openai.com/gpt-4-5-system-card-2272025.pdf)
* [Notebook for the CheckThat Lab at CLEF 2024](https://ceur-ws.org/Vol-3740/paper-53.pdf)
* [Mitigate jailbreaks and prompt injections – Anthropic](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/mitigate-jailbreaks)
* [Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis](https://ama.drwhy.ai/mitre-attck.html)
* [OWASP Top 10 for LLM Applications 2025 – WorldTech IT](https://wtit.com/blog/2025/04/17/owasp-top-10-for-llm-applications-2025/)
* [OWASP Machine Learning Security Top Ten](https://owasp.org/www-project-machine-learning-security-top-10/)
* [Few words about AI Security – Jussi Metso](https://www.jussimetso.com/index.php/2024/09/28/few-words-about-ai-security/)
* [How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry](https://modelmetry.com/blog/how-to-ensure-llm-output-adheres-to-a-json-schema)
* [Easily enforcing valid JSON schema following – API](https://community.openai.com/t/feature-request-function-calling-easily-enforcing-valid-json-schema-following/263515?utm_source)
* [AI Safety + Cybersecurity R\&D Tracker – Fairly AI](https://www.fairly.ai/blog/ai-cybersecurity-tracker)
* [Anthropic makes 'jailbreak' advance to stop AI models producing harmful results](https://www.ft.com/content/cf11ebd8-aa0b-4ed4-945b-a5d4401d186e)
* [Pattern matching filter rules - IBM](https://www.ibm.com/docs/ssw_aix_71/security/intrusion_pattern_matching_filter_rules.html)
* [Real-time Threat Detection](https://www.darktrace.com/cyber-ai-glossary/real-time-threat-detection)


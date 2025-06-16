# Bảo mật Bộ nhớ C8, Nhúng và Cơ sở dữ liệu Vector

## Mục tiêu Kiểm soát

Lưu trữ vector và embeddings đóng vai trò như "bộ nhớ trực tiếp" của các hệ thống AI hiện đại, liên tục tiếp nhận dữ liệu do người dùng cung cấp và đưa lại dữ liệu đó vào các ngữ cảnh mô hình thông qua Kết hợp Truy xuất và Tạo nội dung (Retrieval-Augmented Generation - RAG). Nếu không được kiểm soát, bộ nhớ này có thể làm rò rỉ thông tin cá nhân nhận dạng được (PII), vi phạm sự đồng ý hoặc bị đảo ngược để tái tạo văn bản gốc. Mục tiêu của nhóm biện pháp kiểm soát này là tăng cường các kênh bộ nhớ và cơ sở dữ liệu vector sao cho việc truy cập tuân theo nguyên tắc ít đặc quyền nhất, embeddings bảo vệ quyền riêng tư, các vector lưu trữ có thời hạn hoặc có thể bị thu hồi khi cần, và bộ nhớ riêng của từng người dùng không bao giờ làm nhiễm bẩn các yêu cầu hay kết quả của người dùng khác.

---

## C8.1 Kiểm soát truy cập trên bộ nhớ và chỉ mục RAG

Thực thi các kiểm soát truy cập chi tiết trên mọi bộ sưu tập vector.

|   #   | Description                                                                                                                                                                     | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.1.1 | Xác minh rằng các quy tắc kiểm soát truy cập ở mức dòng/namespace giới hạn các thao tác chèn, xóa và truy vấn theo từng tenant, bộ sưu tập, hoặc nhãn tài liệu.                 |   1   | D/V  |
| 8.1.2 | Xác minh rằng các khóa API hoặc JWT có chứa các quyền hạn phạm vi (ví dụ: ID bộ sưu tập, động từ hành động) và được thay đổi ít nhất hàng quý.                                  |   1   | D/V  |
| 8.1.3 | Xác minh rằng các nỗ lực leo thang đặc quyền (ví dụ: truy vấn tương đồng chéo không gian tên) được phát hiện và ghi lại vào SIEM trong vòng 5 phút.                             |   2   | D/V  |
| 8.1.4 | Xác minh rằng cơ sở dữ liệu vector (vector DB) ghi lại nhật ký với các thông tin về định danh chủ thể, thao tác, ID/không gian tên vector, ngưỡng tương tự và số lượng kết quả. |   2   | D/V  |
| 8.1.5 | Xác minh rằng các quyết định truy cập được kiểm tra lỗi vượt qua mỗi khi bộ máy được nâng cấp hoặc quy tắc phân mảnh chỉ mục thay đổi.                                          |   3   |  V   |

---

## C8.2 Tiêu chuẩn hóa và Xác thực Nhúng

Tiền xử lý văn bản để phát hiện thông tin nhận dạng cá nhân (PII), thực hiện che giấu hoặc ẩn danh trước khi biến đổi thành vector, và tùy chọn xử lý sau các embedding để loại bỏ tín hiệu dư thừa.

|   #   | Description                                                                                                                                                                                                                            | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.2.1 | Xác minh rằng dữ liệu nhận dạng cá nhân (PII) và dữ liệu được điều chỉnh được phát hiện thông qua bộ phân loại tự động và được che mờ, mã token hoặc loại bỏ trước khi nhúng.                                                          |   1   | D/V  |
| 8.2.2 | Xác nhận rằng các quy trình nhúng từ chối hoặc cách ly các đầu vào chứa mã thực thi hoặc các ký tự không phải UTF-8 có thể làm độc danh mục.                                                                                           |   1   |  D   |
| 8.2.3 | Xác minh rằng việc làm sạch dữ liệu theo nguyên tắc riêng tư vi phân cục bộ hoặc chuẩn được áp dụng cho các nhúng câu có khoảng cách đến bất kỳ token Dữ liệu Nhận dạng Cá nhân (PII) nào đã biết nhỏ hơn ngưỡng có thể cấu hình được. |   2   | D/V  |
| 8.2.4 | Xác nhận rằng hiệu quả làm sạch dữ liệu (ví dụ: độ thu hồi của việc che mờ thông tin nhận dạng cá nhân, sự trôi nghĩa ngữ cảnh) được kiểm tra ít nhất nửa năm một lần dựa trên các bộ dữ liệu chuẩn.                                   |   2   |  V   |
| 8.2.5 | Xác minh rằng các cấu hình làm sạch được quản lý phiên bản và các thay đổi phải trải qua quá trình kiểm tra của đồng nghiệp.                                                                                                           |   3   | D/V  |

---

## C8.3 Hết hạn bộ nhớ, Thu hồi & Xóa bỏ

Quyền "được quên" theo GDPR và các luật tương tự yêu cầu việc xóa dữ liệu kịp thời; do đó, các kho vector phải hỗ trợ TTL (thời gian tồn tại), xóa cứng và đánh dấu xóa để các vector bị thu hồi không thể được phục hồi hoặc lập chỉ mục lại.

|   #   | Description                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.3.1 | Xác minh rằng mỗi vector và bản ghi siêu dữ liệu đều có thời gian sống (TTL) hoặc nhãn lưu giữ rõ ràng được các công việc dọn dẹp tự động tuân thủ.                           |   1   | D/V  |
| 8.3.2 | Xác nhận rằng các yêu cầu xóa do người dùng khởi tạo sẽ loại bỏ vectơ, siêu dữ liệu, bản sao bộ nhớ đệm và các chỉ mục dẫn xuất trong vòng 30 ngày.                           |   1   | D/V  |
| 8.3.3 | Xác minh rằng việc xóa logic được thực hiện sau đó bằng phương pháp xóa dữ liệu mã hóa của các khối lưu trữ nếu phần cứng hỗ trợ, hoặc bằng cách phá hủy khóa trong kho khóa. |   2   |  D   |
| 8.3.4 | Xác minh rằng các vector hết hạn bị loại trừ khỏi kết quả tìm kiếm gần nhất trong vòng < 500 ms sau khi hết hạn.                                                              |   3   | D/V  |

---

## C8.4 Ngăn chặn Đảo ngược và Rò rỉ Embedding

Các biện pháp phòng thủ gần đây—ghép chồng nhiễu, mạng chiếu, làm nhiễu neuron bảo mật và mã hóa tầng ứng dụng—có thể giảm tỷ lệ đảo ngược cấp token xuống dưới 5%.

|   #   | Description                                                                                                                                               | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.4.1 | Xác minh rằng một mô hình đe dọa chính thức bao gồm các cuộc tấn công đảo ngược, thành viên và suy đoán thuộc tính tồn tại và được xem xét hàng năm.      |   1   |  V   |
| 8.4.2 | Xác minh rằng mã hóa lớp ứng dụng hoặc mã hóa có thể tìm kiếm bảo vệ các vector khỏi việc đọc trực tiếp bởi quản trị viên hạ tầng hoặc nhân viên đám mây. |   2   | D/V  |
| 8.4.3 | Xác minh các tham số phòng thủ (ε cho DP, độ ồn σ, hạng chiếu k) cân bằng giữa bảo mật ≥ 99% bảo vệ token và tiện ích ≤ 3% mất mát độ chính xác.          |   3   |  V   |
| 8.4.4 | Xác minh rằng các chỉ số độ bền đảo ngược là một phần của các cổng phát hành cho các bản cập nhật mô hình, với ngân sách hồi quy được định nghĩa.         |   3   | D/V  |

---

## C8.5 Thi hành phạm vi cho bộ nhớ theo người dùng cụ thể

Rò rỉ giữa các tenant vẫn là rủi ro hàng đầu của RAG: các truy vấn tương đồng lọc không đúng có thể hiển thị tài liệu riêng tư của khách hàng khác.

|   #   | Description                                                                                                                                                         | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.5.1 | Xác minh rằng mọi truy vấn truy xuất đều được lọc sau theo ID người thuê/người dùng trước khi được chuyển tới lời nhắc LLM.                                         |   1   | D/V  |
| 8.5.2 | Xác minh rằng tên bộ sưu tập hoặc ID có không gian tên được thêm muối theo từng người dùng hoặc khách thuê để các vector không bị trùng lặp giữa các phạm vi.       |   1   |  D   |
| 8.5.3 | Xác minh rằng các kết quả tương đồng vượt quá ngưỡng khoảng cách có thể cấu hình nhưng nằm ngoài phạm vi của người gọi sẽ bị loại bỏ và kích hoạt cảnh báo bảo mật. |   2   | D/V  |
| 8.5.4 | Xác minh rằng các bài kiểm tra tải đa người thuê giả lập các truy vấn đối kháng cố gắng truy xuất tài liệu ngoài phạm vi và chứng minh không rò rỉ dữ liệu.         |   2   |  V   |
| 8.5.5 | Xác minh rằng các khóa mã hóa được phân tách theo từng người thuê, đảm bảo sự cô lập mật mã ngay cả khi lưu trữ vật lý được chia sẻ.                                |   3   | D/V  |

---

## C8.6 An ninh Hệ thống Bộ nhớ Tiên tiến

Các kiểm soát bảo mật cho các kiến trúc bộ nhớ tinh vi bao gồm bộ nhớ theo tập sự kiện (episodic), bộ nhớ ngữ nghĩa (semantic) và bộ nhớ làm việc (working memory) với các yêu cầu cách ly và xác thực cụ thể.

|   #   | Description                                                                                                                                                                                                                                                                             | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 8.6.1 | Xác minh rằng các loại bộ nhớ khác nhau (bộ nhớ theo tập, bộ nhớ ngữ nghĩa, bộ nhớ làm việc) có các ngữ cảnh bảo mật riêng biệt với kiểm soát truy cập dựa trên vai trò, khóa mã hóa riêng biệt và các mô hình truy cập được tài liệu hóa cho từng loại bộ nhớ.                         |   1   | D/V  |
| 8.6.2 | Xác nhận rằng quy trình củng cố bộ nhớ bao gồm việc kiểm tra bảo mật để ngăn chặn việc chèn các ký ức độc hại thông qua việc làm sạch nội dung, xác minh nguồn và kiểm tra tính toàn vẹn trước khi lưu trữ.                                                                             |   2   | D/V  |
| 8.6.3 | Xác minh rằng các truy vấn truy xuất bộ nhớ được kiểm tra và làm sạch để ngăn chặn việc khai thác thông tin không được phép thông qua phân tích mẫu truy vấn, thực thi kiểm soát truy cập và lọc kết quả.                                                                               |   2   | D/V  |
| 8.6.4 | Xác minh rằng các cơ chế quên bộ nhớ xóa dữ liệu nhạy cảm một cách an toàn với các đảm bảo xóa mật mã bằng cách xóa khóa, ghi đè nhiều lần hoặc xóa an toàn dựa trên phần cứng kèm theo chứng nhận xác minh.                                                                            |   3   | D/V  |
| 8.6.5 | Xác minh rằng tính toàn vẹn của hệ thống bộ nhớ được giám sát liên tục để phát hiện các sửa đổi hoặc hư hỏng trái phép thông qua các hàm băm kiểm tra (checksums), nhật ký kiểm toán (audit logs) và cảnh báo tự động khi nội dung bộ nhớ thay đổi ngoài phạm vi hoạt động bình thường. |   3   | D/V  |

---

## Tài liệu tham khảo

* [Vector database security: Pinecone – IronCore Labs](https://ironcorelabs.com/vectordbs/pinecone-security/)
* [Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera](https://privacera.com/blog/securing-the-backbone-of-ai-safeguarding-vector-databases-and-embeddings/)
* [Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances](https://ai.gopubby.com/enhancing-data-security-with-role-based-access-control-of-qdrant-vector-database-3878769bec83)
* [Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv](https://arxiv.org/html/2411.05034v1)
* [DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview](https://openreview.net/forum?id=DF5TVzpTW0)
* [Art. 17 GDPR – Right to Erasure](https://gdpr-info.eu/art-17-gdpr/)
* [Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai](https://www.tonic.ai/blog/sensitive-data-in-text-embeddings-is-recoverable)
* [PII Identification and Removal – NVIDIA NeMo Docs](https://docs.nvidia.com/nemo-framework/user-guide/latest/datacuration/personalidentifiableinformationidentificationandremoval.html)
* [De-identifying Sensitive Data – Google Cloud DLP](https://cloud.google.com/sensitive-data-protection/docs/deidentify-sensitive-data)
* [Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails-sensitive-filters.html)
* [Think Your RAG Is Secure? Think Again – Medium](https://medium.com/%40vijay.poudel1/think-your-rag-is-secure-think-again-heres-how-to-actually-lock-it-down-c4c30e3864e7)
* [Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/secure-multitenant-rag)
* [Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog](https://milvus.io/blog/build-multi-tenancy-rag-with-milvus-best-practices-part-one.md)


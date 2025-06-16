# Phụ lục D: Quản trị và Xác minh Mã hóa An toàn Hỗ trợ bởi AI

## Mục tiêu

Chương này xác định các kiểm soát tổ chức cơ bản để sử dụng an toàn và hiệu quả các công cụ mã hóa hỗ trợ AI trong quá trình phát triển phần mềm, đảm bảo an ninh và khả năng truy xuất trong suốt vòng đời phát triển phần mềm (SDLC).

---

## AD.1 Quy trình lập trình bảo mật được hỗ trợ bởi AI

Tích hợp công cụ AI vào vòng đời phát triển phần mềm an toàn (SSDLC) của tổ chức mà không làm suy yếu các cổng bảo mật hiện có.

|   #    | Description                                                                                                                                                                      | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.1.1 | Xác minh rằng quy trình làm việc đã được ghi chép mô tả khi nào và cách thức các công cụ AI có thể tạo ra, tái cấu trúc hoặc xem xét mã nguồn.                                   |   1   | D/V  |
| AD.1.2 | Xác minh rằng quy trình làm việc tương ứng với từng giai đoạn của SSDLC (thiết kế, triển khai, rà soát mã, kiểm thử, triển khai).                                                |   2   |  D   |
| AD.1.3 | Xác minh rằng các chỉ số (ví dụ, mật độ lỗ hổng, thời gian trung bình để phát hiện) được thu thập trên mã do AI tạo ra và được so sánh với các nền tảng chỉ do con người tạo ra. |   3   | D/V  |

---

## AD.2 Đánh giá Công cụ AI & Mô hình hóa Mối đe dọa

Đảm bảo các công cụ mã hóa AI được đánh giá về khả năng bảo mật, rủi ro và tác động chuỗi cung ứng trước khi áp dụng.

|   #    | Description                                                                                                                                                           | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.2.1 | Xác minh rằng mô hình mối đe dọa cho mỗi công cụ AI xác định được các rủi ro về sử dụng sai mục đích, đảo ngược mô hình, rò rỉ dữ liệu và chuỗi phụ thuộc.            |   1   | D/V  |
| AD.2.2 | Xác minh rằng các đánh giá công cụ bao gồm phân tích tĩnh/động của bất kỳ thành phần cục bộ nào và đánh giá các điểm cuối SaaS (TLS, xác thực/ủy quyền, ghi nhật ký). |   2   |  D   |
| AD.2.3 | Xác minh rằng các đánh giá tuân theo một khung công tác được công nhận và được thực hiện lại sau các thay đổi phiên bản lớn.                                          |   3   | D/V  |

---

## AD.3 Quản lý Bảo mật Lời nhắc và Ngữ cảnh

Ngăn ngừa rò rỉ bí mật, mã nguồn độc quyền và dữ liệu cá nhân khi xây dựng các lời nhắc hoặc ngữ cảnh cho mô hình AI.

|   #    | Description                                                                                                                                                             | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.3.1 | Xác nhận rằng hướng dẫn bằng văn bản nghiêm cấm việc gửi thông tin bí mật, thông tin đăng nhập hoặc dữ liệu mật trong các câu nhắc.                                     |   1   | D/V  |
| AD.3.2 | Xác minh rằng các biện pháp kiểm soát kỹ thuật (lọc bối cảnh được phê duyệt, xóa nội dung phía khách hàng) tự động loại bỏ các thông tin nhạy cảm.                      |   2   |  D   |
| AD.3.3 | Xác minh rằng các prompt và phản hồi được phân tách token, mã hóa trong quá trình truyền và lưu trữ, đồng thời thời gian lưu trữ tuân thủ chính sách phân loại dữ liệu. |   3   | D/V  |

---

## AD.4 Xác thực mã do AI tạo ra

Phát hiện và khắc phục các lỗ hổng bảo mật do kết quả đầu ra của AI gây ra trước khi mã được hợp nhất hoặc triển khai.

|   #    | Description                                                                                                                                                                | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.4.1 | Xác nhận rằng mã do AI tạo ra luôn được kiểm tra bởi con người.                                                                                                            |   1   | D/V  |
| AD.4.2 | Xác minh rằng các trình quét tự động (SAST/IAST/DAST) được chạy trên mọi pull request chứa mã do AI tạo và chặn việc gộp nếu phát hiện các lỗi nghiêm trọng.               |   2   |  D   |
| AD.4.3 | Xác minh rằng việc kiểm thử ngẫu nhiên phân biệt hoặc kiểm thử dựa trên thuộc tính chứng minh các hành vi quan trọng về bảo mật (ví dụ: xác thực đầu vào, logic ủy quyền). |   3   | D/V  |

---

## AD.5 Khả năng giải thích và truy xuất nguồn gốc của các gợi ý mã nguồn

Cung cấp cho kiểm toán viên và nhà phát triển cái nhìn sâu sắc về lý do tại sao một đề xuất được đưa ra và cách nó phát triển như thế nào.

|   #    | Description                                                                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.5.1 | Xác minh rằng các cặp câu lệnh/phản hồi được ghi lại cùng với các ID cam kết.                                                                                                                      |   1   | D/V  |
| AD.5.2 | Xác nhận rằng các nhà phát triển có thể hiển thị các trích dẫn mô hình (đoạn trích đào tạo, tài liệu) hỗ trợ một đề xuất.                                                                          |   2   |  D   |
| AD.5.3 | Xác minh rằng các báo cáo giải thích được lưu trữ cùng với hiện vật thiết kế và được tham chiếu trong các đánh giá bảo mật, đảm bảo tuân thủ các nguyên tắc truy xuất nguồn gốc của ISO/IEC 42001. |   3   | D/V  |

---

## AD.6 Phản hồi liên tục & Tinh chỉnh mô hình

Cải thiện hiệu suất bảo mật mô hình theo thời gian trong khi ngăn chặn sự trượt tiêu cực.

|   #    | Description                                                                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| AD.6.1 | Xác nhận rằng các nhà phát triển có thể đánh dấu các đề xuất không an toàn hoặc không tuân thủ, và các đánh dấu này được theo dõi.                                                                 |   1   | D/V  |
| AD.6.2 | Xác nhận rằng phản hồi tổng hợp được sử dụng để điều chỉnh tinh chỉnh định kỳ hoặc tạo ra nội dung tăng cường truy xuất với các tập hợp mã hóa bảo mật đã được kiểm duyệt (ví dụ: Bảng mẹo OWASP). |   2   |  D   |
| AD.6.3 | Xác minh rằng bộ công cụ đánh giá vòng kín chạy các bài kiểm tra hồi quy sau mỗi lần tinh chỉnh; các chỉ số bảo mật phải đạt hoặc vượt mức chuẩn trước đó trước khi triển khai.                    |   3   | D/V  |

---

### Tài liệu tham khảo

* [NIST AI Risk Management Framework 1.0](https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf)
* [ISO/IEC 42001:2023 — AI Management Systems Requirements](https://www.iso.org/standard/81230.html)
* [OWASP Secure Coding Practices — Quick Reference Guide](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)


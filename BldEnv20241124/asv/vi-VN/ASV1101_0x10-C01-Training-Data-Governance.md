# Quản trị Dữ liệu Đào tạo C1 & Quản lý Định kiến

## Mục tiêu Kiểm soát

Dữ liệu đào tạo phải được thu thập, xử lý và duy trì theo cách bảo toàn nguồn gốc, bảo mật, chất lượng và tính công bằng. Thực hiện như vậy sẽ đáp ứng các nghĩa vụ pháp lý và giảm thiểu rủi ro thiên vị, đầu độc hoặc vi phạm quyền riêng tư trong suốt vòng đời của trí tuệ nhân tạo.

---

## C1.1 Nguồn gốc dữ liệu đào tạo

Duy trì một kho dữ liệu có thể xác minh được tất cả các tập dữ liệu, chỉ chấp nhận các nguồn tin cậy và ghi lại mọi thay đổi để có thể kiểm tra.

|   #   | Description                                                                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.1.1 | Xác minh rằng một danh mục cập nhật về mọi nguồn dữ liệu huấn luyện (nguồn gốc, người quản lý/chủ sở hữu, giấy phép, phương pháp thu thập, các ràng buộc về mục đích sử dụng, và lịch sử xử lý) được duy trì.                                            |   1   | D/V  |
| 1.1.2 | Xác minh rằng chỉ những bộ dữ liệu đã được kiểm định về chất lượng, tính đại diện, nguồn gốc đạo đức và tuân thủ giấy phép mới được phép sử dụng, giảm thiểu rủi ro về nhiễm độc dữ liệu, thiên vị ngầm và vi phạm sở hữu trí tuệ.                       |   1   | D/V  |
| 1.1.3 | Xác minh rằng việc giảm thiểu dữ liệu được thực thi để loại bỏ các thuộc tính không cần thiết hoặc nhạy cảm.                                                                                                                                             |   1   | D/V  |
| 1.1.4 | Xác minh rằng tất cả các thay đổi dữ liệu đều phải tuân theo quy trình phê duyệt có ghi nhật ký.                                                                                                                                                         |   2   | D/V  |
| 1.1.5 | Xác minh rằng chất lượng gán nhãn/chuẩn đoán được đảm bảo thông qua việc kiểm tra chéo hoặc đồng thuận của người đánh giá.                                                                                                                               |   2   | D/V  |
| 1.1.6 | Xác minh rằng "thẻ dữ liệu" hoặc "bảng thông tin dữ liệu cho bộ dữ liệu" được duy trì cho các bộ dữ liệu huấn luyện quan trọng, chi tiết các đặc điểm, động cơ, thành phần, quy trình thu thập, tiền xử lý và các khuyến nghị/sử dụng không nên áp dụng. |   2   | D/V  |

---

## C1.2 An toàn và Toàn vẹn Dữ liệu Đào tạo

Hạn chế truy cập, mã hóa dữ liệu khi lưu trữ và truyền tải, và xác thực tính toàn vẹn để ngăn chặn việc giả mạo hoặc đánh cắp.

|   #   | Description                                                                                                                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.2.1 | Xác minh rằng các kiểm soát truy cập bảo vệ lưu trữ và các pipeline.                                                                                                                                                                                                                                     |   1   | D/V  |
| 1.2.2 | Xác minh rằng các bộ dữ liệu được mã hóa khi truyền và, đối với tất cả thông tin nhạy cảm hoặc thông tin cá nhân có thể nhận dạng được (PII), được mã hóa khi lưu trữ, sử dụng các thuật toán mã hóa tiêu chuẩn ngành và các thực hành quản lý khóa.                                                     |   2   | D/V  |
| 1.2.3 | Xác minh rằng các hàm băm mật mã hoặc chữ ký số được sử dụng để đảm bảo tính toàn vẹn dữ liệu trong quá trình lưu trữ và truyền tải, và các kỹ thuật phát hiện bất thường tự động được áp dụng để ngăn chặn các sửa đổi trái phép hoặc hỏng dữ liệu, bao gồm cả các cố gắng đầu độc dữ liệu có mục tiêu. |   2   | D/V  |
| 1.2.4 | Xác minh rằng các phiên bản bộ dữ liệu được theo dõi để cho phép quay lại.                                                                                                                                                                                                                               |   3   | D/V  |
| 1.2.5 | Xác nhận rằng dữ liệu lỗi thời được xóa hoặc ẩn danh một cách an toàn phù hợp với chính sách lưu giữ dữ liệu, các yêu cầu pháp lý và để giảm thiểu bề mặt tấn công.                                                                                                                                      |   2   | D/V  |

---

## C1.3 Độ đầy đủ và Công bằng của Biểu diễn

Phát hiện sai lệch về nhân khẩu học và áp dụng các biện pháp giảm thiểu để tỷ lệ lỗi của mô hình được công bằng giữa các nhóm.

|   #   | Description                                                                                                                                                                                                                                                                                                                                                                       | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.3.1 | Xác minh rằng các bộ dữ liệu được phân tích hồ sơ để phát hiện sự mất cân bằng đại diện và các thiên vị tiềm ẩn đối với các thuộc tính được pháp luật bảo vệ (ví dụ: chủng tộc, giới tính, tuổi tác) và các đặc điểm nhạy cảm về mặt đạo đức khác liên quan đến lĩnh vực ứng dụng của mô hình (ví dụ: tình trạng kinh tế xã hội, vị trí địa lý).                                  |   1   | D/V  |
| 1.3.2 | Xác nhận rằng các thiên vị đã được xác định được giảm thiểu thông qua các chiến lược đã được ghi chép như cân bằng lại, tăng cường dữ liệu có mục tiêu, điều chỉnh thuật toán (ví dụ: các kỹ thuật tiền xử lý, xử lý trong quá trình, xử lý hậu kỳ), hoặc tái cân trọng số, và đánh giá tác động của việc giảm thiểu đối với cả tính công bằng và hiệu suất tổng thể của mô hình. |   2   | D/V  |
| 1.3.3 | Xác nhận rằng các chỉ số công bằng sau đào tạo được đánh giá và ghi chép lại.                                                                                                                                                                                                                                                                                                     |   2   | D/V  |
| 1.3.4 | Xác minh rằng chính sách quản lý sai lệch theo vòng đời phân công người chịu trách nhiệm và tần suất rà soát.                                                                                                                                                                                                                                                                     |   3   | D/V  |

---

## C1.4 Chất lượng, tính toàn vẹn và bảo mật của nhãn dữ liệu huấn luyện

Bảo vệ nhãn bằng mã hóa và yêu cầu đánh giá kép cho các lớp quan trọng.

|   #   | Description                                                                                                                                                                                                                                                   | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.4.1 | Xác minh rằng chất lượng gán nhãn/chú thích được đảm bảo thông qua các hướng dẫn rõ ràng, kiểm tra chéo của người đánh giá, cơ chế đồng thuận (ví dụ: theo dõi sự đồng thuận giữa các người chú thích), và các quy trình xác định để giải quyết sự khác biệt. |   2   | D/V  |
| 1.4.2 | Xác minh rằng các hàm băm mật mã hoặc chữ ký số được áp dụng cho các artifact nhãn để đảm bảo tính toàn vẹn và xác thực của chúng.                                                                                                                            |   2   | D/V  |
| 1.4.3 | Xác minh rằng các giao diện và nền tảng dán nhãn thực thi kiểm soát truy cập chặt chẽ, duy trì nhật ký kiểm tra có khả năng phát hiện sự giả mạo đối với tất cả các hoạt động dán nhãn, và bảo vệ chống lại các sửa đổi trái phép.                            |   2   | D/V  |
| 1.4.4 | Xác minh rằng các nhãn quan trọng đối với an toàn, bảo mật hoặc sự công bằng (ví dụ: nhận diện nội dung độc hại, phát hiện y tế quan trọng) được thực hiện kiểm duyệt độc lập bắt buộc bởi hai người hoặc có phương pháp xác minh mạnh tương đương.           |   3   | D/V  |
| 1.4.5 | Xác minh rằng thông tin nhạy cảm (bao gồm dữ liệu cá nhân nhận dạng được - PII) vô tình được ghi lại hoặc bắt buộc phải có trong nhãn được biên tập, giả danh, ẩn danh hoặc mã hóa khi lưu trữ và truyền tải, theo các nguyên tắc giảm thiểu dữ liệu.         |   2   | D/V  |
| 1.4.6 | Xác minh rằng các hướng dẫn và chỉ dẫn ghi nhãn đầy đủ, được kiểm soát phiên bản và được đồng nghiệp xem xét.                                                                                                                                                 |   2   | D/V  |
| 1.4.7 | Xác minh rằng các sơ đồ dữ liệu (bao gồm cả nhãn) được định nghĩa rõ ràng và có kiểm soát phiên bản.                                                                                                                                                          |   2   | D/V  |
| 1.8.2 | Xác minh rằng các quy trình làm việc gán nhãn thuê ngoài hoặc sử dụng nguồn lực đám đông bao gồm các biện pháp kỹ thuật/thủ tục để đảm bảo tính bảo mật, tính toàn vẹn của dữ liệu, chất lượng nhãn và ngăn ngừa rò rỉ dữ liệu.                               |   2   | D/V  |

---

## C1.5 Đảm bảo Chất lượng Dữ liệu Đào tạo

Kết hợp xác thực tự động, kiểm tra ngẫu nhiên thủ công và khắc phục ghi nhật ký để đảm bảo độ tin cậy của bộ dữ liệu.

|   #   | Description                                                                                                                                                                                                                                                                    | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.5.1 | Xác minh rằng các bài kiểm tra tự động phát hiện lỗi định dạng, giá trị null và lệch nhãn trong mỗi lần nhập liệu hoặc chuyển đổi quan trọng.                                                                                                                                  |   1   |  D   |
| 1.5.2 | Xác minh rằng các bộ dữ liệu bị lỗi được cách ly cùng với các dấu vết kiểm tra.                                                                                                                                                                                                |   1   | D/V  |
| 1.5.3 | Xác minh rằng các kiểm tra thủ công ngẫu nhiên do chuyên gia lĩnh vực thực hiện bao phủ một mẫu có ý nghĩa thống kê (ví dụ, ≥1% hoặc 1.000 mẫu, tùy theo giá trị nào lớn hơn, hoặc theo đánh giá rủi ro) để phát hiện các vấn đề chất lượng tinh vi mà tự động không bắt được. |   2   |  V   |
| 1.5.4 | Xác minh rằng các bước khắc phục được đính kèm vào các bản ghi nguồn gốc.                                                                                                                                                                                                      |   2   | D/V  |
| 1.5.5 | Xác minh rằng các cổng kiểm soát chất lượng ngăn chặn bộ dữ liệu kém chất lượng trừ khi có sự chấp thuận ngoại lệ.                                                                                                                                                             |   2   | D/V  |

---

## C1.6 Phát hiện Đầu độc Dữ liệu

Áp dụng phát hiện bất thường thống kê và quy trình cách ly để ngăn chặn các chèn ép đối nghịch.

|   #   | Description                                                                                                                                                                                                                                                                               | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.6.1 | Xác minh rằng các kỹ thuật phát hiện dị thường (ví dụ: phương pháp thống kê, phát hiện điểm ngoại lai, phân tích embedding) được áp dụng cho dữ liệu đào tạo khi nhập liệu và trước các lần đào tạo chính để xác định các cuộc tấn công đầu độc tiềm ẩn hoặc sự hỏng dữ liệu không chủ ý. |   2   | D/V  |
| 1.6.2 | Xác minh rằng các mẫu bị đánh dấu kích hoạt việc xem xét thủ công trước khi đào tạo.                                                                                                                                                                                                      |   2   | D/V  |
| 1.6.3 | Xác minh rằng kết quả được đưa vào hồ sơ bảo mật của mô hình và cung cấp thông tin cho tình báo mối đe dọa đang diễn ra.                                                                                                                                                                  |   2   |  V   |
| 1.6.4 | Xác minh rằng logic phát hiện được làm mới với thông tin tình báo mối đe dọa mới.                                                                                                                                                                                                         |   3   | D/V  |
| 1.6.5 | Xác nhận rằng các quy trình học trực tuyến giám sát sự lệch phân phối.                                                                                                                                                                                                                    |   3   | D/V  |
| 1.6.6 | Xác minh rằng các biện pháp phòng thủ cụ thể chống lại các loại tấn công gây nhiễm dữ liệu đã biết (ví dụ: đảo nhãn, chèn kích hoạt cửa hậu, tấn công bằng mẫu có ảnh hưởng) được xem xét và triển khai dựa trên hồ sơ rủi ro của hệ thống và nguồn dữ liệu.                              |   3   | D/V  |

---

## C1.7 Xóa Dữ liệu Người dùng & Thực thi Sự đồng ý

Tôn trọng các yêu cầu xóa dữ liệu và rút lại sự đồng ý trên tất cả các bộ dữ liệu, bản sao lưu và các sản phẩm phái sinh.

|   #   | Description                                                                                                                                                                                                                                                                                                                        | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.7.1 | Xác minh rằng các quy trình xóa dữ liệu loại bỏ dữ liệu chính và dữ liệu dẫn xuất, đồng thời đánh giá ảnh hưởng đến mô hình, và tác động đến các mô hình bị ảnh hưởng được đánh giá và, nếu cần thiết, được xử lý (ví dụ: thông qua việc huấn luyện lại hoặc điều chỉnh lại).                                                      |   1   | D/V  |
| 1.7.2 | Xác minh rằng các cơ chế đã được thiết lập để theo dõi và tôn trọng phạm vi và trạng thái của sự đồng ý của người dùng (và việc rút lại) đối với dữ liệu sử dụng trong quá trình huấn luyện, và sự đồng ý được xác nhận trước khi dữ liệu được tích hợp vào các quy trình huấn luyện mới hoặc các cập nhật quan trọng cho mô hình. |   2   |  D   |
| 1.7.3 | Xác minh rằng các quy trình làm việc được kiểm tra hàng năm và được ghi chép lại.                                                                                                                                                                                                                                                  |   2   |  V   |

---

## C1.8 An ninh Chuỗi Cung Ứng

Kiểm tra nhà cung cấp dữ liệu bên ngoài và xác minh tính toàn vẹn qua các kênh được xác thực, mã hóa.

|   #   | Description                                                                                                                                                                                                                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.8.1 | Xác minh rằng các nhà cung cấp dữ liệu bên thứ ba, bao gồm cả nhà cung cấp mô hình đã được huấn luyện trước và bộ dữ liệu bên ngoài, đều phải trải qua kiểm tra thẩm định về bảo mật, quyền riêng tư, nguồn gốc đạo đức và chất lượng dữ liệu trước khi dữ liệu hoặc mô hình của họ được tích hợp.                                                     |   2   | D/V  |
| 1.8.2 | Xác minh rằng các chuyển khoản bên ngoài sử dụng TLS/xác thực và kiểm tra tính toàn vẹn.                                                                                                                                                                                                                                                               |   1   |  D   |
| 1.8.3 | Xác minh rằng các nguồn dữ liệu có rủi ro cao (ví dụ: bộ dữ liệu mã nguồn mở với nguồn gốc không rõ, nhà cung cấp chưa được kiểm duyệt) được kiểm tra kỹ lưỡng hơn, chẳng hạn như phân tích trong môi trường an toàn (sandbox), kiểm tra chất lượng/định kiến mở rộng và phát hiện đầu độc có mục tiêu, trước khi sử dụng trong các ứng dụng nhạy cảm. |   2   | D/V  |
| 1.8.4 | Xác minh rằng các mô hình đã được huấn luyện sẵn thu được từ bên thứ ba được đánh giá về các thiên kiến nhúng, khả năng có cửa hậu, tính toàn vẹn của kiến trúc, và nguồn gốc dữ liệu huấn luyện gốc của chúng trước khi điều chỉnh tiếp hoặc triển khai.                                                                                              |   3   | D/V  |

---

## C1.9 Phát hiện mẫu đối kháng

Thực hiện các biện pháp trong giai đoạn huấn luyện, chẳng hạn như huấn luyện đối kháng, để tăng cường khả năng chống chịu của mô hình trước các ví dụ đối kháng.

|   #   | Description                                                                                                                                                                                                                                                                                   | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.9.1 | Xác minh rằng các biện pháp phòng thủ thích hợp, như huấn luyện đối kháng (sử dụng các ví dụ đối kháng được tạo ra), tăng cường dữ liệu với các đầu vào bị biến đổi, hoặc các kỹ thuật tối ưu hóa bền vững, được triển khai và điều chỉnh cho các mô hình liên quan dựa trên đánh giá rủi ro. |   3   | D/V  |
| 1.9.2 | Xác minh rằng nếu sử dụng huấn luyện đối kháng, việc tạo ra, quản lý và phiên bản của các bộ dữ liệu đối kháng được ghi chép và kiểm soát.                                                                                                                                                    |   2   | D/V  |
| 1.9.3 | Xác minh rằng tác động của việc huấn luyện độ bền chống đối thủ lên hiệu suất mô hình (đối với cả đầu vào sạch và đầu vào đối thủ) và các chỉ số công bằng được đánh giá, ghi chép và theo dõi.                                                                                               |   3   | D/V  |
| 1.9.4 | Xác minh rằng các chiến lược huấn luyện đối kháng và độ bền được xem xét và cập nhật định kỳ để chống lại các kỹ thuật tấn công đối kháng ngày càng phát triển.                                                                                                                               |   3   | D/V  |

---

## C1.10 Dòng Dữ liệu và Khả năng Truy xuất nguồn gốc

Theo dõi toàn bộ hành trình của mỗi điểm dữ liệu từ nguồn đến đầu vào mô hình để đảm bảo khả năng kiểm toán và phản ứng sự cố.

|   #    | Description                                                                                                                                  | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.10.1 | Xác minh rằng nguồn gốc của từng điểm dữ liệu, bao gồm tất cả các phép biến đổi, tăng cường và hợp nhất, được ghi lại và có thể tái tạo lại. |   2   | D/V  |
| 1.10.2 | Xác minh rằng các bản ghi nguồn gốc là không thể thay đổi, được lưu trữ an toàn và có thể truy cập để kiểm toán hoặc điều tra.               |   2   | D/V  |
| 1.10.3 | Xác minh rằng việc theo dõi nguồn gốc bao gồm cả dữ liệu thô và dữ liệu tổng hợp.                                                            |   2   | D/V  |

---

## C1.11 Quản lý Dữ liệu Tổng hợp

Đảm bảo dữ liệu tổng hợp được quản lý đúng cách, gắn nhãn chính xác và đánh giá rủi ro một cách đầy đủ.

|   #    | Description                                                                                                                                             | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.11.1 | Xác minh rằng tất cả dữ liệu tổng hợp đều được gắn nhãn rõ ràng và có thể phân biệt với dữ liệu thực trong suốt quá trình xử lý.                        |   2   | D/V  |
| 1.11.2 | Xác minh rằng quy trình tạo dữ liệu tổng hợp, các tham số và mục đích sử dụng đã được ghi chép đầy đủ.                                                  |   2   | D/V  |
| 1.11.3 | Xác minh rằng dữ liệu tổng hợp đã được đánh giá rủi ro về thiên lệch, rò rỉ quyền riêng tư và các vấn đề đại diện trước khi sử dụng trong việc đào tạo. |   2   | D/V  |

---

## C1.12 Giám sát truy cập dữ liệu và phát hiện bất thường

Giám sát và cảnh báo về truy cập bất thường vào dữ liệu đào tạo để phát hiện các mối đe dọa nội bộ hoặc việc rò rỉ dữ liệu.

|   #    | Description                                                                                                                                                     | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.12.1 | Xác minh rằng tất cả các truy cập vào dữ liệu đào tạo đều được ghi lại, bao gồm người dùng, thời gian và hành động.                                             |   2   | D/V  |
| 1.12.2 | Xác minh rằng các nhật ký truy cập được xem xét thường xuyên để phát hiện các mẫu bất thường, chẳng hạn như xuất dữ liệu lớn hoặc truy cập từ các địa điểm mới. |   2   | D/V  |
| 1.12.3 | Xác minh rằng các cảnh báo được tạo ra cho các sự kiện truy cập đáng ngờ và được điều tra kịp thời.                                                             |   2   | D/V  |

---

## C1.13 Chính sách Lưu trữ và Hết hạn Dữ liệu

Định nghĩa và thực thi các khoảng thời gian lưu trữ dữ liệu nhằm giảm thiểu việc lưu trữ dữ liệu không cần thiết.

|   #    | Description                                                                                                        | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.13.1 | Xác minh rằng các khoảng thời gian lưu trữ rõ ràng được xác định cho tất cả các bộ dữ liệu đào tạo.                |   1   | D/V  |
| 1.13.2 | Xác minh rằng các bộ dữ liệu tự động hết hạn, bị xóa, hoặc được xem xét để xóa bỏ khi kết thúc vòng đời của chúng. |   2   | D/V  |
| 1.13.3 | Xác minh rằng các hành động lưu giữ và xóa bỏ được ghi lại và có thể kiểm toán.                                    |   2   | D/V  |

---

## C1.14 Tuân thủ Quy định và Pháp lý

Đảm bảo tất cả dữ liệu huấn luyện tuân thủ các luật và quy định hiện hành.

|   #    | Description                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.14.1 | Xác nhận rằng các yêu cầu về cư trú dữ liệu và chuyển giao dữ liệu xuyên biên giới được xác định và thực thi cho tất cả các bộ dữ liệu.  |   2   | D/V  |
| 1.14.2 | Xác minh rằng các quy định cụ thể theo ngành (ví dụ: chăm sóc sức khỏe, tài chính) đã được xác định và xử lý trong việc quản lý dữ liệu. |   2   | D/V  |
| 1.14.3 | Xác minh rằng việc tuân thủ các luật bảo mật thông tin liên quan (ví dụ: GDPR, CCPA) được ghi chép và xem xét thường xuyên.              |   2   | D/V  |

---

## C1.15 Đánh dấu nước dữ liệu & Đóng dấu vân tay dữ liệu

Phát hiện việc sử dụng lại trái phép hoặc rò rỉ dữ liệu sở hữu hoặc nhạy cảm.

|   #    | Description                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 1.15.1 | Xác minh rằng các bộ dữ liệu hoặc tập con đã được đóng dấu nước hoặc đánh dấu vân tay khi có thể.                              |   3   | D/V  |
| 1.15.2 | Xác minh rằng các phương pháp đóng dấu/đánh dấu không gây ra thiên vị hoặc rủi ro về quyền riêng tư.                           |   3   | D/V  |
| 1.15.3 | Xác minh rằng các kiểm tra định kỳ được thực hiện để phát hiện việc sử dụng lại hoặc rò rỉ dữ liệu có dấu bản quyền trái phép. |   3   | D/V  |

---

## C1.16 Quản lý Quyền của Chủ thể Dữ liệu

Hỗ trợ các quyền của chủ thể dữ liệu như quyền truy cập, chỉnh sửa, giới hạn và phản đối.

|   #    | Description                                                                                                                   | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.16.1 | Xác minh rằng có các cơ chế để đáp ứng các yêu cầu của đối tượng dữ liệu về quyền truy cập, chỉnh sửa, hạn chế hoặc phản đối. |   2   | D/V  |
| 1.16.2 | Xác minh rằng các yêu cầu được ghi lại, theo dõi và hoàn thành trong các khung thời gian được quy định bởi pháp luật.         |   2   | D/V  |
| 1.16.3 | Xác minh rằng các quy trình quyền của chủ thể dữ liệu được kiểm tra và xem xét thường xuyên để đảm bảo hiệu quả.              |   2   | D/V  |

---

## C1.17 Phân Tích Tác Động Phiên Bản Bộ Dữ Liệu

Đánh giá tác động của các thay đổi trong bộ dữ liệu trước khi cập nhật hoặc thay thế các phiên bản.

|   #    | Description                                                                                                                                                       | Level | Role |
| :----: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.17.1 | Xác minh rằng một phân tích tác động được thực hiện trước khi cập nhật hoặc thay thế phiên bản bộ dữ liệu, bao gồm hiệu suất mô hình, tính công bằng và tuân thủ. |   2   | D/V  |
| 1.17.2 | Xác nhận rằng kết quả của phân tích tác động được ghi chép và xem xét bởi các bên liên quan thích hợp.                                                            |   2   | D/V  |
| 1.17.3 | Xác minh rằng các kế hoạch khôi phục (rollback) đã được chuẩn bị sẵn sàng trong trường hợp các phiên bản mới gây ra rủi ro không chấp nhận được hoặc lỗi hồi quy. |   2   | D/V  |

---

## C1.18 An ninh lực lượng lao động chú thích dữ liệu

Đảm bảo an ninh và tính toàn vẹn của nhân sự tham gia chú thích dữ liệu.

|   #    | Description                                                                                                                              | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 1.18.1 | Xác minh rằng tất cả nhân sự tham gia chú thích dữ liệu đều được kiểm tra lý lịch và đào tạo về bảo mật dữ liệu cũng như quyền riêng tư. |   2   | D/V  |
| 1.18.2 | Xác minh rằng tất cả nhân viên chú thích đều ký các thỏa thuận bảo mật và không tiết lộ thông tin.                                       |   2   | D/V  |
| 1.18.3 | Xác minh rằng các nền tảng chú thích thực thi kiểm soát truy cập và giám sát các mối đe dọa từ bên trong.                                |   2   | D/V  |

---

## Tài liệu tham khảo

* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [EU AI Act – Article 10: Data & Data Governance](https://artificialintelligenceact.eu/article/10/)
* [MITRE ATLAS: Adversary Tactics for AI](https://atlas.mitre.org/)
* [Survey of ML Bias Mitigation Techniques – MDPI](https://www.mdpi.com/2673-6470/4/1/1)
* [Data Provenance & Lineage Best Practices – Nightfall AI](https://www.nightfall.ai/ai-security-101/data-provenance-and-lineage)
* [Data Labeling Quality Standards – LabelYourData](https://labelyourdata.com/articles/data-labeling-quality-and-how-to-measure-it)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [CISA Advisory: Securing Data for AI Systems](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [ISO/IEC 23053: AI Management Systems Framework](https://www.iso.org/sectors/it-technologies/ai)
* [IBM: What is AI Governance?](https://www.ibm.com/think/topics/ai-governance)
* [Google AI Principles](https://ai.google/principles/)
* [GDPR & AI Training Data – DataProtectionReport](https://www.dataprotectionreport.com/2024/08/recent-regulatory-developments-in-training-artificial-intelligence-ai-models-under-the-gdpr/)
* [Supply-Chain Security for AI Data – AppSOC](https://www.appsoc.com/blog/ai-is-the-new-frontier-of-supply-chain-security)
* [OpenAI Privacy Center – Data Deletion Controls](https://privacy.openai.com/policies?modal=take-control)
* [Adversarial ML Dataset – Kaggle](https://www.kaggle.com/datasets/cnrieiit/adversarial-machine-learning-dataset)


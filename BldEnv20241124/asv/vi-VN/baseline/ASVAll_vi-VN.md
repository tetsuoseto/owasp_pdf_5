## Trang đầu

### Về Tiêu chuẩn

Tiêu chuẩn Xác minh An ninh Trí tuệ Nhân tạo (AISVS) là một danh mục các yêu cầu về an ninh do cộng đồng phát triển, dành cho các nhà khoa học dữ liệu, kỹ sư MLOps, kiến trúc sư phần mềm, nhà phát triển, kiểm thử viên, chuyên gia an ninh, nhà cung cấp công cụ, cơ quan quản lý và người tiêu dùng sử dụng để thiết kế, xây dựng, kiểm thử và xác minh các hệ thống và ứng dụng hỗ trợ AI đáng tin cậy. Nó cung cấp một ngôn ngữ chung để xác định các kiểm soát an ninh trong suốt vòng đời AI — từ thu thập dữ liệu và phát triển mô hình đến triển khai và giám sát liên tục — nhằm giúp các tổ chức đo lường và nâng cao khả năng chống chịu, bảo mật quyền riêng tư và an toàn của các giải pháp AI của họ.

### Bản quyền và Giấy phép

Phiên bản 0.1 (Bản nháp công khai đầu tiên - Đang trong quá trình hoàn thiện), 2025  

![license](images/license.png)
Bản quyền © 2025 Dự án AISVS.  

Phát hành theo Creative Commons Attribution‑ShareAlike 4.0 International License.
Đối với bất kỳ việc tái sử dụng hoặc phân phối nào, bạn phải truyền đạt rõ ràng các điều khoản giấy phép của tác phẩm này tới người khác.

### Trưởng dự án

Jim Manico
Aras “Russ” Memisyazici

### Những Người Đóng Góp và Người Đánh Giá

https://github.com/ottosulin
https://github.com/mbhatt1
https://github.com/vineethsai
https://github.com/cciprofm
https://github.com/deepakrpandey12


---

AISVS là một tiêu chuẩn hoàn toàn mới được tạo ra đặc biệt để giải quyết các thách thức an ninh độc đáo của các hệ thống trí tuệ nhân tạo. Mặc dù nó lấy cảm hứng từ các thực tiễn an ninh tốt hơn rộng hơn, mọi yêu cầu trong AISVS đều được phát triển từ đầu để phản ánh bối cảnh các mối đe dọa AI và giúp các tổ chức xây dựng các giải pháp AI an toàn hơn, bền vững hơn.

## Lời nói đầu

Chào mừng bạn đến với Tiêu chuẩn Xác minh An ninh Trí tuệ Nhân tạo (AISVS) phiên bản 1.0!

### Giới thiệu

Được thành lập vào năm 2025 thông qua một nỗ lực hợp tác cộng đồng, AISVS xác định các yêu cầu bảo mật cần xem xét khi thiết kế, phát triển, triển khai và vận hành các mô hình AI hiện đại, các quy trình và dịch vụ hỗ trợ AI.

AISVS v1.0 đại diện cho công trình kết hợp của các trưởng dự án, nhóm làm việc và cộng đồng rộng lớn hơn để tạo ra một cơ sở thực tế, có thể kiểm tra nhằm bảo vệ hệ thống AI.

Mục tiêu của chúng tôi với phiên bản này là làm cho AISVS dễ dàng được áp dụng trong khi vẫn tập trung chính xác vào phạm vi đã định và giải quyết cảnh quan rủi ro đang phát triển nhanh chóng, đặc thù của AI.

### Mục tiêu chính cho AISVS Phiên bản 1.0

Phiên bản 1.0 sẽ được tạo ra dựa trên một số nguyên tắc chỉ đạo.

#### Phạm vi xác định rõ ràng

Mỗi yêu cầu phải phù hợp với tên gọi và sứ mệnh của AISVS:

Trí tuệ nhân tạo – Các kiểm soát hoạt động ở lớp AI/ML (dữ liệu, mô hình, quy trình, hoặc suy luận) và là trách nhiệm của các chuyên gia AI.
Bảo mật – Các yêu cầu trực tiếp giảm thiểu những rủi ro về bảo mật, quyền riêng tư hoặc an toàn đã được xác định.
Xác minh – Ngôn ngữ được viết để sự tuân thủ có thể được xác nhận một cách khách quan.
Tiêu chuẩn – Các phần tuân theo cấu trúc và thuật ngữ nhất quán để tạo thành một tài liệu tham khảo mạch lạc.
​
---

Bằng cách tuân theo AISVS, các tổ chức có thể hệ thống đánh giá và củng cố vị thế an ninh của các giải pháp AI của họ, thúc đẩy văn hóa kỹ thuật AI an toàn.

## Sử dụng AISVS

Tiêu chuẩn Xác minh An ninh Trí tuệ Nhân tạo (AISVS) quy định các yêu cầu an ninh cho các ứng dụng và dịch vụ AI hiện đại, tập trung vào các khía cạnh trong tầm kiểm soát của nhà phát triển ứng dụng.

AISVS dành cho bất kỳ ai phát triển hoặc đánh giá bảo mật các ứng dụng AI, bao gồm các nhà phát triển, kiến trúc sư, kỹ sư bảo mật và kiểm toán viên. Chương này giới thiệu cấu trúc và cách sử dụng AISVS, bao gồm các cấp độ xác minh và các trường hợp sử dụng dự kiến.

### Các cấp độ xác minh bảo mật Trí tuệ Nhân tạo

AISVS xác định ba cấp độ xác minh bảo mật tăng dần. Mỗi cấp độ thêm chiều sâu và độ phức tạp, cho phép các tổ chức điều chỉnh mức độ bảo mật phù hợp với mức độ rủi ro của hệ thống AI của họ.

Các tổ chức có thể bắt đầu từ Cấp 1 và dần dần áp dụng các cấp cao hơn khi mức độ trưởng thành về bảo mật và mức độ tiếp xúc với mối đe dọa tăng lên.

#### Định nghĩa các cấp độ

Mỗi yêu cầu trong AISVS phiên bản 1.0 được phân loại vào một trong các cấp độ sau:

 Yêu cầu cấp độ 1

Cấp độ 1 bao gồm các yêu cầu bảo mật quan trọng và nền tảng nhất. Chúng tập trung vào việc ngăn chặn các cuộc tấn công phổ biến không phụ thuộc vào các điều kiện tiên quyết hoặc lỗ hổng khác. Hầu hết các biện pháp kiểm soát ở Cấp độ 1 đều dễ thực hiện hoặc đủ thiết yếu để biện minh cho nỗ lực triển khai.

 Yêu cầu cấp độ 2

Cấp độ 2 giải quyết các cuộc tấn công nâng cao hơn hoặc ít phổ biến hơn, cũng như các biện pháp phòng thủ nhiều lớp chống lại các mối đe dọa phổ biến. Những yêu cầu này có thể bao gồm logic phức tạp hơn hoặc nhắm vào các điều kiện tiên quyết cụ thể của cuộc tấn công.

 Yêu cầu cấp độ 3

Cấp độ 3 bao gồm các biện pháp kiểm soát thường khó thực hiện hơn hoặc áp dụng theo tình huống. Những biện pháp này thường đại diện cho các cơ chế phòng thủ sâu hoặc các biện pháp giảm thiểu tấn công đặc thù, có mục tiêu hoặc có độ phức tạp cao.

#### Vai trò (D/V)

Mỗi yêu cầu AISVS được đánh dấu theo đối tượng chính:

D – Các yêu cầu tập trung vào nhà phát triển
V – Yêu cầu tập trung vào người kiểm tra/đánh giá
D/V – Liên quan đến cả nhà phát triển và người kiểm chứng

## Quản trị Dữ liệu Đào tạo C1 & Quản lý Định kiến

### Mục tiêu Kiểm soát

Dữ liệu đào tạo phải được thu thập, xử lý và duy trì theo cách bảo toàn nguồn gốc, bảo mật, chất lượng và tính công bằng. Thực hiện như vậy sẽ đáp ứng các nghĩa vụ pháp lý và giảm thiểu rủi ro thiên vị, đầu độc hoặc vi phạm quyền riêng tư trong suốt vòng đời của trí tuệ nhân tạo.

---

### C1.1 Nguồn gốc dữ liệu đào tạo

Duy trì một kho dữ liệu có thể xác minh được tất cả các tập dữ liệu, chỉ chấp nhận các nguồn tin cậy và ghi lại mọi thay đổi để có thể kiểm tra.

 #1.1.1    Level: 1    Role: D/V
 Xác minh rằng một danh mục cập nhật về mọi nguồn dữ liệu huấn luyện (nguồn gốc, người quản lý/chủ sở hữu, giấy phép, phương pháp thu thập, các ràng buộc về mục đích sử dụng, và lịch sử xử lý) được duy trì.
 #1.1.2    Level: 1    Role: D/V
 Xác minh rằng chỉ những bộ dữ liệu đã được kiểm định về chất lượng, tính đại diện, nguồn gốc đạo đức và tuân thủ giấy phép mới được phép sử dụng, giảm thiểu rủi ro về nhiễm độc dữ liệu, thiên vị ngầm và vi phạm sở hữu trí tuệ.
 #1.1.3    Level: 1    Role: D/V
 Xác minh rằng việc giảm thiểu dữ liệu được thực thi để loại bỏ các thuộc tính không cần thiết hoặc nhạy cảm.
 #1.1.4    Level: 2    Role: D/V
 Xác minh rằng tất cả các thay đổi dữ liệu đều phải tuân theo quy trình phê duyệt có ghi nhật ký.
 #1.1.5    Level: 2    Role: D/V
 Xác minh rằng chất lượng gán nhãn/chuẩn đoán được đảm bảo thông qua việc kiểm tra chéo hoặc đồng thuận của người đánh giá.
 #1.1.6    Level: 2    Role: D/V
 Xác minh rằng "thẻ dữ liệu" hoặc "bảng thông tin dữ liệu cho bộ dữ liệu" được duy trì cho các bộ dữ liệu huấn luyện quan trọng, chi tiết các đặc điểm, động cơ, thành phần, quy trình thu thập, tiền xử lý và các khuyến nghị/sử dụng không nên áp dụng.

---

### C1.2 An toàn và Toàn vẹn Dữ liệu Đào tạo

Hạn chế truy cập, mã hóa dữ liệu khi lưu trữ và truyền tải, và xác thực tính toàn vẹn để ngăn chặn việc giả mạo hoặc đánh cắp.

 #1.2.1    Level: 1    Role: D/V
 Xác minh rằng các kiểm soát truy cập bảo vệ lưu trữ và các pipeline.
 #1.2.2    Level: 2    Role: D/V
 Xác minh rằng các bộ dữ liệu được mã hóa khi truyền và, đối với tất cả thông tin nhạy cảm hoặc thông tin cá nhân có thể nhận dạng được (PII), được mã hóa khi lưu trữ, sử dụng các thuật toán mã hóa tiêu chuẩn ngành và các thực hành quản lý khóa.
 #1.2.3    Level: 2    Role: D/V
 Xác minh rằng các hàm băm mật mã hoặc chữ ký số được sử dụng để đảm bảo tính toàn vẹn dữ liệu trong quá trình lưu trữ và truyền tải, và các kỹ thuật phát hiện bất thường tự động được áp dụng để ngăn chặn các sửa đổi trái phép hoặc hỏng dữ liệu, bao gồm cả các cố gắng đầu độc dữ liệu có mục tiêu.
 #1.2.4    Level: 3    Role: D/V
 Xác minh rằng các phiên bản bộ dữ liệu được theo dõi để cho phép quay lại.
 #1.2.5    Level: 2    Role: D/V
 Xác nhận rằng dữ liệu lỗi thời được xóa hoặc ẩn danh một cách an toàn phù hợp với chính sách lưu giữ dữ liệu, các yêu cầu pháp lý và để giảm thiểu bề mặt tấn công.

---

### C1.3 Độ đầy đủ và Công bằng của Biểu diễn

Phát hiện sai lệch về nhân khẩu học và áp dụng các biện pháp giảm thiểu để tỷ lệ lỗi của mô hình được công bằng giữa các nhóm.

 #1.3.1    Level: 1    Role: D/V
 Xác minh rằng các bộ dữ liệu được phân tích hồ sơ để phát hiện sự mất cân bằng đại diện và các thiên vị tiềm ẩn đối với các thuộc tính được pháp luật bảo vệ (ví dụ: chủng tộc, giới tính, tuổi tác) và các đặc điểm nhạy cảm về mặt đạo đức khác liên quan đến lĩnh vực ứng dụng của mô hình (ví dụ: tình trạng kinh tế xã hội, vị trí địa lý).
 #1.3.2    Level: 2    Role: D/V
 Xác nhận rằng các thiên vị đã được xác định được giảm thiểu thông qua các chiến lược đã được ghi chép như cân bằng lại, tăng cường dữ liệu có mục tiêu, điều chỉnh thuật toán (ví dụ: các kỹ thuật tiền xử lý, xử lý trong quá trình, xử lý hậu kỳ), hoặc tái cân trọng số, và đánh giá tác động của việc giảm thiểu đối với cả tính công bằng và hiệu suất tổng thể của mô hình.
 #1.3.3    Level: 2    Role: D/V
 Xác nhận rằng các chỉ số công bằng sau đào tạo được đánh giá và ghi chép lại.
 #1.3.4    Level: 3    Role: D/V
 Xác minh rằng chính sách quản lý sai lệch theo vòng đời phân công người chịu trách nhiệm và tần suất rà soát.

---

### C1.4 Chất lượng, tính toàn vẹn và bảo mật của nhãn dữ liệu huấn luyện

Bảo vệ nhãn bằng mã hóa và yêu cầu đánh giá kép cho các lớp quan trọng.

 #1.4.1    Level: 2    Role: D/V
 Xác minh rằng chất lượng gán nhãn/chú thích được đảm bảo thông qua các hướng dẫn rõ ràng, kiểm tra chéo của người đánh giá, cơ chế đồng thuận (ví dụ: theo dõi sự đồng thuận giữa các người chú thích), và các quy trình xác định để giải quyết sự khác biệt.
 #1.4.2    Level: 2    Role: D/V
 Xác minh rằng các hàm băm mật mã hoặc chữ ký số được áp dụng cho các artifact nhãn để đảm bảo tính toàn vẹn và xác thực của chúng.
 #1.4.3    Level: 2    Role: D/V
 Xác minh rằng các giao diện và nền tảng dán nhãn thực thi kiểm soát truy cập chặt chẽ, duy trì nhật ký kiểm tra có khả năng phát hiện sự giả mạo đối với tất cả các hoạt động dán nhãn, và bảo vệ chống lại các sửa đổi trái phép.
 #1.4.4    Level: 3    Role: D/V
 Xác minh rằng các nhãn quan trọng đối với an toàn, bảo mật hoặc sự công bằng (ví dụ: nhận diện nội dung độc hại, phát hiện y tế quan trọng) được thực hiện kiểm duyệt độc lập bắt buộc bởi hai người hoặc có phương pháp xác minh mạnh tương đương.
 #1.4.5    Level: 2    Role: D/V
 Xác minh rằng thông tin nhạy cảm (bao gồm dữ liệu cá nhân nhận dạng được - PII) vô tình được ghi lại hoặc bắt buộc phải có trong nhãn được biên tập, giả danh, ẩn danh hoặc mã hóa khi lưu trữ và truyền tải, theo các nguyên tắc giảm thiểu dữ liệu.
 #1.4.6    Level: 2    Role: D/V
 Xác minh rằng các hướng dẫn và chỉ dẫn ghi nhãn đầy đủ, được kiểm soát phiên bản và được đồng nghiệp xem xét.
 #1.4.7    Level: 2    Role: D/V
 Xác minh rằng các sơ đồ dữ liệu (bao gồm cả nhãn) được định nghĩa rõ ràng và có kiểm soát phiên bản.
 #1.8.2    Level: 2    Role: D/V
 Xác minh rằng các quy trình làm việc gán nhãn thuê ngoài hoặc sử dụng nguồn lực đám đông bao gồm các biện pháp kỹ thuật/thủ tục để đảm bảo tính bảo mật, tính toàn vẹn của dữ liệu, chất lượng nhãn và ngăn ngừa rò rỉ dữ liệu.

---

### C1.5 Đảm bảo Chất lượng Dữ liệu Đào tạo

Kết hợp xác thực tự động, kiểm tra ngẫu nhiên thủ công và khắc phục ghi nhật ký để đảm bảo độ tin cậy của bộ dữ liệu.

 #1.5.1    Level: 1    Role: D
 Xác minh rằng các bài kiểm tra tự động phát hiện lỗi định dạng, giá trị null và lệch nhãn trong mỗi lần nhập liệu hoặc chuyển đổi quan trọng.
 #1.5.2    Level: 1    Role: D/V
 Xác minh rằng các bộ dữ liệu bị lỗi được cách ly cùng với các dấu vết kiểm tra.
 #1.5.3    Level: 2    Role: V
 Xác minh rằng các kiểm tra thủ công ngẫu nhiên do chuyên gia lĩnh vực thực hiện bao phủ một mẫu có ý nghĩa thống kê (ví dụ, ≥1% hoặc 1.000 mẫu, tùy theo giá trị nào lớn hơn, hoặc theo đánh giá rủi ro) để phát hiện các vấn đề chất lượng tinh vi mà tự động không bắt được.
 #1.5.4    Level: 2    Role: D/V
 Xác minh rằng các bước khắc phục được đính kèm vào các bản ghi nguồn gốc.
 #1.5.5    Level: 2    Role: D/V
 Xác minh rằng các cổng kiểm soát chất lượng ngăn chặn bộ dữ liệu kém chất lượng trừ khi có sự chấp thuận ngoại lệ.

---

### C1.6 Phát hiện Đầu độc Dữ liệu

Áp dụng phát hiện bất thường thống kê và quy trình cách ly để ngăn chặn các chèn ép đối nghịch.

 #1.6.1    Level: 2    Role: D/V
 Xác minh rằng các kỹ thuật phát hiện dị thường (ví dụ: phương pháp thống kê, phát hiện điểm ngoại lai, phân tích embedding) được áp dụng cho dữ liệu đào tạo khi nhập liệu và trước các lần đào tạo chính để xác định các cuộc tấn công đầu độc tiềm ẩn hoặc sự hỏng dữ liệu không chủ ý.
 #1.6.2    Level: 2    Role: D/V
 Xác minh rằng các mẫu bị đánh dấu kích hoạt việc xem xét thủ công trước khi đào tạo.
 #1.6.3    Level: 2    Role: V
 Xác minh rằng kết quả được đưa vào hồ sơ bảo mật của mô hình và cung cấp thông tin cho tình báo mối đe dọa đang diễn ra.
 #1.6.4    Level: 3    Role: D/V
 Xác minh rằng logic phát hiện được làm mới với thông tin tình báo mối đe dọa mới.
 #1.6.5    Level: 3    Role: D/V
 Xác nhận rằng các quy trình học trực tuyến giám sát sự lệch phân phối.
 #1.6.6    Level: 3    Role: D/V
 Xác minh rằng các biện pháp phòng thủ cụ thể chống lại các loại tấn công gây nhiễm dữ liệu đã biết (ví dụ: đảo nhãn, chèn kích hoạt cửa hậu, tấn công bằng mẫu có ảnh hưởng) được xem xét và triển khai dựa trên hồ sơ rủi ro của hệ thống và nguồn dữ liệu.

---

### C1.7 Xóa Dữ liệu Người dùng & Thực thi Sự đồng ý

Tôn trọng các yêu cầu xóa dữ liệu và rút lại sự đồng ý trên tất cả các bộ dữ liệu, bản sao lưu và các sản phẩm phái sinh.

 #1.7.1    Level: 1    Role: D/V
 Xác minh rằng các quy trình xóa dữ liệu loại bỏ dữ liệu chính và dữ liệu dẫn xuất, đồng thời đánh giá ảnh hưởng đến mô hình, và tác động đến các mô hình bị ảnh hưởng được đánh giá và, nếu cần thiết, được xử lý (ví dụ: thông qua việc huấn luyện lại hoặc điều chỉnh lại).
 #1.7.2    Level: 2    Role: D
 Xác minh rằng các cơ chế đã được thiết lập để theo dõi và tôn trọng phạm vi và trạng thái của sự đồng ý của người dùng (và việc rút lại) đối với dữ liệu sử dụng trong quá trình huấn luyện, và sự đồng ý được xác nhận trước khi dữ liệu được tích hợp vào các quy trình huấn luyện mới hoặc các cập nhật quan trọng cho mô hình.
 #1.7.3    Level: 2    Role: V
 Xác minh rằng các quy trình làm việc được kiểm tra hàng năm và được ghi chép lại.

---

### C1.8 An ninh Chuỗi Cung Ứng

Kiểm tra nhà cung cấp dữ liệu bên ngoài và xác minh tính toàn vẹn qua các kênh được xác thực, mã hóa.

 #1.8.1    Level: 2    Role: D/V
 Xác minh rằng các nhà cung cấp dữ liệu bên thứ ba, bao gồm cả nhà cung cấp mô hình đã được huấn luyện trước và bộ dữ liệu bên ngoài, đều phải trải qua kiểm tra thẩm định về bảo mật, quyền riêng tư, nguồn gốc đạo đức và chất lượng dữ liệu trước khi dữ liệu hoặc mô hình của họ được tích hợp.
 #1.8.2    Level: 1    Role: D
 Xác minh rằng các chuyển khoản bên ngoài sử dụng TLS/xác thực và kiểm tra tính toàn vẹn.
 #1.8.3    Level: 2    Role: D/V
 Xác minh rằng các nguồn dữ liệu có rủi ro cao (ví dụ: bộ dữ liệu mã nguồn mở với nguồn gốc không rõ, nhà cung cấp chưa được kiểm duyệt) được kiểm tra kỹ lưỡng hơn, chẳng hạn như phân tích trong môi trường an toàn (sandbox), kiểm tra chất lượng/định kiến mở rộng và phát hiện đầu độc có mục tiêu, trước khi sử dụng trong các ứng dụng nhạy cảm.
 #1.8.4    Level: 3    Role: D/V
 Xác minh rằng các mô hình đã được huấn luyện sẵn thu được từ bên thứ ba được đánh giá về các thiên kiến nhúng, khả năng có cửa hậu, tính toàn vẹn của kiến trúc, và nguồn gốc dữ liệu huấn luyện gốc của chúng trước khi điều chỉnh tiếp hoặc triển khai.

---

### C1.9 Phát hiện mẫu đối kháng

Thực hiện các biện pháp trong giai đoạn huấn luyện, chẳng hạn như huấn luyện đối kháng, để tăng cường khả năng chống chịu của mô hình trước các ví dụ đối kháng.

 #1.9.1    Level: 3    Role: D/V
 Xác minh rằng các biện pháp phòng thủ thích hợp, như huấn luyện đối kháng (sử dụng các ví dụ đối kháng được tạo ra), tăng cường dữ liệu với các đầu vào bị biến đổi, hoặc các kỹ thuật tối ưu hóa bền vững, được triển khai và điều chỉnh cho các mô hình liên quan dựa trên đánh giá rủi ro.
 #1.9.2    Level: 2    Role: D/V
 Xác minh rằng nếu sử dụng huấn luyện đối kháng, việc tạo ra, quản lý và phiên bản của các bộ dữ liệu đối kháng được ghi chép và kiểm soát.
 #1.9.3    Level: 3    Role: D/V
 Xác minh rằng tác động của việc huấn luyện độ bền chống đối thủ lên hiệu suất mô hình (đối với cả đầu vào sạch và đầu vào đối thủ) và các chỉ số công bằng được đánh giá, ghi chép và theo dõi.
 #1.9.4    Level: 3    Role: D/V
 Xác minh rằng các chiến lược huấn luyện đối kháng và độ bền được xem xét và cập nhật định kỳ để chống lại các kỹ thuật tấn công đối kháng ngày càng phát triển.

---

### C1.10 Dòng Dữ liệu và Khả năng Truy xuất nguồn gốc

Theo dõi toàn bộ hành trình của mỗi điểm dữ liệu từ nguồn đến đầu vào mô hình để đảm bảo khả năng kiểm toán và phản ứng sự cố.

 #1.10.1    Level: 2    Role: D/V
 Xác minh rằng nguồn gốc của từng điểm dữ liệu, bao gồm tất cả các phép biến đổi, tăng cường và hợp nhất, được ghi lại và có thể tái tạo lại.
 #1.10.2    Level: 2    Role: D/V
 Xác minh rằng các bản ghi nguồn gốc là không thể thay đổi, được lưu trữ an toàn và có thể truy cập để kiểm toán hoặc điều tra.
 #1.10.3    Level: 2    Role: D/V
 Xác minh rằng việc theo dõi nguồn gốc bao gồm cả dữ liệu thô và dữ liệu tổng hợp.

---

### C1.11 Quản lý Dữ liệu Tổng hợp

Đảm bảo dữ liệu tổng hợp được quản lý đúng cách, gắn nhãn chính xác và đánh giá rủi ro một cách đầy đủ.

 #1.11.1    Level: 2    Role: D/V
 Xác minh rằng tất cả dữ liệu tổng hợp đều được gắn nhãn rõ ràng và có thể phân biệt với dữ liệu thực trong suốt quá trình xử lý.
 #1.11.2    Level: 2    Role: D/V
 Xác minh rằng quy trình tạo dữ liệu tổng hợp, các tham số và mục đích sử dụng đã được ghi chép đầy đủ.
 #1.11.3    Level: 2    Role: D/V
 Xác minh rằng dữ liệu tổng hợp đã được đánh giá rủi ro về thiên lệch, rò rỉ quyền riêng tư và các vấn đề đại diện trước khi sử dụng trong việc đào tạo.

---

### C1.12 Giám sát truy cập dữ liệu và phát hiện bất thường

Giám sát và cảnh báo về truy cập bất thường vào dữ liệu đào tạo để phát hiện các mối đe dọa nội bộ hoặc việc rò rỉ dữ liệu.

 #1.12.1    Level: 2    Role: D/V
 Xác minh rằng tất cả các truy cập vào dữ liệu đào tạo đều được ghi lại, bao gồm người dùng, thời gian và hành động.
 #1.12.2    Level: 2    Role: D/V
 Xác minh rằng các nhật ký truy cập được xem xét thường xuyên để phát hiện các mẫu bất thường, chẳng hạn như xuất dữ liệu lớn hoặc truy cập từ các địa điểm mới.
 #1.12.3    Level: 2    Role: D/V
 Xác minh rằng các cảnh báo được tạo ra cho các sự kiện truy cập đáng ngờ và được điều tra kịp thời.

---

### C1.13 Chính sách Lưu trữ và Hết hạn Dữ liệu

Định nghĩa và thực thi các khoảng thời gian lưu trữ dữ liệu nhằm giảm thiểu việc lưu trữ dữ liệu không cần thiết.

 #1.13.1    Level: 1    Role: D/V
 Xác minh rằng các khoảng thời gian lưu trữ rõ ràng được xác định cho tất cả các bộ dữ liệu đào tạo.
 #1.13.2    Level: 2    Role: D/V
 Xác minh rằng các bộ dữ liệu tự động hết hạn, bị xóa, hoặc được xem xét để xóa bỏ khi kết thúc vòng đời của chúng.
 #1.13.3    Level: 2    Role: D/V
 Xác minh rằng các hành động lưu giữ và xóa bỏ được ghi lại và có thể kiểm toán.

---

### C1.14 Tuân thủ Quy định và Pháp lý

Đảm bảo tất cả dữ liệu huấn luyện tuân thủ các luật và quy định hiện hành.

 #1.14.1    Level: 2    Role: D/V
 Xác nhận rằng các yêu cầu về cư trú dữ liệu và chuyển giao dữ liệu xuyên biên giới được xác định và thực thi cho tất cả các bộ dữ liệu.
 #1.14.2    Level: 2    Role: D/V
 Xác minh rằng các quy định cụ thể theo ngành (ví dụ: chăm sóc sức khỏe, tài chính) đã được xác định và xử lý trong việc quản lý dữ liệu.
 #1.14.3    Level: 2    Role: D/V
 Xác minh rằng việc tuân thủ các luật bảo mật thông tin liên quan (ví dụ: GDPR, CCPA) được ghi chép và xem xét thường xuyên.

---

### C1.15 Đánh dấu nước dữ liệu & Đóng dấu vân tay dữ liệu

Phát hiện việc sử dụng lại trái phép hoặc rò rỉ dữ liệu sở hữu hoặc nhạy cảm.

 #1.15.1    Level: 3    Role: D/V
 Xác minh rằng các bộ dữ liệu hoặc tập con đã được đóng dấu nước hoặc đánh dấu vân tay khi có thể.
 #1.15.2    Level: 3    Role: D/V
 Xác minh rằng các phương pháp đóng dấu/đánh dấu không gây ra thiên vị hoặc rủi ro về quyền riêng tư.
 #1.15.3    Level: 3    Role: D/V
 Xác minh rằng các kiểm tra định kỳ được thực hiện để phát hiện việc sử dụng lại hoặc rò rỉ dữ liệu có dấu bản quyền trái phép.

---

### C1.16 Quản lý Quyền của Chủ thể Dữ liệu

Hỗ trợ các quyền của chủ thể dữ liệu như quyền truy cập, chỉnh sửa, giới hạn và phản đối.

 #1.16.1    Level: 2    Role: D/V
 Xác minh rằng có các cơ chế để đáp ứng các yêu cầu của đối tượng dữ liệu về quyền truy cập, chỉnh sửa, hạn chế hoặc phản đối.
 #1.16.2    Level: 2    Role: D/V
 Xác minh rằng các yêu cầu được ghi lại, theo dõi và hoàn thành trong các khung thời gian được quy định bởi pháp luật.
 #1.16.3    Level: 2    Role: D/V
 Xác minh rằng các quy trình quyền của chủ thể dữ liệu được kiểm tra và xem xét thường xuyên để đảm bảo hiệu quả.

---

### C1.17 Phân Tích Tác Động Phiên Bản Bộ Dữ Liệu

Đánh giá tác động của các thay đổi trong bộ dữ liệu trước khi cập nhật hoặc thay thế các phiên bản.

 #1.17.1    Level: 2    Role: D/V
 Xác minh rằng một phân tích tác động được thực hiện trước khi cập nhật hoặc thay thế phiên bản bộ dữ liệu, bao gồm hiệu suất mô hình, tính công bằng và tuân thủ.
 #1.17.2    Level: 2    Role: D/V
 Xác nhận rằng kết quả của phân tích tác động được ghi chép và xem xét bởi các bên liên quan thích hợp.
 #1.17.3    Level: 2    Role: D/V
 Xác minh rằng các kế hoạch khôi phục (rollback) đã được chuẩn bị sẵn sàng trong trường hợp các phiên bản mới gây ra rủi ro không chấp nhận được hoặc lỗi hồi quy.

---

### C1.18 An ninh lực lượng lao động chú thích dữ liệu

Đảm bảo an ninh và tính toàn vẹn của nhân sự tham gia chú thích dữ liệu.

 #1.18.1    Level: 2    Role: D/V
 Xác minh rằng tất cả nhân sự tham gia chú thích dữ liệu đều được kiểm tra lý lịch và đào tạo về bảo mật dữ liệu cũng như quyền riêng tư.
 #1.18.2    Level: 2    Role: D/V
 Xác minh rằng tất cả nhân viên chú thích đều ký các thỏa thuận bảo mật và không tiết lộ thông tin.
 #1.18.3    Level: 2    Role: D/V
 Xác minh rằng các nền tảng chú thích thực thi kiểm soát truy cập và giám sát các mối đe dọa từ bên trong.

---

### Tài liệu tham khảo

NIST AI Risk Management Framework
EU AI Act – Article 10: Data & Data Governance
MITRE ATLAS: Adversary Tactics for AI
Survey of ML Bias Mitigation Techniques – MDPI
Data Provenance & Lineage Best Practices – Nightfall AI
Data Labeling Quality Standards – LabelYourData
Training Data Poisoning Guide – Lakera.ai
CISA Advisory: Securing Data for AI Systems
ISO/IEC 23053: AI Management Systems Framework
IBM: What is AI Governance?
Google AI Principles
GDPR & AI Training Data – DataProtectionReport
Supply-Chain Security for AI Data – AppSOC
OpenAI Privacy Center – Data Deletion Controls
Adversarial ML Dataset – Kaggle

## Xác thực đầu vào của người dùng C2

### Mục tiêu kiểm soát

Xác thực đầu vào của người dùng một cách chặt chẽ là lá chắn phòng thủ hàng đầu chống lại một số cuộc tấn công gây hại nhất đối với các hệ thống AI. Các cuộc tấn công chèn prompt có thể ghi đè các lệnh hệ thống, rò rỉ dữ liệu nhạy cảm hoặc điều khiển mô hình theo hướng hành vi không được phép. Trừ khi có các bộ lọc chuyên dụng và cấu trúc chỉ dẫn phân cấp được thiết lập, nghiên cứu cho thấy các phương pháp jailbreak "đa lần" khai thác cửa sổ ngữ cảnh rất dài sẽ hiệu quả. Ngoài ra, các cuộc tấn công gây nhiễu đối kháng tinh vi — như việc hoán đổi ký tự giống hình dạng (homoglyph) hoặc ngôn ngữ leetspeak — có thể âm thầm thay đổi các quyết định của mô hình.

---

### Phòng thủ Tiêm nhiễm Lệnh (Prompt Injection Defense) C2.1

Tấn công chèn đoạn lệnh (prompt injection) là một trong những rủi ro hàng đầu đối với các hệ thống AI. Các biện pháp phòng vệ chống lại chiến thuật này sử dụng sự kết hợp giữa bộ lọc mẫu tĩnh, bộ phân loại động và việc thực thi thứ bậc hướng dẫn.

 #2.1.1    Level: 1    Role: D/V
 Xác minh rằng các đầu vào của người dùng được kiểm tra dựa trên một thư viện liên tục được cập nhật các mẫu tấn công chèn lệnh (từ khóa jailbreak, "bỏ qua trước đó", chuỗi nhập vai, các cuộc tấn công gián tiếp qua HTML/URL).
 #2.1.2    Level: 1    Role: D/V
 Xác minh rằng hệ thống thi hành một cấu trúc hướng dẫn theo thứ bậc trong đó các thông điệp của hệ thống hoặc nhà phát triển ghi đè lên các hướng dẫn của người dùng, ngay cả sau khi mở rộng cửa sổ ngữ cảnh.
 #2.1.3    Level: 2    Role: D/V
 Xác minh rằng các bài kiểm tra đánh giá đối kháng (ví dụ, các lệnh nhắc "nhiều lần" của Đội Đỏ) được thực hiện trước mỗi lần phát hành mô hình hoặc mẫu lời nhắc, kèm theo các ngưỡng tỷ lệ thành công và các cơ chế chặn tự động cho các trường hợp suy giảm hiệu suất.
 #2.1.4    Level: 2    Role: D
 Xác minh rằng các câu lệnh xuất phát từ nội dung bên thứ ba (trang web, tệp PDF, email) được làm sạch trong một ngữ cảnh phân tích riêng biệt trước khi được nối vào câu lệnh chính.
 #2.1.5    Level: 3    Role: D/V
 Xác minh rằng tất cả các cập nhật quy tắc lọc prompt, các phiên bản mô hình phân loại và các thay đổi danh sách chặn đều được quản lý phiên bản và có thể kiểm tra được.

---

### C2.2 Kháng lại Ví dụ Đối kháng

Mô hình Xử lý Ngôn ngữ Tự nhiên (NLP) vẫn dễ bị tổn thương bởi các biến động tinh vi ở cấp độ ký tự hoặc từ mà con người thường bỏ qua nhưng mô hình có xu hướng phân loại sai.

 #2.2.1    Level: 1    Role: D
 Xác minh rằng các bước chuẩn hóa đầu vào cơ bản (Unicode NFC, ánh xạ homoglyph, cắt khoảng trắng) được thực hiện trước khi phân tích từ.
 #2.2.2    Level: 2    Role: D/V
 Xác minh rằng phát hiện dị thường thống kê đánh dấu các đầu vào có khoảng cách chỉnh sửa cao bất thường so với chuẩn ngôn ngữ, số lượng token lặp lại quá mức, hoặc khoảng cách nhúng bất thường.
 #2.2.3    Level: 2    Role: D
 Xác nhận rằng quy trình suy luận hỗ trợ các biến thể mô hình được gia cố bằng huấn luyện đối kháng tùy chọn hoặc các lớp phòng thủ (ví dụ, ngẫu nhiên hóa, chưng cất phòng thủ) cho các điểm cuối có rủi ro cao.
 #2.2.4    Level: 2    Role: V
 Xác minh rằng các đầu vào nghi ngờ là tấn công đối thủ được cách ly, ghi lại cùng với toàn bộ dữ liệu (sau khi đã loại bỏ thông tin cá nhân nhạy cảm).
 #2.2.5    Level: 3    Role: D/V
 Xác minh rằng các chỉ số độ bền (tỷ lệ thành công của các bộ công cụ tấn công đã biết) được theo dõi theo thời gian và các suy giảm hiệu suất gây ra việc chặn phát hành.

---

### C2.3 Xác thực Lược đồ, Kiểu dữ liệu & Độ dài

Các cuộc tấn công AI sử dụng dữ liệu đầu vào bị lỗi định dạng hoặc quá cỡ có thể gây ra lỗi phân tích cú pháp, tràn dữ liệu trong các trường, và cạn kiệt tài nguyên. Việc thực thi nghiêm ngặt sơ đồ cấu trúc (schema) cũng là điều kiện tiên quyết khi thực hiện các cuộc gọi công cụ có tính xác định.

 #2.3.1    Level: 1    Role: D
 Xác minh rằng mọi điểm cuối gọi API hoặc hàm đều định nghĩa một schema đầu vào rõ ràng (JSON Schema, Protobuf hoặc tương đương đa mô hình) và rằng các đầu vào được kiểm tra hợp lệ trước khi tạo prompt.
 #2.3.2    Level: 1    Role: D/V
 Xác minh rằng các đầu vào vượt quá giới hạn tối đa về token hoặc byte đều bị từ chối với lỗi an toàn và không bao giờ bị cắt bớt một cách im lặng.
 #2.3.3    Level: 2    Role: D/V
 Xác minh rằng các kiểm tra kiểu (ví dụ: phạm vi số, giá trị enum, loại MIME cho hình ảnh/âm thanh) được thực thi phía máy chủ, không chỉ trong mã phía khách.
 #2.3.4    Level: 2    Role: D
 Xác minh rằng các bộ kiểm tra ngữ nghĩa (ví dụ: JSON Schema) chạy trong thời gian không đổi để ngăn chặn tấn công từ chối dịch vụ thuật toán (DoS).
 #2.3.5    Level: 3    Role: V
 Xác minh rằng các lỗi xác thực được ghi lại với các đoạn tải trọng đã được che khuất và mã lỗi rõ ràng để hỗ trợ phân loại sự cố bảo mật.

---

### C2.4 Sàng lọc Nội dung & Chính sách

Các nhà phát triển nên có khả năng phát hiện các lời nhắc hợp lệ về mặt cú pháp nhưng yêu cầu nội dung bị cấm (chẳng hạn như hướng dẫn bất hợp pháp, ngôn ngữ thù địch và văn bản có bản quyền) và ngăn chặn chúng lan truyền.

 #2.4.1    Level: 1    Role: D
 Xác minh rằng bộ phân loại nội dung (zero shot hoặc đã tinh chỉnh) chấm điểm từng đầu vào về các yếu tố bạo lực, tự làm hại bản thân, thù hận, nội dung tình dục và yêu cầu bất hợp pháp, với các ngưỡng có thể cấu hình được.
 #2.4.2    Level: 1    Role: D/V
 Xác minh rằng các đầu vào vi phạm chính sách sẽ nhận được phản hồi từ chối chuẩn hóa hoặc hoàn thành an toàn để chúng không lan truyền đến các cuộc gọi LLM tiếp theo.
 #2.4.3    Level: 2    Role: D
 Xác nhận rằng mô hình sàng lọc hoặc bộ quy tắc được đào tạo lại/cập nhật ít nhất hàng quý, bao gồm các mẫu bỏ qua chính sách hoặc jailbreak mới được quan sát.
 #2.4.4    Level: 2    Role: D
 Xác minh rằng việc sàng lọc tuân thủ các chính sách riêng của người dùng (độ tuổi, các hạn chế pháp lý theo vùng) thông qua các quy tắc dựa trên thuộc tính được giải quyết tại thời điểm yêu cầu.
 #2.4.5    Level: 3    Role: V
 Xác minh rằng nhật ký sàng lọc bao gồm điểm tin cậy của bộ phân loại và thẻ danh mục chính sách để tương quan SOC và phát lại nhóm đỏ trong tương lai.

---

### C2.5 Giới hạn tốc độ đầu vào & Ngăn chặn lạm dụng

Các nhà phát triển nên ngăn chặn việc lạm dụng, cạn kiệt tài nguyên và các cuộc tấn công tự động vào hệ thống AI bằng cách giới hạn tốc độ đầu vào và phát hiện các mẫu sử dụng bất thường.

 #2.5.1    Level: 1    Role: D/V
 Xác minh rằng giới hạn tốc độ theo người dùng, theo địa chỉ IP và theo khóa API được thực thi cho tất cả các điểm đầu vào.
 #2.5.2    Level: 2    Role: D/V
 Xác minh rằng các giới hạn tốc độ đỉnh và duy trì được điều chỉnh để ngăn ngừa các cuộc tấn công từ chối dịch vụ (DoS) và tấn công dò mật khẩu (brute force).
 #2.5.3    Level: 2    Role: D/V
 Xác minh rằng các mẫu sử dụng bất thường (ví dụ: yêu cầu liên tục nhanh, đầu vào tràn ngập) kích hoạt các chặn tự động hoặc tăng cấp.
 #2.5.4    Level: 3    Role: V
 Xác minh rằng các bản ghi phòng chống lạm dụng được lưu giữ và xem xét để phát hiện các mô hình tấn công mới xuất hiện.

---

### C2.6 Xác thực đầu vào đa phương thức

Hệ thống AI nên bao gồm kiểm tra xác thực mạnh mẽ cho các đầu vào phi văn bản (hình ảnh, âm thanh, tệp tin) để ngăn chặn việc tiêm nhiễm, né tránh hoặc lạm dụng tài nguyên.

 #2.6.1    Level: 1    Role: D
 Xác nhận rằng tất cả các đầu vào không phải văn bản (hình ảnh, âm thanh, tập tin) đều được kiểm tra về loại, kích thước và định dạng trước khi xử lý.
 #2.6.2    Level: 2    Role: D/V
 Xác minh rằng các tệp được quét để phát hiện phần mềm độc hại và tải payload ẩn (steganographic) trước khi nhập dữ liệu.
 #2.6.3    Level: 2    Role: D/V
 Xác minh rằng các đầu vào hình ảnh / âm thanh được kiểm tra các nhiễu loạn gây đối kháng hoặc các mẫu tấn công đã biết.
 #2.6.4    Level: 3    Role: V
 Xác minh rằng các lỗi xác thực đầu vào đa phương thức được ghi lại và kích hoạt cảnh báo để điều tra.

---

### C2.7 Nguồn Gốc Dữ Liệu Đầu Vào & Ghi Công

Các hệ thống AI nên hỗ trợ kiểm toán, theo dõi lạm dụng và tuân thủ bằng cách giám sát và gắn thẻ nguồn gốc của tất cả các đầu vào của người dùng.

 #2.7.1    Level: 1    Role: D/V
 Xác minh rằng tất cả các đầu vào của người dùng đều được gắn thẻ với siêu dữ liệu (ID người dùng, phiên làm việc, nguồn, dấu thời gian, địa chỉ IP) khi tiếp nhận.
 #2.7.2    Level: 2    Role: D/V
 Xác minh rằng siêu dữ liệu nguồn gốc được giữ lại và có thể kiểm tra được cho tất cả các đầu vào đã xử lý.
 #2.7.3    Level: 2    Role: D/V
 Xác minh rằng các nguồn đầu vào bất thường hoặc không tin cậy được đánh dấu và chịu sự kiểm tra nghiêm ngặt hơn hoặc bị chặn.

---

### C2.8 Phát hiện mối đe dọa thích ứng theo thời gian thực

Các nhà phát triển nên sử dụng các hệ thống phát hiện mối đe dọa tiên tiến cho AI, có khả năng thích ứng với các mẫu tấn công mới và cung cấp bảo vệ thời gian thực với phương pháp so khớp mẫu biên dịch.

 #2.8.1    Level: 1    Role: D/V
 Xác minh rằng các mẫu phát hiện mối đe dọa được biên dịch thành các bộ máy regex tối ưu hóa để lọc thời gian thực hiệu suất cao với tác động độ trễ tối thiểu.
 #2.8.2    Level: 1    Role: D/V
 Xác minh rằng các hệ thống phát hiện mối đe dọa duy trì các thư viện mẫu riêng biệt cho các loại mối đe dọa khác nhau (chèn lệnh gợi ý, nội dung gây hại, dữ liệu nhạy cảm, lệnh hệ thống).
 #2.8.3    Level: 2    Role: D/V
 Xác minh rằng việc phát hiện mối đe dọa thích ứng bao gồm các mô hình học máy cập nhật độ nhạy mối đe dọa dựa trên tần suất và tỷ lệ thành công của các cuộc tấn công.
 #2.8.4    Level: 2    Role: D/V
 Xác minh rằng các nguồn dữ liệu thông tin tình báo mối đe dọa theo thời gian thực tự động cập nhật thư viện mẫu với các chữ ký tấn công và các Chỉ báo Xâm nhập (IOCs) mới.
 #2.8.5    Level: 3    Role: D/V
 Xác minh rằng tỷ lệ dương tính giả trong phát hiện mối đe dọa được theo dõi liên tục và tính đặc hiệu của mẫu được tự động điều chỉnh để giảm thiểu sự cản trở trong các trường hợp sử dụng hợp pháp.
 #2.8.6    Level: 3    Role: D/V
 Xác minh rằng phân tích mối đe dọa theo ngữ cảnh xem xét nguồn đầu vào, các mẫu hành vi người dùng và lịch sử phiên để cải thiện độ chính xác trong việc phát hiện.
 #2.8.7    Level: 3    Role: D/V
 Xác nhận rằng các chỉ số hiệu suất phát hiện mối đe dọa (tỷ lệ phát hiện, độ trễ xử lý, sử dụng tài nguyên) được giám sát và tối ưu hóa theo thời gian thực.

---

### C2.9 Quy trình xác thực bảo mật đa phương thức

Các nhà phát triển nên cung cấp xác thực bảo mật cho văn bản, hình ảnh, âm thanh và các loại đầu vào AI khác với các loại phát hiện mối đe dọa cụ thể và cách ly tài nguyên.

 #2.9.1    Level: 1    Role: D/V
 Xác minh rằng mỗi phương thức đầu vào đều có các bộ kiểm tra bảo mật chuyên dụng với các mẫu mối đe dọa được tài liệu hóa (văn bản: tiêm lệnh nhắc, hình ảnh: ẩn hình, âm thanh: tấn công phổ tần) và các ngưỡng phát hiện.
 #2.9.2    Level: 2    Role: D/V
 Xác minh rằng các đầu vào đa phương thức được xử lý trong các vùng cách ly riêng biệt với giới hạn tài nguyên xác định (bộ nhớ, CPU, thời gian xử lý) cụ thể cho từng loại phương thức và được ghi chép trong các chính sách bảo mật.
 #2.9.3    Level: 2    Role: D/V
 Xác minh rằng phát hiện tấn công đa phương thức có thể nhận diện các cuộc tấn công phối hợp trên nhiều loại đầu vào khác nhau (ví dụ, payload ẩn trong ảnh kết hợp với chèn lệnh trong văn bản) bằng các quy tắc tương quan và tạo cảnh báo.
 #2.9.4    Level: 3    Role: D/V
 Xác minh rằng các lỗi xác thực đa phương thức kích hoạt ghi nhật ký chi tiết bao gồm tất cả các phương thức đầu vào, kết quả xác thực, điểm mối đe dọa và phân tích tương quan với định dạng nhật ký có cấu trúc để tích hợp SIEM.
 #2.9.5    Level: 3    Role: D/V
 Xác minh rằng các bộ phân loại nội dung theo loại phương thức đã được cập nhật theo lịch trình đã được ghi lại (ít nhất hàng quý) với các mẫu mối đe dọa mới, ví dụ đối kháng, và các chuẩn hiệu suất duy trì trên ngưỡng cơ bản.

---

### Tài liệu tham khảo

LLM01:2025 Prompt Injection – OWASP Top 10 for LLM & Generative AI Security
Generative AI's Biggest Security Flaw Is Not Easy to Fix
Many-shot jailbreaking \ Anthropic
$PDF$ OpenAI GPT-4.5 System Card
Notebook for the CheckThat Lab at CLEF 2024
Mitigate jailbreaks and prompt injections – Anthropic
Chapter 3 MITRE ATT\&CK – Adversarial Model Analysis
OWASP Top 10 for LLM Applications 2025 – WorldTech IT
OWASP Machine Learning Security Top Ten
Few words about AI Security – Jussi Metso
How To Ensure LLM Output Adheres to a JSON Schema | Modelmetry
Easily enforcing valid JSON schema following – API
AI Safety + Cybersecurity R\&D Tracker – Fairly AI
Anthropic makes 'jailbreak' advance to stop AI models producing harmful results
Pattern matching filter rules - IBM
Real-time Threat Detection

## Quản lý Vòng đời Mô hình C3 & Kiểm soát Thay đổi

### Mục tiêu Kiểm soát

Các hệ thống AI phải triển khai quy trình kiểm soát thay đổi nhằm ngăn chặn các sửa đổi mô hình không được phép hoặc không an toàn tiếp cận môi trường sản xuất. Quy trình kiểm soát này đảm bảo tính toàn vẹn của mô hình trong suốt vòng đời—từ phát triển đến triển khai và đến khi ngừng hoạt động—giúp phản ứng nhanh chóng với sự cố và duy trì trách nhiệm cho tất cả các thay đổi.

Mục tiêu bảo mật cốt lõi: Chỉ những mô hình được ủy quyền và xác thực mới được đưa vào sản xuất thông qua các quy trình kiểm soát nhằm duy trì tính toàn vẹn, khả năng truy xuất và khả năng phục hồi.

---

### C3.1 Ủy quyền và Tính toàn vẹn của Mô hình

Chỉ các mô hình được ủy quyền với tính toàn vẹn đã được xác minh mới được đưa vào môi trường sản xuất.

 #3.1.1    Level: 1    Role: D/V
 Xác minh rằng tất cả các hiện vật mô hình (trọng số, cấu hình, bộ mã hóa từ) đều được ký kỹ thuật số bởi các thực thể được ủy quyền trước khi triển khai.
 #3.1.2    Level: 1    Role: D/V
 Xác minh rằng tính toàn vẹn của mô hình được kiểm tra khi triển khai và các lỗi xác thực chữ ký ngăn chặn việc tải mô hình.
 #3.1.3    Level: 2    Role: D/V
 Xác minh rằng hồ sơ nguồn gốc mô hình bao gồm danh tính của thực thể ủy quyền, bảng kiểm đối chiếu dữ liệu đào tạo, kết quả kiểm tra xác nhận với trạng thái đạt/không đạt, và dấu thời gian tạo.
 #3.1.4    Level: 2    Role: D/V
 Xác minh rằng tất cả các mô hình mẫu sử dụng hệ phiên bản ngữ nghĩa (MAJOR.MINOR.PATCH) với các tiêu chí được ghi nhận rõ ràng xác định khi nào mỗi thành phần phiên bản sẽ tăng lên.
 #3.1.5    Level: 2    Role: V
 Xác minh rằng theo dõi phụ thuộc duy trì một kho hàng thời gian thực cho phép xác định nhanh tất cả các hệ thống tiêu thụ.

---

### C3.2 Xác thực và Kiểm thử Mô hình

Mô hình phải vượt qua các kiểm tra về bảo mật và an toàn đã được xác định trước khi triển khai.

 #3.2.1    Level: 1    Role: D/V
 Xác nhận rằng các mô hình được kiểm tra an ninh tự động bao gồm kiểm tra hợp lệ đầu vào, làm sạch đầu ra và đánh giá an toàn với các ngưỡng đạt/không đạt đã được tổ chức thỏa thuận trước khi triển khai.
 #3.2.2    Level: 1    Role: D/V
 Xác minh rằng các lỗi xác thực tự động chặn việc triển khai mô hình ngay cả sau khi có sự phê duyệt ghi đè rõ ràng từ nhân sự được ủy quyền trước, kèm theo các lý do kinh doanh đã được ghi chép.
 #3.2.3    Level: 2    Role: V
 Xác minh rằng kết quả kiểm tra được ký số bằng mật mã và liên kết bất biến với băm phiên bản mô hình cụ thể đang được xác thực.
 #3.2.4    Level: 2    Role: D/V
 Xác minh rằng việc triển khai khẩn cấp yêu cầu phải có đánh giá rủi ro bảo mật được ghi chép và phê duyệt từ cơ quan an ninh được chỉ định trước trong khung thời gian đã thỏa thuận trước.

---

### C3.3 Triển khai có kiểm soát & Quay lại phiên bản trước

Việc triển khai mô hình phải được kiểm soát, giám sát và có thể hoàn tác.

 #3.3.1    Level: 1    Role: D
 Xác nhận rằng các triển khai sản xuất thực hiện các cơ chế triển khai dần (triển khai canary, triển khai xanh-lam) với các kích hoạt hoàn tác tự động dựa trên các tỷ lệ lỗi, ngưỡng độ trễ, hoặc tiêu chí cảnh báo bảo mật đã thỏa thuận trước.
 #3.3.2    Level: 1    Role: D/V
 Xác minh rằng khả năng khôi phục lại trạng thái mô hình hoàn chỉnh (trọng số, cấu hình, phụ thuộc) được thực hiện nguyên tử trong các cửa sổ thời gian tổ chức được xác định trước.
 #3.3.3    Level: 2    Role: D/V
 Xác minh rằng các quy trình triển khai xác thực chữ ký mật mã và tính toán kiểm tra tổng kiểm tra toàn vẹn trước khi kích hoạt mô hình, và ngừng triển khai nếu phát hiện bất kỳ sự không khớp nào.
 #3.3.4    Level: 2    Role: D/V
 Xác minh rằng các chức năng tắt mô hình khẩn cấp có thể vô hiệu hóa các điểm cuối mô hình trong khoảng thời gian phản hồi đã được xác định trước thông qua các bộ ngắt mạch tự động hoặc công tắc tắt thủ công.
 #3.3.5    Level: 2    Role: V
 Xác minh rằng các bản ghi phục hồi (phiên bản mô hình trước, cấu hình, phụ thuộc) được giữ lại theo chính sách tổ chức với bộ lưu trữ không thể thay đổi để phản ứng sự cố.

---

### C3.4 Thay đổi Trách nhiệm và Kiểm toán

Tất cả các thay đổi trong vòng đời mô hình phải có khả năng truy vết và kiểm toán.

 #3.4.1    Level: 1    Role: V
 Xác minh rằng tất cả các thay đổi mô hình (triển khai, cấu hình, ngừng sử dụng) đều tạo ra các bản ghi kiểm tra không thể thay đổi bao gồm dấu thời gian, danh tính tác nhân được xác thực, loại thay đổi và trạng thái trước/sau.
 #3.4.2    Level: 2    Role: D/V
 Xác minh rằng việc truy cập nhật ký kiểm toán yêu cầu có sự ủy quyền thích hợp và tất cả các lần cố gắng truy cập đều được ghi lại với danh tính người dùng và dấu thời gian.
 #3.4.3    Level: 2    Role: D/V
 Xác minh rằng các mẫu prompt và tin nhắn hệ thống được quản lý phiên bản trong các kho git với việc xem xét mã bắt buộc và phê duyệt từ các người đánh giá được chỉ định trước khi triển khai.
 #3.4.4    Level: 2    Role: V
 Xác minh rằng các bản ghi kiểm toán bao gồm đủ chi tiết (băm mô hình, ảnh chụp cấu hình, phiên bản phụ thuộc) để cho phép tái tạo hoàn chỉnh trạng thái mô hình cho bất kỳ mốc thời gian nào trong khoảng thời gian lưu giữ.

---

### C3.5 Thực hành phát triển an toàn

Quy trình phát triển và đào tạo mô hình phải tuân theo các thực hành an toàn để ngăn chặn việc bị xâm phạm.

 #3.5.1    Level: 1    Role: D
 Xác minh rằng các môi trường phát triển mô hình, thử nghiệm và sản xuất được tách biệt vật lý hoặc logic. Chúng không sử dụng hạ tầng chung, có kiểm soát truy cập riêng biệt và lưu trữ dữ liệu cô lập.
 #3.5.2    Level: 1    Role: D
 Xác minh rằng việc đào tạo và tinh chỉnh mô hình diễn ra trong các môi trường tách biệt với quyền truy cập mạng được kiểm soát.
 #3.5.3    Level: 1    Role: D/V
 Xác minh rằng nguồn dữ liệu huấn luyện đã được kiểm tra tính toàn vẹn và xác thực thông qua các nguồn đáng tin cậy với chuỗi lưu giữ tài liệu trước khi sử dụng trong phát triển mô hình.
 #3.5.4    Level: 2    Role: D
 Xác minh rằng các sản phẩm phát triển mô hình (siêu tham số, kịch bản huấn luyện, tập tin cấu hình) được lưu trữ trong hệ thống quản lý phiên bản và yêu cầu phê duyệt đánh giá đồng nghiệp trước khi sử dụng trong quá trình huấn luyện.

---

### C3.6 Ngừng sử dụng và loại bỏ mô hình

Các mô hình phải được gỡ bỏ một cách an toàn khi không còn cần thiết hoặc khi các vấn đề về bảo mật được phát hiện.

 #3.6.1    Level: 1    Role: D
 Xác nhận rằng quy trình nghỉ hưu mô hình tự động quét đồ thị phụ thuộc, xác định tất cả các hệ thống tiêu thụ, và cung cấp thời gian thông báo trước đã được thỏa thuận trước khi ngừng hoạt động.
 #3.6.2    Level: 1    Role: D/V
 Xác minh rằng các hiện vật mô hình đã nghỉ hưu được xóa sạch một cách an toàn bằng cách sử dụng xóa mật mã hoặc ghi đè đa lần theo chính sách giữ dữ liệu được tài liệu hóa kèm theo các chứng nhận hủy tài liệu đã được xác minh.
 #3.6.3    Level: 2    Role: V
 Xác minh rằng các sự kiện nghỉ hưu mô hình được ghi lại với dấu thời gian và danh tính người thực hiện, và chữ ký mô hình bị thu hồi để ngăn chặn việc sử dụng lại.
 #3.6.4    Level: 2    Role: D/V
 Xác minh rằng việc nghỉ hưu mô hình khẩn cấp có thể vô hiệu hóa quyền truy cập mô hình trong phạm vi thời gian phản ứng khẩn cấp đã được thiết lập trước thông qua các công tắc tắt tự động nếu phát hiện ra các lỗ hổng bảo mật nghiêm trọng.

---

### Tài liệu tham khảo

MLOps Principles
Securing AI/ML Ops – Cisco.com
Audit logs security: cryptographically signed tamper-proof logs
Machine Learning Model Versioning: Top Tools & Best Practices
AI Hygiene Starts with Models and Data Loaders – SEI Blog
How to handle versioning and rollback of a deployed ML model?
Reinforcement fine-tuning – OpenAI API
Auditing Machine Learning models: Governance, Data Security and …
Adversarial Training to Improve Model Robustness
What is AI adversarial robustness? – IBM Research
Exploring Data Provenance: Ensuring Data Integrity and Authenticity
MITRE ATLAS
AWS Prescriptive Guidance – Best practices for retiring applications …

## Bảo mật Hạ tầng, Cấu hình và Triển khai C4

### Mục tiêu Kiểm soát

Hạ tầng AI phải được củng cố để chống lại việc leo thang đặc quyền, can thiệp chuỗi cung ứng, và di chuyển ngang thông qua cấu hình bảo mật, cách ly trong thời gian chạy, quy trình triển khai tin cậy, và giám sát toàn diện. Chỉ có các thành phần và cấu hình hạ tầng được ủy quyền, xác thực mới được đưa vào sản xuất thông qua các quy trình kiểm soát đảm bảo an ninh, tính toàn vẹn, và khả năng kiểm tra.

Mục tiêu bảo mật cốt lõi: Chỉ các thành phần hạ tầng được ký mật mã và quét lỗ hổng mới được đưa vào môi trường sản xuất thông qua các đường ống kiểm tra tự động, đảm bảo thực thi chính sách bảo mật và duy trì các bản ghi kiểm toán không thể thay đổi.

---

### C4.1 Cô lập Môi trường Chạy thời gian

Ngăn chặn việc thoát khỏi container và leo thang đặc quyền thông qua các nguyên thủy cách ly ở cấp nhân và các kiểm soát truy cập bắt buộc.

 #4.1.1    Level: 1    Role: D/V
 Xác minh rằng tất cả các container AI loại bỏ TẤT CẢ các quyền hạn Linux ngoại trừ CAP_SETUID, CAP_SETGID và các quyền hạn được yêu cầu rõ ràng đã được ghi chép trong các tiêu chuẩn bảo mật.
 #4.1.2    Level: 1    Role: D/V
 Xác minh rằng các hồ sơ seccomp chặn tất cả các syscall ngoại trừ những syscall có trong danh sách cho phép đã được phê duyệt trước, với các vi phạm sẽ kết thúc container và tạo ra các cảnh báo bảo mật.
 #4.1.3    Level: 2    Role: D/V
 Xác minh rằng các khối lượng công việc AI chạy với hệ thống tập tin gốc chỉ đọc, tmpfs cho dữ liệu tạm thời, và các ổ đĩa được đặt tên cho dữ liệu bền với tùy chọn gắn noexec được thực thi.
 #4.1.4    Level: 2    Role: D/V
 Xác minh rằng việc giám sát thời gian thực dựa trên eBPF (Falco, Tetragon hoặc tương đương) phát hiện các cố gắng leo thang đặc quyền và tự động chấm dứt các tiến trình vi phạm trong thời gian đáp ứng yêu cầu của tổ chức.
 #4.1.5    Level: 3    Role: D/V
 Xác minh rằng các khối lượng công việc AI có nguy cơ cao được thực thi trong môi trường cách ly phần cứng (Intel TXT, AMD SVM hoặc các nút bare-metal chuyên dụng) với việc xác thực chứng nhận.

---

### C4.2 Đường ống Xây dựng & Triển khai An toàn

Đảm bảo tính toàn vẹn mật mã và an ninh chuỗi cung ứng thông qua các bản build có thể tái tạo và các sản phẩm được ký số.

 #4.2.1    Level: 1    Role: D/V
 Xác minh rằng hạ tầng dưới dạng mã được quét bằng công cụ (tfsec, Checkov hoặc Terrascan) trên mỗi lần commit, chặn các lần hợp nhất có phát hiện mức độ nghiêm trọng CAO hoặc NGHIÊM TRỌNG.
 #4.2.2    Level: 1    Role: D/V
 Xác minh rằng việc xây dựng container có thể tái tạo với các hàm băm SHA256 giống hệt nhau giữa các lần xây dựng và tạo các chứng nhận nguồn gốc SLSA Cấp độ 3 được ký bằng Sigstore.
 #4.2.3    Level: 2    Role: D/V
 Xác minh rằng các hình ảnh container nhúng CycloneDX hoặc SPDX SBOM và được ký bằng Cosign trước khi đẩy lên registry, với các hình ảnh chưa ký bị từ chối khi triển khai.
 #4.2.4    Level: 2    Role: D/V
 Xác minh rằng các pipeline CI/CD sử dụng token OIDC từ HashiCorp Vault, vai trò IAM của AWS, hoặc Azure Managed Identity với thời gian tồn tại không vượt quá giới hạn chính sách bảo mật tổ chức.
 #4.2.5    Level: 2    Role: D/V
 Xác minh rằng các chữ ký Cosign và nguồn gốc SLSA được kiểm tra hợp lệ trong quá trình triển khai trước khi thực thi container và các lỗi xác minh sẽ khiến việc triển khai bị thất bại.
 #4.2.6    Level: 2    Role: D/V
 Xác minh rằng các môi trường xây dựng chạy trong các container hoặc máy ảo tạm thời không có lưu trữ lâu dài và được cách ly mạng khỏi các VPC sản xuất.

---

### C4.3 An ninh Mạng & Kiểm soát Truy cập

Triển khai mạng không tin cậy với các chính sách từ chối mặc định và truyền thông được mã hóa.

 #4.3.1    Level: 1    Role: D/V
 Xác minh rằng Kubernetes NetworkPolicies hoặc bất kỳ giải pháp tương đương nào thực hiện việc từ chối mặc định đối với ingress/egress với các quy tắc cho phép rõ ràng cho các cổng cần thiết (443, 8080, v.v.).
 #4.3.2    Level: 1    Role: D/V
 Xác minh rằng SSH (cổng 22), RDP (cổng 3389) và các điểm cuối metadata đám mây (169.254.169.254) bị chặn hoặc yêu cầu xác thực dựa trên chứng chỉ.
 #4.3.3    Level: 2    Role: D/V
 Xác minh rằng lưu lượng ra được lọc qua các proxy HTTP/HTTPS (Squid, Istio hoặc các cổng NAT đám mây) với danh sách cho phép theo miền và các yêu cầu bị chặn được ghi nhật ký.
 #4.3.4    Level: 2    Role: D/V
 Xác minh rằng giao tiếp giữa các dịch vụ sử dụng TLS hai chiều với các chứng chỉ được luân chuyển theo chính sách tổ chức và việc xác thực chứng chỉ được thực thi (không sử dụng cờ bỏ qua xác minh).
 #4.3.5    Level: 2    Role: D/V
 Xác minh rằng hạ tầng AI hoạt động trong các VPC/VNet riêng biệt không có truy cập internet trực tiếp và chỉ giao tiếp qua các gateway NAT hoặc máy chủ trung gian (bastion hosts).

---

### C4.4 Quản lý Bí mật & Khóa Mã hóa

Bảo vệ thông tin đăng nhập thông qua lưu trữ được hỗ trợ phần cứng và xoay vòng tự động với truy cập không tin cậy.

 #4.4.1    Level: 1    Role: D/V
 Xác minh rằng các bí mật được lưu trữ trong HashiCorp Vault, AWS Secrets Manager, Azure Key Vault, hoặc Google Secret Manager với mã hóa khi lưu trữ sử dụng AES-256.
 #4.4.2    Level: 1    Role: D/V
 Xác minh rằng các khóa mật mã được tạo ra trong các thiết bị HSM đạt chuẩn FIPS 140-2 Cấp 2 (AWS CloudHSM, Azure Dedicated HSM) với việc xoay vòng khóa theo chính sách mật mã của tổ chức.
 #4.4.3    Level: 2    Role: D/V
 Xác nhận rằng việc xoay vòng bí mật được tự động hóa với triển khai không gián đoạn cùng với việc xoay vòng ngay lập tức được kích hoạt bởi các thay đổi nhân sự hoặc sự cố an ninh.
 #4.4.4    Level: 2    Role: D/V
 Xác minh rằng các ảnh container được quét bằng các công cụ (GitLeaks, TruffleHog hoặc detect-secrets) để chặn các bản build chứa khóa API, mật khẩu hoặc chứng chỉ.
 #4.4.5    Level: 2    Role: D/V
 Xác minh rằng việc truy cập bí mật sản xuất yêu cầu MFA với các token phần cứng (YubiKey, FIDO2) và được ghi lại bởi các nhật ký kiểm toán không thể thay đổi với danh tính người dùng và dấu thời gian.
 #4.4.6    Level: 2    Role: D/V
 Xác minh rằng các bí mật được tiêm qua Kubernetes secrets, các volume được gắn kết hoặc các init container và đảm bảo rằng bí mật không bao giờ được nhúng trong biến môi trường hoặc hình ảnh.

---

### C4.5 Phân vùng tải công việc AI và Xác thực

Cô lập các mô hình AI không đáng tin cậy trong các hộp cát an toàn với phân tích hành vi toàn diện.

 #4.5.1    Level: 1    Role: D/V
 Xác nhận rằng các mô hình AI bên ngoài thực thi trong gVisor, microVMs (chẳng hạn như Firecracker, CrossVM) hoặc các container Docker với các cờ --security-opt=no-new-privileges và --read-only.
 #4.5.2    Level: 1    Role: D/V
 Xác nhận rằng các môi trường sandbox không có kết nối mạng (--network=none) hoặc chỉ truy cập localhost với tất cả các yêu cầu bên ngoài bị chặn bởi quy tắc iptables.
 #4.5.3    Level: 2    Role: D/V
 Xác minh rằng việc xác nhận mô hình AI bao gồm kiểm tra nhóm đỏ tự động với phạm vi kiểm tra được tổ chức xác định và phân tích hành vi để phát hiện cửa hậu.
 #4.5.4    Level: 2    Role: D/V
 Xác minh rằng trước khi một mô hình AI được đưa vào sản xuất, kết quả trong môi trường thử nghiệm (sandbox) của nó được ký số bằng mật mã bởi nhân sự an ninh được ủy quyền và được lưu trữ trong các nhật ký kiểm tra không thể thay đổi.
 #4.5.5    Level: 2    Role: D/V
 Xác minh rằng các môi trường sandbox được hủy và tái tạo từ hình ảnh gốc giữa các lần đánh giá với việc làm sạch hoàn toàn hệ thống tập tin và bộ nhớ.

---

### C4.6 Giám sát An ninh Hạ tầng

Liên tục quét và giám sát hạ tầng với khắc phục tự động và cảnh báo thời gian thực.

 #4.6.1    Level: 1    Role: D/V
 Xác minh rằng các ảnh container được quét theo lịch trình của tổ chức với các lỗ hổng NGHIÊM TRỌNG (CRITICAL) ngăn chặn việc triển khai dựa trên các ngưỡng rủi ro của tổ chức.
 #4.6.2    Level: 1    Role: D/V
 Xác minh rằng hạ tầng đáp ứng các tiêu chuẩn CIS Benchmarks hoặc các kiểm soát NIST 800-53 với các ngưỡng tuân thủ do tổ chức xác định và tự động xử lý khắc phục cho các kiểm tra không đạt.
 #4.6.3    Level: 2    Role: D/V
 Xác minh rằng các lỗ hổng có mức độ nghiêm trọng CAO được vá theo các mốc thời gian quản lý rủi ro của tổ chức với các quy trình khẩn cấp cho các CVE đang bị khai thác tích cực.
 #4.6.4    Level: 2    Role: V
 Xác minh rằng các cảnh báo bảo mật tích hợp với các nền tảng SIEM (Splunk, Elastic hoặc Sentinel) sử dụng định dạng CEF hoặc STIX/TAXII với việc làm giàu tự động.
 #4.6.5    Level: 3    Role: V
 Xác minh rằng các chỉ số hạ tầng được xuất khẩu tới hệ thống giám sát (Prometheus, DataDog) với bảng điều khiển SLA và báo cáo dành cho lãnh đạo.
 #4.6.6    Level: 2    Role: D/V
 Xác minh rằng sự sai lệch cấu hình được phát hiện bằng cách sử dụng các công cụ (Chef InSpec, AWS Config) theo yêu cầu giám sát của tổ chức với khả năng hoàn tác tự động đối với các thay đổi không được phép.

---

### C4.7 Quản lý Tài nguyên Hạ tầng AI

Ngăn chặn các cuộc tấn công làm cạn kiệt tài nguyên và đảm bảo phân bổ tài nguyên công bằng thông qua hạn ngạch và giám sát.

 #4.7.1    Level: 1    Role: D/V
 Xác minh rằng việc sử dụng GPU/TPU được giám sát với cảnh báo được kích hoạt tại các ngưỡng được tổ chức xác định và tự động mở rộng hoặc cân bằng tải được kích hoạt dựa trên các chính sách quản lý công suất.
 #4.7.2    Level: 1    Role: D/V
 Xác minh rằng các chỉ số khối lượng công việc AI (độ trễ suy luận, thông lượng, tỷ lệ lỗi) được thu thập theo yêu cầu giám sát của tổ chức và được đối chiếu với việc sử dụng hạ tầng.
 #4.7.3    Level: 2    Role: D/V
 Xác minh rằng Kubernetes ResourceQuotas hoặc các cơ chế tương đương giới hạn từng workload theo chính sách phân bổ tài nguyên của tổ chức với các giới hạn cứng được thực thi.
 #4.7.4    Level: 2    Role: V
 Xác minh rằng việc giám sát chi phí theo dõi chi tiêu theo từng khối lượng công việc/người thuê với các cảnh báo dựa trên ngưỡng ngân sách tổ chức và các kiểm soát tự động để ngăn ngừa vượt ngân sách.
 #4.7.5    Level: 3    Role: V
 Xác minh rằng lập kế hoạch dung lượng sử dụng dữ liệu lịch sử với các khoảng thời gian dự báo được tổ chức xác định và cung cấp tài nguyên tự động dựa trên các mẫu nhu cầu.
 #4.7.6    Level: 2    Role: D/V
 Xác minh rằng việc cạn kiệt tài nguyên kích hoạt các công tắc ngắt theo yêu cầu phản hồi của tổ chức, bao gồm giới hạn tốc độ dựa trên chính sách năng lực và cô lập khối lượng công việc.

---

### C4.8 Kiểm soát Tách biệt Môi trường & Thúc đẩy

Thiết lập ranh giới môi trường nghiêm ngặt với các cổng thăng tiến tự động và xác thực bảo mật.

 #4.8.1    Level: 1    Role: D/V
 Xác minh rằng các môi trường phát triển/kiểm thử/sản xuất chạy trong các VPC/VNet riêng biệt mà không có vai trò IAM, nhóm bảo mật hoặc kết nối mạng dùng chung.
 #4.8.2    Level: 1    Role: D/V
 Xác nhận rằng việc thăng môi trường yêu cầu phê duyệt từ nhân sự được tổ chức xác định có thẩm quyền, kèm theo chữ ký mật mã và nhật ký kiểm toán không thể thay đổi.
 #4.8.3    Level: 2    Role: D/V
 Xác nhận rằng các môi trường sản xuất chặn truy cập SSH, vô hiệu hóa các điểm cuối gỡ lỗi và yêu cầu các yêu cầu thay đổi kèm theo thông báo trước theo quy định của tổ chức, ngoại trừ các trường hợp khẩn cấp.
 #4.8.4    Level: 2    Role: D/V
 Xác minh rằng các thay đổi hạ tầng dưới dạng mã yêu cầu phải được đồng nghiệp xem xét kèm kiểm thử tự động và quét bảo mật trước khi gộp vào nhánh chính.
 #4.8.5    Level: 2    Role: D/V
 Xác minh rằng dữ liệu không thuộc môi trường sản xuất được ẩn danh theo các yêu cầu bảo mật của tổ chức, tạo dữ liệu tổng hợp hoặc che dấu dữ liệu hoàn toàn với việc loại bỏ thông tin cá nhân nhận dạng (PII) đã được kiểm chứng.
 #4.8.6    Level: 2    Role: D/V
 Xác minh rằng các cổng thăng tiến bao gồm các bài kiểm tra bảo mật tự động (SAST, DAST, quét container) với yêu cầu không có phát hiện CRITICAL để được phê duyệt.

---

### Sao lưu & Phục hồi Cơ sở hạ tầng C4.9

Đảm bảo độ bền vững của hạ tầng thông qua các bản sao lưu tự động, quy trình khôi phục đã được kiểm tra và khả năng phục hồi sau thảm họa.

 #4.9.1    Level: 1    Role: D/V
 Xác minh rằng các cấu hình hạ tầng được sao lưu theo lịch sao lưu của tổ chức tới các khu vực địa lý tách biệt, với việc triển khai chiến lược sao lưu 3-2-1.
 #4.9.2    Level: 2    Role: D/V
 Xác minh rằng các hệ thống sao lưu hoạt động trong mạng riêng biệt với thông tin xác thực riêng và lưu trữ cách ly để bảo vệ chống lại ransomware.
 #4.9.3    Level: 2    Role: V
 Xác minh rằng các thủ tục phục hồi được kiểm tra và xác nhận thông qua kiểm thử tự động theo lịch trình tổ chức với các mục tiêu RTO và RPO đáp ứng yêu cầu của tổ chức.
 #4.9.4    Level: 3    Role: V
 Xác minh rằng khôi phục sau thảm họa bao gồm các sách hướng dẫn chạy riêng cho AI với việc phục hồi trọng số mô hình, xây dựng lại cụm GPU và bản đồ phụ thuộc dịch vụ.

---

### C4.10 Tuân thủ và Quản trị Hạ tầng

Duy trì tuân thủ quy định thông qua đánh giá liên tục, ghi chép và kiểm soát tự động hóa.

 #4.10.1    Level: 2    Role: D/V
 Xác minh rằng việc tuân thủ hạ tầng được đánh giá theo lịch trình tổ chức dựa trên các kiểm soát SOC 2, ISO 27001 hoặc FedRAMP với việc thu thập bằng chứng tự động.
 #4.10.2    Level: 2    Role: V
 Xác minh rằng tài liệu hạ tầng bao gồm sơ đồ mạng, bản đồ luồng dữ liệu và mô hình đe dọa được cập nhật theo các yêu cầu quản lý thay đổi tổ chức.
 #4.10.3    Level: 3    Role: D/V
 Xác minh rằng các thay đổi cơ sở hạ tầng trải qua đánh giá tác động tuân thủ tự động với quy trình phê duyệt theo quy định cho các sửa đổi có rủi ro cao.

---

### C4.11 An ninh Phần cứng AI

Bảo mật các thành phần phần cứng đặc thù cho AI bao gồm GPU, TPU và các bộ tăng tốc AI chuyên dụng.

 #4.11.1    Level: 2    Role: D/V
 Xác minh rằng firmware bộ tăng tốc AI (BIOS GPU, firmware TPU) được xác thực bằng chữ ký mật mã và được cập nhật theo lịch trình quản lý bản vá của tổ chức.
 #4.11.2    Level: 2    Role: D/V
 Xác minh rằng trước khi thực hiện tải công việc, tính toàn vẹn của bộ tăng tốc AI được xác nhận bởi chứng thực phần cứng sử dụng TPM 2.0, Intel TXT hoặc AMD SVM.
 #4.11.3    Level: 2    Role: D/V
 Xác minh rằng bộ nhớ GPU được cô lập giữa các khối lượng công việc bằng cách sử dụng SR-IOV, MIG (GPU đa thể hiện), hoặc phân vùng phần cứng tương đương với việc làm sạch bộ nhớ giữa các tác vụ.
 #4.11.4    Level: 3    Role: V
 Xác minh rằng chuỗi cung ứng phần cứng AI bao gồm việc kiểm tra nguồn gốc bằng chứng chỉ từ nhà sản xuất và xác minh bao bì chống giả mạo.
 #4.11.5    Level: 3    Role: D/V
 Xác minh rằng các mô-đun bảo mật phần cứng (HSM) bảo vệ trọng số mô hình AI và khóa mật mã với chứng nhận FIPS 140-2 Cấp 3 hoặc Tiêu chí Chung EAL4+.

---

### C4.12 Cơ sở hạ tầng AI Biên & Phân tán

Triển khai AI phân tán an toàn bao gồm điện toán biên, học liên kết và kiến trúc đa địa điểm.

 #4.12.1    Level: 2    Role: D/V
 Xác minh rằng các thiết bị AI biên xác thực với hạ tầng trung tâm sử dụng mutual TLS với chứng chỉ thiết bị được xoay vòng theo chính sách quản lý chứng chỉ của tổ chức.
 #4.12.2    Level: 2    Role: D/V
 Xác minh rằng các thiết bị biên thực hiện cơ chế khởi động an toàn với chữ ký đã được xác minh và bảo vệ chống quay lui, ngăn chặn các cuộc tấn công hạ cấp phần mềm hệ thống.
 #4.12.3    Level: 3    Role: D/V
 Xác minh rằng sự phối hợp AI phân tán sử dụng các thuật toán đồng thuận chịu lỗi Byzantine với việc xác thực người tham gia và phát hiện nút độc hại.
 #4.12.4    Level: 3    Role: D/V
 Xác minh rằng giao tiếp từ edge đến cloud bao gồm điều tiết băng thông, nén dữ liệu và khả năng hoạt động ngoại tuyến với lưu trữ cục bộ an toàn.

---

### C4.13 An ninh Hạ tầng Đa Đám mây & Hỗn hợp

Bảo mật khối lượng công việc AI trên nhiều nhà cung cấp đám mây và triển khai đám mây lai kết hợp với tại chỗ.

 #4.13.1    Level: 2    Role: D/V
 Xác minh rằng các triển khai AI đa đám mây sử dụng liên kết danh tính không phụ thuộc vào nền tảng đám mây (OIDC, SAML) với quản lý chính sách tập trung trên các nhà cung cấp.
 #4.13.2    Level: 2    Role: D/V
 Xác minh rằng việc chuyển dữ liệu đa đám mây sử dụng mã hóa đầu cuối với khóa do khách hàng quản lý và các kiểm soát cư trú dữ liệu được thi hành theo từng khu vực pháp lý.
 #4.13.3    Level: 2    Role: D/V
 Xác minh rằng các khối lượng công việc AI đám mây lai thực hiện chính sách bảo mật nhất quán trên cả môi trường tại chỗ và đám mây với việc giám sát và cảnh báo thống nhất.
 #4.13.4    Level: 3    Role: V
 Xác minh rằng việc ngăn chặn khóa nhà cung cấp đám mây bao gồm cơ sở hạ tầng dưới dạng mã có thể di động, API chuẩn hóa và khả năng xuất dữ liệu với công cụ chuyển đổi định dạng.
 #4.13.5    Level: 3    Role: V
 Xác minh rằng tối ưu hóa chi phí đa đám mây bao gồm các biện pháp kiểm soát bảo mật ngăn chặn việc phân tán tài nguyên cũng như các khoản phí chuyển dữ liệu không được phép giữa các đám mây.

---

### C4.14 Tự động hóa Hạ tầng & Bảo mật GitOps

Tự động hóa các đường ống hạ tầng bảo mật và quy trình làm việc GitOps cho quản lý hạ tầng AI.

 #4.14.1    Level: 2    Role: D/V
 Xác minh rằng các kho GitOps yêu cầu các commit được ký bằng khóa GPG và áp dụng các quy tắc bảo vệ nhánh ngăn cấm đẩy trực tiếp vào các nhánh chính.
 #4.14.2    Level: 2    Role: D/V
 Xác minh rằng tự động hóa hạ tầng bao gồm phát hiện sai lệch với khả năng khắc phục tự động và hoàn tác được kích hoạt theo yêu cầu phản hồi của tổ chức đối với các thay đổi không được phép.
 #4.14.3    Level: 2    Role: D/V
 Xác minh rằng việc cung cấp hạ tầng tự động bao gồm xác thực chính sách bảo mật với việc chặn triển khai đối với các cấu hình không tuân thủ.
 #4.14.4    Level: 2    Role: D/V
 Xác minh rằng các bí mật tự động hóa hạ tầng được quản lý thông qua các bộ điều khiển bí mật bên ngoài (External Secrets Operator, Bank-Vaults) với việc xoay vòng tự động.
 #4.14.5    Level: 3    Role: V
 Xác minh rằng hạ tầng tự phục hồi bao gồm việc kết hợp sự kiện bảo mật với phản ứng sự cố tự động và quy trình thông báo các bên liên quan.

---

### C4.15 An ninh Hạ tầng Kháng Lượng tử

Chuẩn bị cơ sở hạ tầng AI để đối phó với các mối đe dọa từ máy tính lượng tử thông qua mật mã hậu lượng tử và các giao thức an toàn lượng tử.

 #4.15.1    Level: 3    Role: D/V
 Xác minh rằng cơ sở hạ tầng AI triển khai các thuật toán mật mã hậu lượng tử được NIST phê duyệt (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) cho trao đổi khóa và chữ ký số.
 #4.15.2    Level: 3    Role: D/V
 Xác minh rằng các hệ thống phân phối khóa lượng tử (QKD) được triển khai cho các liên lạc AI bảo mật cao với các giao thức quản lý khóa an toàn trước lượng tử.
 #4.15.3    Level: 3    Role: D/V
 Xác minh rằng các khung công tác linh hoạt mật mã cho phép di chuyển nhanh chóng sang các thuật toán hậu lượng tử mới với việc tự động xoay vòng chứng chỉ và khóa.
 #4.15.4    Level: 3    Role: V
 Xác minh rằng mô hình hóa mối đe dọa lượng tử đánh giá mức độ dễ tổn thương của cơ sở hạ tầng AI đối với các cuộc tấn công lượng tử cùng với các thời hạn di chuyển đã được ghi chép và các đánh giá rủi ro.
 #4.15.5    Level: 3    Role: D/V
 Xác minh rằng các hệ thống mật mã lai cổ điển-lượng tử cung cấp phương pháp phòng thủ đa lớp trong giai đoạn chuyển tiếp lượng tử với việc giám sát hiệu suất.

---

### C4.16 Tính Toán Bảo Mật & Khu Vực An Toàn

Bảo vệ khối lượng công việc AI và trọng số mô hình bằng cách sử dụng môi trường thực thi đáng tin cậy dựa trên phần cứng và công nghệ điện toán bảo mật.

 #4.16.1    Level: 3    Role: D/V
 Xác minh rằng các mô hình AI nhạy cảm được thực thi bên trong các vùng bảo vệ Intel SGX, AMD SEV-SNP hoặc ARM TrustZone với bộ nhớ được mã hóa và xác thực chứng nhận.
 #4.16.2    Level: 3    Role: D/V
 Xác minh rằng các container bảo mật (Kata Containers, gVisor với tính toán bảo mật) cách ly các khối lượng công việc AI bằng mã hóa bộ nhớ được thực thi phần cứng.
 #4.16.3    Level: 3    Role: D/V
 Xác minh rằng xác thực từ xa kiểm tra tính toàn vẹn của enclave trước khi tải các mô hình AI với bằng chứng mật mã về tính xác thực của môi trường thực thi.
 #4.16.4    Level: 3    Role: D/V
 Xác minh rằng các dịch vụ suy luận AI bảo mật ngăn chặn việc trích xuất mô hình thông qua tính toán mã hóa với trọng số mô hình được niêm phong và thực thi được bảo vệ.
 #4.16.5    Level: 3    Role: D/V
 Xác minh rằng việc điều phối môi trường thực thi tin cậy quản lý vòng đời khu vực bảo mật với xác thực từ xa và kênh truyền thông được mã hóa.
 #4.16.6    Level: 3    Role: D/V
 Xác minh rằng tính toán đa bên bảo mật (SMPC) cho phép đào tạo trí tuệ nhân tạo hợp tác mà không tiết lộ bộ dữ liệu cá nhân hoặc các tham số mô hình.

---

### C4.17 Cơ sở hạ tầng Không Kiến thức

Triển khai các hệ thống bằng chứng không tiết lộ kiến thức (zero-knowledge proof) để xác minh và chứng thực AI bảo vệ quyền riêng tư mà không tiết lộ thông tin nhạy cảm.

 #4.17.1    Level: 3    Role: D/V
 Xác minh rằng các bằng chứng không tiết lộ thông tin (ZK-SNARKs, ZK-STARKs) xác thực tính toàn vẹn của mô hình AI và nguồn gốc huấn luyện mà không làm lộ trọng số mô hình hoặc dữ liệu huấn luyện.
 #4.17.2    Level: 3    Role: D/V
 Xác minh rằng các hệ thống xác thực dựa trên ZK cho phép xác thực người dùng bảo vệ quyền riêng tư đối với các dịch vụ AI mà không tiết lộ thông tin liên quan đến danh tính.
 #4.17.3    Level: 3    Role: D/V
 Xác nhận rằng các giao thức giao điểm tập hợp riêng tư (PSI) cho phép khớp dữ liệu an toàn cho AI liên kết mà không làm lộ các bộ dữ liệu riêng lẻ.
 #4.17.4    Level: 3    Role: D/V
 Xác minh rằng các hệ thống học máy không tri thức (ZKML) cho phép suy luận AI có thể xác minh với bằng chứng mật mã về tính toán đúng đắn.
 #4.17.5    Level: 3    Role: D/V
 Xác minh rằng ZK-rollups cung cấp xử lý giao dịch AI có khả năng mở rộng và bảo vệ quyền riêng tư với việc xác minh theo lô và giảm tải tính toán.

---

### C4.18 Phòng chống tấn công kênh phụ

Bảo vệ hạ tầng AI khỏi các cuộc tấn công kênh bên dựa trên thời gian, năng lượng, điện từ và bộ nhớ đệm có thể làm rò rỉ thông tin nhạy cảm.

 #4.18.1    Level: 3    Role: D/V
 Xác minh rằng thời gian suy luận AI được chuẩn hóa bằng cách sử dụng các thuật toán thời gian không đổi và kỹ thuật đệm để ngăn chặn các cuộc tấn công trích xuất mô hình dựa trên thời gian.
 #4.18.2    Level: 3    Role: D/V
 Xác nhận rằng bảo vệ phân tích công suất bao gồm việc tiêm nhiễu, lọc đường nguồn và các mẫu thực thi ngẫu nhiên cho phần cứng AI.
 #4.18.3    Level: 3    Role: D/V
 Xác minh rằng biện pháp giảm thiểu kênh phụ dựa trên bộ nhớ đệm sử dụng phân vùng bộ nhớ đệm, ngẫu nhiên hóa và lệnh xóa để ngăn chặn rò rỉ thông tin.
 #4.18.4    Level: 3    Role: D/V
 Xác minh rằng bảo vệ phát xạ điện từ bao gồm che chắn, lọc tín hiệu và xử lý ngẫu nhiên để ngăn chặn các cuộc tấn công kiểu TEMPEST.
 #4.18.5    Level: 3    Role: D/V
 Xác minh rằng các biện pháp phòng chống kênh bên vi kiến trúc bao gồm các kiểm soát thực thi suy đoán và che giấu mẫu truy cập bộ nhớ.

---

### C4.19 Bảo mật Phần cứng AI Chuyên biệt & Nhận dạng thần kinh

Bảo mật các kiến trúc phần cứng AI mới nổi bao gồm chip thần kinh (neuromorphic), FPGA, ASIC tùy chỉnh và hệ thống tính toán quang học.

 #4.19.1    Level: 3    Role: D/V
 Xác nhận rằng bảo mật chip neuromorphic bao gồm mã hóa mẫu xung, bảo vệ trọng số kết nối synaptic và xác thực quy tắc học dựa trên phần cứng.
 #4.19.2    Level: 3    Role: D/V
 Xác minh rằng các bộ tăng tốc AI dựa trên FPGA thực hiện mã hóa luồng bit, cơ chế chống giả mạo và tải cấu hình an toàn với các bản cập nhật có xác thực.
 #4.19.3    Level: 3    Role: D/V
 Xác minh rằng bảo mật ASIC tùy chỉnh bao gồm các bộ xử lý bảo mật trên chip, gốc tin cậy phần cứng và lưu trữ khóa an toàn với khả năng phát hiện xâm nhập.
 #4.19.4    Level: 3    Role: D/V
 Xác minh rằng các hệ thống tính toán quang học thực hiện mã hóa quang học an toàn trước lượng tử, chuyển mạch quang tử bảo mật và xử lý tín hiệu quang được bảo vệ.
 #4.19.5    Level: 3    Role: D/V
 Xác nhận rằng các chip AI lai analog-kỹ thuật số bao gồm tính toán analog an toàn, lưu trữ trọng số được bảo vệ và chuyển đổi analog-số được xác thực.

---

### C4.20 Cơ sở hạ tầng tính toán bảo vệ quyền riêng tư

Triển khai các biện pháp kiểm soát hạ tầng cho tính toán bảo vệ quyền riêng tư để bảo vệ dữ liệu nhạy cảm trong quá trình xử lý và phân tích AI.

 #4.20.1    Level: 3    Role: D/V
 Xác minh rằng hạ tầng mã hóa đồng dạng cho phép tính toán trên dữ liệu mã hóa đối với các khối lượng công việc AI nhạy cảm với việc xác minh tính toàn vẹn mật mã và giám sát hiệu suất.
 #4.20.2    Level: 3    Role: D/V
 Xác minh rằng các hệ thống truy xuất thông tin riêng tư cho phép truy vấn cơ sở dữ liệu mà không tiết lộ mẫu truy vấn thông qua bảo vệ mật mã đối với các mẫu truy cập.
 #4.20.3    Level: 3    Role: D/V
 Xác minh rằng các giao thức tính toán đa bên bảo mật cho phép suy luận AI bảo vệ quyền riêng tư mà không tiết lộ các đầu vào cá nhân hoặc các phép tính trung gian.
 #4.20.4    Level: 3    Role: D/V
 Xác minh rằng quản lý khóa bảo vệ quyền riêng tư bao gồm tạo khóa phân tán, mật mã ngưỡng, và xoay khóa an toàn với bảo vệ được hỗ trợ phần cứng.
 #4.20.5    Level: 3    Role: D/V
 Xác minh rằng hiệu suất tính toán bảo vệ quyền riêng tư được tối ưu hóa thông qua việc nhóm lệnh, lưu trữ tạm thời và tăng tốc phần cứng trong khi vẫn duy trì các đảm bảo bảo mật mật mã.

---

### C4.15 Bảo mật Tích hợp Đám mây Khung Đại lý & Triển khai Hỗn hợp

Các biện pháp kiểm soát bảo mật cho các khung tác nhân tích hợp đám mây với kiến trúc lai tại chỗ/đám mây.

 #4.15.1    Level: 1    Role: D/V
 Xác minh rằng tích hợp lưu trữ đám mây sử dụng mã hóa đầu cuối với quản lý khóa do đại lý kiểm soát.
 #4.15.2    Level: 2    Role: D/V
 Xác minh rằng các ranh giới bảo mật của triển khai lai được xác định rõ ràng với các kênh truyền thông được mã hóa.
 #4.15.3    Level: 2    Role: D/V
 Xác minh rằng việc truy cập tài nguyên đám mây bao gồm xác thực không tin cậy (zero-trust) với xác thực liên tục.
 #4.15.4    Level: 3    Role: D/V
 Xác minh rằng các yêu cầu về cư trú dữ liệu được thực thi thông qua xác nhận mật mã về vị trí lưu trữ.
 #4.15.5    Level: 3    Role: D/V
 Xác minh rằng các đánh giá bảo mật của nhà cung cấp đám mây bao gồm mô hình hóa mối đe dọa cụ thể cho tác nhân và đánh giá rủi ro.

---

### Tài liệu tham khảo

NIST Cybersecurity Framework 2.0
CIS Controls v8
OWASP Container Security Verification Standard
Kubernetes Security Best Practices
SLSA Supply Chain Security Framework
NIST SP 800-190: Application Container Security Guide
Cloud Security Alliance: Cloud Controls Matrix
ENISA: Secure Infrastructure Design
NIST SP 800-53: Security Controls for Federal Information Systems
ISO 27001:2022 Information Security Management
NIST AI Risk Management Framework
CIS Kubernetes Benchmark
FIPS 140-2 Security Requirements
NIST SP 800-207: Zero Trust Architecture
IEEE 2857: Privacy Engineering for AI Systems
NIST SP 800-161: Cybersecurity Supply Chain Risk Management
NIST Post-Quantum Cryptography Standards
Intel SGX Developer Guide
AMD SEV-SNP White Paper
ARM TrustZone Technology
ZK-SNARKs: A Gentle Introduction
NIST SP 800-57: Cryptographic Key Management
Side-Channel Attack Countermeasures
Neuromorphic Computing Security Challenges
FPGA Security: Fundamentals, Evaluation, and Countermeasures
Microsoft SEAL: Homomorphic Encryption Library
HElib: Homomorphic Encryption Library
PALISADE Lattice Cryptography Library
Differential Privacy: A Survey of Results
Secure Aggregation for Federated Learning
Private Information Retrieval: Concepts and Constructions

## Kiểm soát truy cập C5 & Nhận diện cho các thành phần và người dùng AI

### Mục tiêu Kiểm soát

Kiểm soát truy cập hiệu quả cho các hệ thống AI đòi hỏi quản lý định danh vững chắc, cấp phép dựa trên ngữ cảnh và thực thi trong thời gian chạy theo các nguyên tắc không tin cậy. Các biện pháp kiểm soát này đảm bảo rằng con người, dịch vụ và các tác nhân tự động chỉ tương tác với mô hình, dữ liệu và tài nguyên tính toán trong phạm vi được cấp phép rõ ràng, đồng thời có khả năng xác minh liên tục và kiểm tra.

---

### C5.1 Quản lý Danh tính & Xác thực

Thiết lập danh tính được bảo vệ bằng mật mã cho tất cả các thực thể với xác thực đa yếu tố cho các thao tác đặc quyền.

 #5.1.1    Level: 1    Role: D/V
 Xác minh rằng tất cả người dùng là con người và các nguyên tắc dịch vụ đều xác thực thông qua nhà cung cấp danh tính doanh nghiệp tập trung (IdP) sử dụng các giao thức OIDC/SAML với ánh xạ nhận dạng thành token duy nhất (không dùng chung tài khoản hoặc thông tin đăng nhập).
 #5.1.2    Level: 1    Role: D/V
 Xác minh rằng các hoạt động có rủi ro cao (triển khai mô hình, xuất trọng số, truy cập dữ liệu huấn luyện, thay đổi cấu hình sản xuất) yêu cầu xác thực đa yếu tố hoặc xác thực nâng cao kèm theo xác thực lại phiên.
 #5.1.3    Level: 2    Role: D
 Xác minh rằng các cán bộ mới trải qua việc xác minh danh tính phù hợp với tiêu chuẩn NIST 800-63-3 IAL-2 hoặc các tiêu chuẩn tương đương trước khi được cấp quyền truy cập hệ thống sản xuất.
 #5.1.4    Level: 2    Role: V
 Xác minh rằng các đánh giá truy cập được thực hiện hàng quý với việc phát hiện tự động các tài khoản không hoạt động, thực thi xoay vòng thông tin đăng nhập, và quy trình hủy cấp quyền.
 #5.1.5    Level: 3    Role: D/V
 Xác minh rằng các đại lý AI liên kết xác thực thông qua các khẳng định JWT được ký có thời hạn tối đa là 24 giờ và bao gồm bằng chứng mật mã về nguồn gốc.

---

### C5.2 Ủy quyền Tài nguyên & Nguyên tắc Quyền Hạn Tối Thiểu

Triển khai kiểm soát truy cập chi tiết cho tất cả các tài nguyên AI với mô hình cấp phép rõ ràng và dấu vết kiểm toán.

 #5.2.1    Level: 1    Role: D/V
 Xác minh rằng mọi tài nguyên AI (bộ dữ liệu, mô hình, điểm cuối, bộ sưu tập vector, chỉ mục nhúng, các phiên bản tính toán) đều thực thi kiểm soát truy cập dựa trên vai trò với danh sách cho phép rõ ràng và chính sách từ chối mặc định.
 #5.2.2    Level: 1    Role: D/V
 Xác nhận rằng các nguyên tắc quyền tối thiểu được thực thi theo mặc định với các tài khoản dịch vụ, bắt đầu với quyền chỉ đọc và yêu cầu có tài liệu chứng minh lý do kinh doanh cho quyền ghi.
 #5.2.3    Level: 1    Role: V
 Xác minh rằng tất cả các sửa đổi kiểm soát truy cập đều được liên kết với các yêu cầu thay đổi đã được phê duyệt và được ghi lại một cách bất biến với dấu thời gian, danh tính người thực hiện, định danh tài nguyên và sự thay đổi về quyền hạn.
 #5.2.4    Level: 2    Role: D
 Xác minh rằng các nhãn phân loại dữ liệu (PII, PHI, kiểm soát xuất khẩu, quyền sở hữu) tự động lan truyền đến các tài nguyên được tạo ra (nhúng, bộ nhớ đệm đề xuất, đầu ra mô hình) với việc thực thi chính sách nhất quán.
 #5.2.5    Level: 2    Role: D/V
 Xác minh rằng các lần cố gắng truy cập trái phép và sự kiện leo thang đặc quyền kích hoạt cảnh báo thời gian thực với siêu dữ liệu ngữ cảnh gửi đến hệ thống SIEM trong vòng 5 phút.

---

### C5.3 Đánh giá Chính sách Động

Triển khai các công cụ kiểm soát truy cập dựa trên thuộc tính (ABAC) để đưa ra các quyết định cấp quyền dựa trên ngữ cảnh với khả năng kiểm toán.

 #5.3.1    Level: 1    Role: D/V
 Xác minh rằng các quyết định ủy quyền được tách ra ngoài và xử lý bởi một bộ máy chính sách chuyên dụng (OPA, Cedar hoặc tương đương) có thể truy cập qua các API được xác thực với bảo vệ toàn vẹn bằng mật mã.
 #5.3.2    Level: 1    Role: D/V
 Xác minh rằng các chính sách đánh giá các thuộc tính động tại thời điểm chạy bao gồm mức độ được phép của người dùng, phân loại độ nhạy cảm của tài nguyên, ngữ cảnh yêu cầu, sự cô lập giữa các khách thuê, và các giới hạn thời gian.
 #5.3.3    Level: 2    Role: D
 Xác nhận rằng các định nghĩa chính sách được quản lý phiên bản, đánh giá bởi đồng nghiệp và được xác thực thông qua kiểm thử tự động trong các pipeline CI/CD trước khi triển khai vào môi trường sản xuất.
 #5.3.4    Level: 2    Role: V
 Xác minh rằng kết quả đánh giá chính sách bao gồm các lý do quyết định có cấu trúc và được truyền đến các hệ thống SIEM để phân tích tương quan và báo cáo tuân thủ.
 #5.3.5    Level: 3    Role: D/V
 Xác minh rằng giá trị thời gian sống trong bộ nhớ đệm chính sách (TTL) không vượt quá 5 phút đối với các tài nguyên nhạy cảm cao và 1 giờ đối với các tài nguyên tiêu chuẩn có khả năng làm mới bộ nhớ đệm.

---

### C5.4 Thực thi bảo mật trong thời gian truy vấn

Triển khai các biện pháp kiểm soát bảo mật cấp cơ sở dữ liệu với bộ lọc bắt buộc và chính sách bảo mật cấp hàng.

 #5.4.1    Level: 1    Role: D/V
 Xác minh rằng tất cả truy vấn cơ sở dữ liệu vector và SQL bao gồm các bộ lọc bảo mật bắt buộc (ID người thuê, nhãn độ nhạy, phạm vi người dùng) được thực thi ở cấp độ động cơ cơ sở dữ liệu, không phải mã ứng dụng.
 #5.4.2    Level: 1    Role: D/V
 Xác minh rằng các chính sách bảo mật cấp hàng (RLS) và che mặt trường dữ liệu được bật với kế thừa chính sách cho tất cả các cơ sở dữ liệu vector, chỉ mục tìm kiếm và bộ dữ liệu đào tạo.
 #5.4.3    Level: 2    Role: D
 Xác minh rằng việc đánh giá ủy quyền không thành công sẽ ngăn chặn "tấn công đại lý nhầm lẫn" bằng cách ngay lập tức hủy bỏ các truy vấn và trả về mã lỗi ủy quyền rõ ràng thay vì trả về các tập kết quả rỗng.
 #5.4.4    Level: 2    Role: V
 Xác minh rằng độ trễ đánh giá chính sách được giám sát liên tục với các cảnh báo tự động cho các điều kiện hết thời gian có thể cho phép vượt qua việc ủy quyền.
 #5.4.5    Level: 3    Role: D/V
 Xác minh rằng cơ chế thử lại truy vấn đánh giá lại các chính sách ủy quyền để tính đến các thay đổi quyền động trong các phiên người dùng đang hoạt động.

---

### Lọc đầu ra C5.5 & Ngăn ngừa mất dữ liệu

Triển khai các kiểm soát hậu xử lý để ngăn chặn việc tiết lộ dữ liệu không được phép trong nội dung do AI tạo ra.

 #5.5.1    Level: 1    Role: D/V
 Xác minh rằng các cơ chế lọc sau suy luận quét và xóa thông tin nhận dạng cá nhân (PII) không được phép, thông tin phân loại và dữ liệu sở hữu trước khi cung cấp nội dung cho người yêu cầu.
 #5.5.2    Level: 1    Role: D/V
 Xác minh rằng các trích dẫn, tham chiếu và ghi nguồn trong kết quả mô hình được xác thực dựa trên quyền hạn của người gọi và loại bỏ nếu phát hiện truy cập trái phép.
 #5.5.3    Level: 2    Role: D
 Xác minh rằng các hạn chế về định dạng đầu ra (PDF đã được làm sạch, hình ảnh đã loại bỏ siêu dữ liệu, các loại tệp được phê duyệt) được thực thi dựa trên cấp độ quyền người dùng và phân loại dữ liệu.
 #5.5.4    Level: 2    Role: V
 Xác minh rằng các thuật toán che khuất dữ liệu là xác định trước, được kiểm soát phiên bản và duy trì nhật ký kiểm toán để hỗ trợ các cuộc điều tra tuân thủ và phân tích pháp y.
 #5.5.5    Level: 3    Role: V
 Xác minh rằng các sự kiện che dấu có rủi ro cao tạo ra các bản ghi thích ứng bao gồm các hàm băm mật mã của nội dung gốc để truy xuất pháp y mà không làm lộ dữ liệu.

---

### C5.6 Cách ly đa người thuê (Multi-Tenant Isolation)

Đảm bảo tách biệt mật mã và tách biệt logic giữa các khách thuê trong hạ tầng AI dùng chung.

 #5.6.1    Level: 1    Role: D/V
 Xác minh rằng các không gian bộ nhớ, kho nhúng, mục trong bộ đệm và các tệp tạm thời được phân tách theo không gian tên cho từng khách thuê với việc xóa bảo mật khi khách thuê bị xóa hoặc phiên làm việc kết thúc.
 #5.6.2    Level: 1    Role: D/V
 Xác minh rằng mọi yêu cầu API đều bao gồm một định danh người thuê đã được xác thực, được xác thực bằng mã hóa đối chiếu với ngữ cảnh phiên và quyền của người dùng.
 #5.6.3    Level: 2    Role: D
 Xác minh rằng các chính sách mạng thực thi các quy tắc mặc định từ chối đối với giao tiếp chéo giữa các khách thuê trong các service mesh và nền tảng điều phối container.
 #5.6.4    Level: 3    Role: D
 Xác minh rằng các khóa mã hóa là duy nhất cho từng khách thuê với hỗ trợ khóa do khách hàng quản lý (CMK) và sự cô lập mật mã giữa các kho dữ liệu của khách thuê.

---

### C5.7 Ủy quyền Đại lý Tự động

Kiểm soát quyền hạn cho các tác nhân AI và hệ thống tự động thông qua token khả năng giới hạn phạm vi và ủy quyền liên tục.

 #5.7.1    Level: 1    Role: D/V
 Xác minh rằng các tác nhân tự trị nhận được token khả năng có phạm vi, trong đó liệt kê rõ các hành động được phép, tài nguyên có thể truy cập, giới hạn thời gian và các ràng buộc vận hành.
 #5.7.2    Level: 1    Role: D/V
 Xác minh rằng các khả năng có rủi ro cao (truy cập hệ thống tệp, thực thi mã, gọi API bên ngoài, giao dịch tài chính) được tắt theo mặc định và yêu cầu các quyền rõ ràng để kích hoạt cùng với lý do kinh doanh.
 #5.7.3    Level: 2    Role: D
 Xác minh rằng các token năng lực được liên kết với phiên người dùng, bao gồm bảo vệ tính toàn vẹn mật mã, và đảm bảo rằng chúng không thể được lưu trữ hoặc tái sử dụng trong các trường hợp ngoại tuyến.
 #5.7.4    Level: 2    Role: V
 Xác minh rằng các hành động do đại lý khởi xướng phải trải qua xác thực thứ cấp thông qua bộ máy chính sách ABAC với đánh giá ngữ cảnh đầy đủ và ghi nhật ký kiểm toán.
 #5.7.5    Level: 3    Role: V
 Xác minh rằng các điều kiện lỗi của đại lý và xử lý ngoại lệ bao gồm thông tin phạm vi khả năng để hỗ trợ phân tích sự cố và điều tra pháp y.

---

### Tài liệu tham khảo

#### Tiêu chuẩn & Khung làm việc

NIST SP 800-63-3: Digital Identity Guidelines
Zero Trust Architecture – NIST SP 800-207
OWASP Application Security Verification Standard (AISVS)
​
#### Hướng dẫn triển khai

Identity and Access Management in the AI Era: 2025 Guide – IDSA
Attribute-Based Access Control with OPA – Permify
How We Designed Cedar to Be Intuitive, Fast, and Safe – AWS
​
#### Bảo mật chuyên biệt cho AI

Row Level Security in Vector DBs for RAG – Bluetuple.ai
Tenant Isolation in Multi-Tenant Systems – WorkOS
Handling AI Agent Permissions – Stytch
OWASP Top 10 for Large Language Model Applications

## C6 Bảo mật chuỗi cung ứng cho Mô hình, Khung và Dữ liệu

### Mục tiêu Kiểm soát

Các cuộc tấn công chuỗi cung ứng AI khai thác các mô hình, khung làm việc hoặc bộ dữ liệu của bên thứ ba để chèn cửa hậu, thiên vị hoặc mã có thể khai thác. Những biện pháp kiểm soát này cung cấp khả năng truy xuất nguồn gốc từ đầu đến cuối, quản lý lỗ hổng và giám sát nhằm bảo vệ toàn bộ vòng đời mô hình.

---

### C6.1 Kiểm tra và Xuất xứ Mô hình Được Huấn luyện Trước

Đánh giá và xác thực nguồn gốc, giấy phép và hành vi ẩn của mô hình bên thứ ba trước khi bất kỳ việc tinh chỉnh hay triển khai nào.

 #6.1.1    Level: 1    Role: D/V
 Xác minh rằng mọi bản sao mô hình bên thứ ba đều bao gồm một hồ sơ nguồn gốc được ký xác nhận, trong đó xác định kho lưu trữ nguồn và mã băm cam kết.
 #6.1.2    Level: 1    Role: D/V
 Xác minh rằng các mô hình được quét để phát hiện các lớp độc hại hoặc kích hoạt Trojan bằng các công cụ tự động trước khi nhập.
 #6.1.3    Level: 2    Role: D
 Xác minh rằng việc tinh chỉnh học chuyển giao vượt qua đánh giá kẻ thù để phát hiện các hành vi ẩn.
 #6.1.4    Level: 2    Role: V
 Xác nhận rằng giấy phép mô hình, thẻ kiểm soát xuất khẩu và tuyên bố nguồn gốc dữ liệu được ghi lại trong mục ML-BOM.
 #6.1.5    Level: 3    Role: D/V
 Xác minh rằng các mô hình rủi ro cao (trọng số được tải lên công khai, người tạo chưa được xác minh) vẫn bị cách ly cho đến khi được kiểm tra và phê duyệt bởi con người.

---

### C6.2 Quét Khung Công Tác & Thư Viện

Liên tục quét các khung và thư viện ML để tìm các CVE và mã độc nhằm giữ cho ngăn xếp runtime được bảo mật.

 #6.2.1    Level: 1    Role: D/V
 Xác minh rằng các pipeline CI chạy các công cụ quét phụ thuộc trên các framework AI và các thư viện quan trọng.
 #6.2.2    Level: 1    Role: D/V
 Xác minh rằng các lỗ hổng nghiêm trọng (CVSS ≥ 7.0) chặn việc thúc đẩy lên các ảnh sản xuất.
 #6.2.3    Level: 2    Role: D
 Xác minh rằng phân tích mã tĩnh được thực hiện trên các thư viện ML được fork hoặc vendor hóa.
 #6.2.4    Level: 2    Role: V
 Xác nhận rằng các đề xuất nâng cấp khung làm việc bao gồm đánh giá tác động bảo mật tham chiếu đến các nguồn thông tin CVE công khai.
 #6.2.5    Level: 3    Role: V
 Xác minh rằng các cảm biến thời gian chạy cảnh báo khi có tải thư viện động không mong đợi mà lệch khỏi SBOM đã được ký.

---

### C6.3 Ghim và Xác minh Phụ thuộc

Ghim mọi phụ thuộc vào các bản tổng hợp không thay đổi và tái tạo các bản xây dựng để đảm bảo các sản phẩm là giống hệt nhau và không bị giả mạo.

 #6.3.1    Level: 1    Role: D/V
 Xác minh rằng tất cả các trình quản lý gói đều thực thi việc cố định phiên bản thông qua các file khóa.
 #6.3.2    Level: 1    Role: D/V
 Xác minh rằng các giá trị băm không thay đổi được sử dụng thay vì các thẻ có thể thay đổi trong các tham chiếu container.
 #6.3.3    Level: 2    Role: D
 Xác minh rằng các kiểm tra xây dựng có thể tái tạo so sánh các giá trị băm qua các lần chạy CI để đảm bảo đầu ra giống hệt nhau.
 #6.3.4    Level: 2    Role: V
 Xác minh rằng chứng thực xây dựng được lưu trữ trong 18 tháng để đảm bảo khả năng truy xuất kiểm toán.
 #6.3.5    Level: 3    Role: D
 Xác minh rằng các phụ thuộc đã hết hạn kích hoạt PR tự động để cập nhật hoặc tách phiên bản được cố định.

---

### C6.4 Thực thi Nguồn Tin cậy

Chỉ cho phép tải xuống tác phẩm từ các nguồn được tổ chức phê duyệt và xác minh bằng mã hóa, đồng thời chặn mọi nguồn khác.

 #6.4.1    Level: 1    Role: D/V
 Xác minh rằng các trọng số mô hình, bộ dữ liệu và container chỉ được tải xuống từ các miền được phê duyệt hoặc các registry nội bộ.
 #6.4.2    Level: 1    Role: D/V
 Xác minh rằng các chữ ký Sigstore/Cosign xác nhận danh tính nhà xuất bản trước khi các tác phẩm được lưu vào bộ nhớ đệm cục bộ.
 #6.4.3    Level: 2    Role: D
 Xác minh rằng các proxy egress chặn việc tải xuống artifact không xác thực để thực thi chính sách nguồn tin cậy.
 #6.4.4    Level: 2    Role: V
 Xác minh rằng danh sách cho phép của kho lưu trữ được xem xét hàng quý với bằng chứng về sự biện minh kinh doanh cho mỗi mục.
 #6.4.5    Level: 3    Role: V
 Xác minh rằng các vi phạm chính sách kích hoạt việc cách ly các hiện vật và hoàn tác các lần chạy đường ống phụ thuộc.

---

### C6.5 Đánh giá Rủi ro Bộ dữ liệu Bên thứ ba

Đánh giá các bộ dữ liệu bên ngoài về khả năng bị đầu độc, thiên vị và tuân thủ pháp lý, đồng thời giám sát chúng trong suốt vòng đời của chúng.

 #6.5.1    Level: 1    Role: D/V
 Xác minh rằng các bộ dữ liệu bên ngoài trải qua đánh giá rủi ro nhiễm độc (ví dụ: tạo dấu vân tay dữ liệu, phát hiện điểm ngoại lai).
 #6.5.2    Level: 1    Role: D
 Xác nhận rằng các chỉ số thiên vị (cân bằng dân số, cơ hội công bằng) được tính toán trước khi phê duyệt bộ dữ liệu.
 #6.5.3    Level: 2    Role: V
 Xác minh rằng nguồn gốc và điều khoản cấp phép cho các tập dữ liệu được ghi lại trong các mục ML-BOM.
 #6.5.4    Level: 2    Role: V
 Xác minh rằng việc giám sát định kỳ phát hiện sự trôi dạt hoặc hỏng hóc trong các bộ dữ liệu được lưu trữ.
 #6.5.5    Level: 3    Role: D
 Xác minh rằng nội dung không được phép (bản quyền, thông tin cá nhân nhạy cảm) đã được loại bỏ thông qua quá trình làm sạch tự động trước khi đào tạo.

---

### C6.6 Giám sát tấn công chuỗi cung ứng

Phát hiện các mối đe dọa chuỗi cung ứng từ sớm thông qua nguồn dữ liệu CVE, phân tích nhật ký kiểm toán và mô phỏng đội tấn công.

 #6.6.1    Level: 1    Role: V
 Xác minh rằng nhật ký kiểm toán CI/CD được truyền đến hệ thống SIEM để phát hiện các hành vi bất thường trong việc kéo gói hoặc các bước xây dựng bị thay đổi.
 #6.6.2    Level: 2    Role: D
 Xác minh rằng các kịch bản ứng phó sự cố bao gồm các thủ tục khôi phục cho các mô hình hoặc thư viện bị xâm phạm.
 #6.6.3    Level: 3    Role: V
 Xác minh rằng việc làm giàu thông tin tình báo về mối đe dọa gắn thẻ các chỉ số cụ thể của ML (ví dụ: các chỉ số IoC về đầu độc mô hình) trong quá trình phân loại cảnh báo.

---

### C6.7 ML‑BOM cho các Tác phẩm Mô hình

Tạo và ký các SBOM chi tiết dành riêng cho ML (ML-BOM) để người tiêu dùng hạ nguồn có thể xác minh tính toàn vẹn của các thành phần khi triển khai.

 #6.7.1    Level: 1    Role: D/V
 Xác minh rằng mọi artefact mô hình đều công bố một ML-BOM liệt kê các bộ dữ liệu, trọng số, siêu tham số và giấy phép.
 #6.7.2    Level: 1    Role: D/V
 Xác minh rằng việc tạo ML-BOM và ký Cosign được tự động hóa trong CI và là yêu cầu bắt buộc để hợp nhất.
 #6.7.3    Level: 2    Role: D
 Xác minh rằng các kiểm tra đầy đủ ML-BOM sẽ làm cho quá trình xây dựng thất bại nếu thiếu bất kỳ siêu dữ liệu thành phần nào (băm, giấy phép).
 #6.7.4    Level: 2    Role: V
 Xác minh rằng người tiêu dùng hạ nguồn có thể truy vấn ML-BOMs qua API để xác thực các mô hình đã nhập khi triển khai.
 #6.7.5    Level: 3    Role: V
 Xác minh rằng ML-BOM được kiểm soát phiên bản và so sánh sự khác biệt để phát hiện các sửa đổi trái phép.

---

### Tài liệu tham khảo

ML Supply Chain Compromise – MITRE ATLAS
Supply‑chain Levels for Software Artifacts (SLSA)
CycloneDX – Machine Learning Bill of Materials
What is Data Poisoning? – SentinelOne
Transfer Learning Attack – OWASP ML Security Top 10
AI Data Security Best Practices – CISA
Secure CI/CD Supply Chain – Sumo Logic
AI & Transparency: Protect ML Models – ReversingLabs
SBOM Overview – CISA
Training Data Poisoning Guide – Lakera.ai
Dependency Pinning for Reproducible Python – Medium

## Hành vi mô hình C7, Kiểm soát đầu ra và Đảm bảo an toàn

### Mục tiêu kiểm soát

Đầu ra của mô hình phải được cấu trúc, đáng tin cậy, an toàn, có thể giải thích và được giám sát liên tục trong môi trường sản xuất. Việc này giúp giảm thiểu các ảo giác, rò rỉ thông tin riêng tư, nội dung gây hại và các hành động ngoài dự kiến, đồng thời tăng cường sự tin tưởng của người dùng và tuân thủ các quy định.

---

### C7.1 Thực thi định dạng đầu ra

Các sơ đồ nghiêm ngặt, giải mã hạn chế và xác thực hạ nguồn ngăn chặn nội dung bị lỗi hoặc độc hại trước khi nó lan truyền.

 #7.1.1    Level: 1    Role: D/V
 Xác minh rằng các sơ đồ phản hồi (ví dụ: JSON Schema) được cung cấp trong lời nhắc hệ thống và mọi đầu ra đều được tự động xác thực; các đầu ra không phù hợp sẽ kích hoạt sửa chữa hoặc từ chối.
 #7.1.2    Level: 1    Role: D/V
 Xác minh rằng giải mã có giới hạn (token dừng, regex, tối đa token) được bật để ngăn ngừa tràn bộ đệm hoặc các kênh bên của việc tiêm lệnh vào prompt.
 #7.1.3    Level: 2    Role: D/V
 Xác minh rằng các thành phần hạ nguồn coi các đầu ra là không được tin cậy và kiểm tra chúng dựa trên các sơ đồ hoặc bộ giải tuần tự hóa an toàn chống chèn mã.
 #7.1.4    Level: 3    Role: V
 Xác minh rằng các sự kiện đầu ra không đúng được ghi lại, giới hạn tần suất và hiển thị lên hệ thống giám sát.

---

### C7.2 Phát hiện và Giảm thiểu Ảo giác

Ước lượng độ không chắc chắn và các chiến lược dự phòng giúp giảm thiểu các câu trả lời bịa đặt.

 #7.2.1    Level: 1    Role: D/V
 Xác minh rằng xác suất log cấp token, độ nhất quán nội bộ của tập hợp mô hình, hoặc các bộ phát hiện ảo tưởng được tinh chỉnh đều gán điểm tin cậy cho từng câu trả lời.
 #7.2.2    Level: 1    Role: D/V
 Xác nhận rằng các phản hồi dưới ngưỡng độ tin cậy có thể cấu hình kích hoạt quy trình làm việc dự phòng (ví dụ: tạo câu trả lời tăng cường truy xuất, mô hình phụ, hoặc đánh giá bởi con người).
 #7.2.3    Level: 2    Role: D/V
 Xác minh rằng các sự cố ảo giác được gắn thẻ với siêu dữ liệu nguyên nhân gốc rễ và được đưa vào các quy trình phân tích sau sự kiện và tinh chỉnh.
 #7.2.4    Level: 3    Role: D/V
 Xác minh rằng các ngưỡng và bộ dò được hiệu chuẩn lại sau các cập nhật lớn về mô hình hoặc cơ sở tri thức.
 #7.2.5    Level: 3    Role: V
 Xác minh rằng các trực quan trên bảng điều khiển theo dõi tỷ lệ ảo giác.

---

### C7.3 Lọc An toàn & Bảo mật Đầu ra

Bộ lọc chính sách và phạm vi kiểm tra đội đỏ bảo vệ người dùng và dữ liệu bí mật.

 #7.3.1    Level: 1    Role: D/V
 Xác minh rằng các bộ phân loại trước và sau khi tạo chặn các nội dung gây thù hận, quấy rối, tự làm hại, cực đoan và nội dung khiêu dâm phù hợp với chính sách.
 #7.3.2    Level: 1    Role: D/V
 Xác minh rằng việc phát hiện PII/PCI và tự động làm mờ được thực hiện trên mọi phản hồi; các vi phạm sẽ kích hoạt một sự cố về quyền riêng tư.
 #7.3.3    Level: 2    Role: D
 Xác minh rằng các thẻ bảo mật (ví dụ: bí mật thương mại) được lan truyền qua các chế độ khác nhau để ngăn ngừa rò rỉ trong văn bản, hình ảnh hoặc mã.
 #7.3.4    Level: 3    Role: D/V
 Xác minh rằng các cố gắng vượt qua bộ lọc hoặc các phân loại rủi ro cao yêu cầu phê duyệt phụ hoặc xác thực người dùng lại.
 #7.3.5    Level: 3    Role: D/V
 Xác minh rằng các ngưỡng lọc phản ánh vùng pháp lý và bối cảnh độ tuổi/vai trò của người dùng.

---

### C7.4 Giới hạn Đầu ra & Hành động

Giới hạn tần suất và cổng phê duyệt ngăn ngừa việc lạm dụng và quyền tự trị quá mức.

 #7.4.1    Level: 1    Role: D
 Xác minh rằng hạn mức cho từng người dùng và từng khóa API giới hạn yêu cầu, token và chi phí với cơ chế tăng thời gian chờ theo cấp số nhân khi gặp lỗi 429.
 #7.4.2    Level: 1    Role: D/V
 Xác minh rằng các hành động đặc quyền (ghi tập tin, thực thi mã, gọi mạng) yêu cầu sự phê duyệt dựa trên chính sách hoặc có sự can thiệp của con người trong quá trình thực hiện.
 #7.4.3    Level: 2    Role: D/V
 Xác minh rằng các kiểm tra nhất quán đa phương thức đảm bảo hình ảnh, mã và văn bản được tạo ra cho cùng một yêu cầu không thể được sử dụng để buôn lậu nội dung độc hại.
 #7.4.4    Level: 2    Role: D
 Xác minh rằng độ sâu ủy quyền đại lý, giới hạn đệ quy và danh sách công cụ được phép được cấu hình rõ ràng.
 #7.4.5    Level: 3    Role: V
 Xác minh rằng việc vi phạm giới hạn phát ra các sự kiện bảo mật có cấu trúc để tiếp nhận vào hệ thống SIEM.

---

### C7.5 Giải thích Đầu ra

Các tín hiệu minh bạch cải thiện sự tin tưởng của người dùng và hỗ trợ gỡ lỗi nội bộ.

 #7.5.1    Level: 2    Role: D/V
 Xác minh rằng các điểm số độ tin cậy đối với người dùng hoặc các bản tóm tắt lý do ngắn gọn được hiển thị khi đánh giá rủi ro cho là phù hợp.
 #7.5.2    Level: 2    Role: D/V
 Xác minh rằng các giải thích được tạo ra không tiết lộ các lời nhắc hệ thống nhạy cảm hoặc dữ liệu sở hữu độc quyền.
 #7.5.3    Level: 3    Role: D
 Xác minh rằng hệ thống ghi lại xác suất log ở cấp độ token hoặc bản đồ chú ý và lưu trữ chúng để kiểm tra có thẩm quyền.
 #7.5.4    Level: 3    Role: V
 Xác minh rằng các tài liệu giải thích được quản lý phiên bản cùng với các bản phát hành mô hình để đảm bảo khả năng kiểm tra.

---

### C7.6 Tích hợp giám sát

Khả năng quan sát thời gian thực kết nối vòng lặp giữa phát triển và sản xuất.

 #7.6.1    Level: 1    Role: D
 Xác minh rằng các chỉ số (vi phạm lược đồ, tỷ lệ ảo giác, độ độc hại, rò rỉ thông tin cá nhân, độ trễ, chi phí) được truyền đến một nền tảng giám sát trung tâm.
 #7.6.2    Level: 1    Role: V
 Xác nhận rằng các ngưỡng cảnh báo được định nghĩa cho từng chỉ số an toàn, kèm theo các con đường leo thang trong ca trực.
 #7.6.3    Level: 2    Role: V
 Xác minh rằng các bảng điều khiển liên kết các điểm bất thường đầu ra với mô hình/phiên bản, cờ tính năng và các thay đổi dữ liệu nguồn cấp.
 #7.6.4    Level: 2    Role: D/V
 Xác minh rằng dữ liệu giám sát được phản hồi vào quá trình tái đào tạo, điều chỉnh tinh chỉnh, hoặc cập nhật quy tắc trong một quy trình MLOps được tài liệu hóa.
 #7.6.5    Level: 3    Role: V
 Xác minh rằng các pipeline giám sát đã được kiểm tra xâm nhập và kiểm soát truy cập để tránh rò rỉ các nhật ký nhạy cảm.

---

### 7.7 Biện pháp bảo vệ truyền thông tạo sinh

Đảm bảo rằng hệ thống AI không tạo ra nội dung phương tiện bất hợp pháp, có hại hoặc không được phép bằng cách thực thi các giới hạn chính sách, xác thực đầu ra và khả năng truy xuất nguồn gốc.

 #7.7.1    Level: 1    Role: D/V
 Xác minh rằng các lời nhắc hệ thống và hướng dẫn người dùng rõ ràng cấm việc tạo ra các phương tiện deepfake bất hợp pháp, có hại hoặc không có sự đồng thuận (ví dụ: hình ảnh, video, âm thanh).
 #7.7.2    Level: 2    Role: D/V
 Xác minh rằng các câu lệnh được lọc để ngăn chặn các cố gắng tạo ra các bản giả mạo, deepfake mang tính khiêu dâm, hoặc các phương tiện truyền thông mô tả cá nhân thật mà không có sự đồng ý.
 #7.7.3    Level: 2    Role: V
 Xác minh rằng hệ thống sử dụng băm nhận thức, phát hiện watermark, hoặc gán dấu vân tay để ngăn chặn việc sao chép trái phép các phương tiện có bản quyền.
 #7.7.4    Level: 3    Role: D/V
 Xác minh rằng tất cả các phương tiện được tạo ra đều được ký số mật mã, đóng dấu bản quyền, hoặc nhúng metadata nguồn gốc chống giả mạo để đảm bảo khả năng truy xuất nguồn gốc trong quá trình xử lý tiếp theo.
 #7.7.5    Level: 3    Role: V
 Xác minh rằng các nỗ lực vượt qua (ví dụ: làm rối câu lệnh đầu vào, sử dụng tiếng lóng, cách diễn đạt đối nghịch) được phát hiện, ghi lại và giới hạn tần suất; lạm dụng lặp đi lặp lại được báo cáo cho các hệ thống giám sát.

### Tài liệu tham khảo

NIST AI Risk Management Framework
ISO/IEC 42001:2023 – AI Management System
OWASP Top-10 for Large Language Model Applications (2025)
Improper Output Handling – OWASP LLM05:2025
Practical Techniques to Constrain LLM Output
Dataiku – Structured Text Generation Guide
VL-Uncertainty: Detecting Hallucinations
HaDeMiF: Hallucination Detection & Mitigation
Building Confidence in LLM Outputs
Explainable AI & LLMs
LLM Red-Teaming Guide
Sensitive Information Disclosure in LLMs
LangChain – Chat Model Rate Limiting
OpenAI Rate-Limit & Exponential Back-off
Arize AI – LLM Observability Platform

## Bảo mật Bộ nhớ C8, Nhúng và Cơ sở dữ liệu Vector

### Mục tiêu Kiểm soát

Lưu trữ vector và embeddings đóng vai trò như "bộ nhớ trực tiếp" của các hệ thống AI hiện đại, liên tục tiếp nhận dữ liệu do người dùng cung cấp và đưa lại dữ liệu đó vào các ngữ cảnh mô hình thông qua Kết hợp Truy xuất và Tạo nội dung (Retrieval-Augmented Generation - RAG). Nếu không được kiểm soát, bộ nhớ này có thể làm rò rỉ thông tin cá nhân nhận dạng được (PII), vi phạm sự đồng ý hoặc bị đảo ngược để tái tạo văn bản gốc. Mục tiêu của nhóm biện pháp kiểm soát này là tăng cường các kênh bộ nhớ và cơ sở dữ liệu vector sao cho việc truy cập tuân theo nguyên tắc ít đặc quyền nhất, embeddings bảo vệ quyền riêng tư, các vector lưu trữ có thời hạn hoặc có thể bị thu hồi khi cần, và bộ nhớ riêng của từng người dùng không bao giờ làm nhiễm bẩn các yêu cầu hay kết quả của người dùng khác.

---

### C8.1 Kiểm soát truy cập trên bộ nhớ và chỉ mục RAG

Thực thi các kiểm soát truy cập chi tiết trên mọi bộ sưu tập vector.

 #8.1.1    Level: 1    Role: D/V
 Xác minh rằng các quy tắc kiểm soát truy cập ở mức dòng/namespace giới hạn các thao tác chèn, xóa và truy vấn theo từng tenant, bộ sưu tập, hoặc nhãn tài liệu.
 #8.1.2    Level: 1    Role: D/V
 Xác minh rằng các khóa API hoặc JWT có chứa các quyền hạn phạm vi (ví dụ: ID bộ sưu tập, động từ hành động) và được thay đổi ít nhất hàng quý.
 #8.1.3    Level: 2    Role: D/V
 Xác minh rằng các nỗ lực leo thang đặc quyền (ví dụ: truy vấn tương đồng chéo không gian tên) được phát hiện và ghi lại vào SIEM trong vòng 5 phút.
 #8.1.4    Level: 2    Role: D/V
 Xác minh rằng cơ sở dữ liệu vector (vector DB) ghi lại nhật ký với các thông tin về định danh chủ thể, thao tác, ID/không gian tên vector, ngưỡng tương tự và số lượng kết quả.
 #8.1.5    Level: 3    Role: V
 Xác minh rằng các quyết định truy cập được kiểm tra lỗi vượt qua mỗi khi bộ máy được nâng cấp hoặc quy tắc phân mảnh chỉ mục thay đổi.

---

### C8.2 Tiêu chuẩn hóa và Xác thực Nhúng

Tiền xử lý văn bản để phát hiện thông tin nhận dạng cá nhân (PII), thực hiện che giấu hoặc ẩn danh trước khi biến đổi thành vector, và tùy chọn xử lý sau các embedding để loại bỏ tín hiệu dư thừa.

 #8.2.1    Level: 1    Role: D/V
 Xác minh rằng dữ liệu nhận dạng cá nhân (PII) và dữ liệu được điều chỉnh được phát hiện thông qua bộ phân loại tự động và được che mờ, mã token hoặc loại bỏ trước khi nhúng.
 #8.2.2    Level: 1    Role: D
 Xác nhận rằng các quy trình nhúng từ chối hoặc cách ly các đầu vào chứa mã thực thi hoặc các ký tự không phải UTF-8 có thể làm độc danh mục.
 #8.2.3    Level: 2    Role: D/V
 Xác minh rằng việc làm sạch dữ liệu theo nguyên tắc riêng tư vi phân cục bộ hoặc chuẩn được áp dụng cho các nhúng câu có khoảng cách đến bất kỳ token Dữ liệu Nhận dạng Cá nhân (PII) nào đã biết nhỏ hơn ngưỡng có thể cấu hình được.
 #8.2.4    Level: 2    Role: V
 Xác nhận rằng hiệu quả làm sạch dữ liệu (ví dụ: độ thu hồi của việc che mờ thông tin nhận dạng cá nhân, sự trôi nghĩa ngữ cảnh) được kiểm tra ít nhất nửa năm một lần dựa trên các bộ dữ liệu chuẩn.
 #8.2.5    Level: 3    Role: D/V
 Xác minh rằng các cấu hình làm sạch được quản lý phiên bản và các thay đổi phải trải qua quá trình kiểm tra của đồng nghiệp.

---

### C8.3 Hết hạn bộ nhớ, Thu hồi & Xóa bỏ

Quyền "được quên" theo GDPR và các luật tương tự yêu cầu việc xóa dữ liệu kịp thời; do đó, các kho vector phải hỗ trợ TTL (thời gian tồn tại), xóa cứng và đánh dấu xóa để các vector bị thu hồi không thể được phục hồi hoặc lập chỉ mục lại.

 #8.3.1    Level: 1    Role: D/V
 Xác minh rằng mỗi vector và bản ghi siêu dữ liệu đều có thời gian sống (TTL) hoặc nhãn lưu giữ rõ ràng được các công việc dọn dẹp tự động tuân thủ.
 #8.3.2    Level: 1    Role: D/V
 Xác nhận rằng các yêu cầu xóa do người dùng khởi tạo sẽ loại bỏ vectơ, siêu dữ liệu, bản sao bộ nhớ đệm và các chỉ mục dẫn xuất trong vòng 30 ngày.
 #8.3.3    Level: 2    Role: D
 Xác minh rằng việc xóa logic được thực hiện sau đó bằng phương pháp xóa dữ liệu mã hóa của các khối lưu trữ nếu phần cứng hỗ trợ, hoặc bằng cách phá hủy khóa trong kho khóa.
 #8.3.4    Level: 3    Role: D/V
 Xác minh rằng các vector hết hạn bị loại trừ khỏi kết quả tìm kiếm gần nhất trong vòng < 500 ms sau khi hết hạn.

---

### C8.4 Ngăn chặn Đảo ngược và Rò rỉ Embedding

Các biện pháp phòng thủ gần đây—ghép chồng nhiễu, mạng chiếu, làm nhiễu neuron bảo mật và mã hóa tầng ứng dụng—có thể giảm tỷ lệ đảo ngược cấp token xuống dưới 5%.

 #8.4.1    Level: 1    Role: V
 Xác minh rằng một mô hình đe dọa chính thức bao gồm các cuộc tấn công đảo ngược, thành viên và suy đoán thuộc tính tồn tại và được xem xét hàng năm.
 #8.4.2    Level: 2    Role: D/V
 Xác minh rằng mã hóa lớp ứng dụng hoặc mã hóa có thể tìm kiếm bảo vệ các vector khỏi việc đọc trực tiếp bởi quản trị viên hạ tầng hoặc nhân viên đám mây.
 #8.4.3    Level: 3    Role: V
 Xác minh các tham số phòng thủ (ε cho DP, độ ồn σ, hạng chiếu k) cân bằng giữa bảo mật ≥ 99% bảo vệ token và tiện ích ≤ 3% mất mát độ chính xác.
 #8.4.4    Level: 3    Role: D/V
 Xác minh rằng các chỉ số độ bền đảo ngược là một phần của các cổng phát hành cho các bản cập nhật mô hình, với ngân sách hồi quy được định nghĩa.

---

### C8.5 Thi hành phạm vi cho bộ nhớ theo người dùng cụ thể

Rò rỉ giữa các tenant vẫn là rủi ro hàng đầu của RAG: các truy vấn tương đồng lọc không đúng có thể hiển thị tài liệu riêng tư của khách hàng khác.

 #8.5.1    Level: 1    Role: D/V
 Xác minh rằng mọi truy vấn truy xuất đều được lọc sau theo ID người thuê/người dùng trước khi được chuyển tới lời nhắc LLM.
 #8.5.2    Level: 1    Role: D
 Xác minh rằng tên bộ sưu tập hoặc ID có không gian tên được thêm muối theo từng người dùng hoặc khách thuê để các vector không bị trùng lặp giữa các phạm vi.
 #8.5.3    Level: 2    Role: D/V
 Xác minh rằng các kết quả tương đồng vượt quá ngưỡng khoảng cách có thể cấu hình nhưng nằm ngoài phạm vi của người gọi sẽ bị loại bỏ và kích hoạt cảnh báo bảo mật.
 #8.5.4    Level: 2    Role: V
 Xác minh rằng các bài kiểm tra tải đa người thuê giả lập các truy vấn đối kháng cố gắng truy xuất tài liệu ngoài phạm vi và chứng minh không rò rỉ dữ liệu.
 #8.5.5    Level: 3    Role: D/V
 Xác minh rằng các khóa mã hóa được phân tách theo từng người thuê, đảm bảo sự cô lập mật mã ngay cả khi lưu trữ vật lý được chia sẻ.

---

### C8.6 An ninh Hệ thống Bộ nhớ Tiên tiến

Các kiểm soát bảo mật cho các kiến trúc bộ nhớ tinh vi bao gồm bộ nhớ theo tập sự kiện (episodic), bộ nhớ ngữ nghĩa (semantic) và bộ nhớ làm việc (working memory) với các yêu cầu cách ly và xác thực cụ thể.

 #8.6.1    Level: 1    Role: D/V
 Xác minh rằng các loại bộ nhớ khác nhau (bộ nhớ theo tập, bộ nhớ ngữ nghĩa, bộ nhớ làm việc) có các ngữ cảnh bảo mật riêng biệt với kiểm soát truy cập dựa trên vai trò, khóa mã hóa riêng biệt và các mô hình truy cập được tài liệu hóa cho từng loại bộ nhớ.
 #8.6.2    Level: 2    Role: D/V
 Xác nhận rằng quy trình củng cố bộ nhớ bao gồm việc kiểm tra bảo mật để ngăn chặn việc chèn các ký ức độc hại thông qua việc làm sạch nội dung, xác minh nguồn và kiểm tra tính toàn vẹn trước khi lưu trữ.
 #8.6.3    Level: 2    Role: D/V
 Xác minh rằng các truy vấn truy xuất bộ nhớ được kiểm tra và làm sạch để ngăn chặn việc khai thác thông tin không được phép thông qua phân tích mẫu truy vấn, thực thi kiểm soát truy cập và lọc kết quả.
 #8.6.4    Level: 3    Role: D/V
 Xác minh rằng các cơ chế quên bộ nhớ xóa dữ liệu nhạy cảm một cách an toàn với các đảm bảo xóa mật mã bằng cách xóa khóa, ghi đè nhiều lần hoặc xóa an toàn dựa trên phần cứng kèm theo chứng nhận xác minh.
 #8.6.5    Level: 3    Role: D/V
 Xác minh rằng tính toàn vẹn của hệ thống bộ nhớ được giám sát liên tục để phát hiện các sửa đổi hoặc hư hỏng trái phép thông qua các hàm băm kiểm tra (checksums), nhật ký kiểm toán (audit logs) và cảnh báo tự động khi nội dung bộ nhớ thay đổi ngoài phạm vi hoạt động bình thường.

---

### Tài liệu tham khảo

Vector database security: Pinecone – IronCore Labs
Securing the Backbone of AI: Safeguarding Vector Databases and Embeddings – Privacera
Enhancing Data Security with RBAC of Qdrant Vector Database – AI Advances
Mitigating Privacy Risks in LLM Embeddings from Embedding Inversion – arXiv
DPPN: Detecting and Perturbing Privacy-Sensitive Neurons – OpenReview
Art. 17 GDPR – Right to Erasure
Sensitive Data in Text Embeddings Is Recoverable – Tonic.ai
PII Identification and Removal – NVIDIA NeMo Docs
De-identifying Sensitive Data – Google Cloud DLP
Remove PII from Conversations Using Sensitive Information Filters – AWS Bedrock Guardrails
Think Your RAG Is Secure? Think Again – Medium
Design a Secure Multitenant RAG Inferencing Solution – Microsoft Learn
Best Practices for Multi-Tenancy RAG with Milvus – Milvus Blog

## 9 Tự động điều phối & An ninh hành động tác nhân

### Mục Tiêu Kiểm Soát

Đảm bảo rằng các hệ thống AI tự động hoặc đa tác nhân chỉ có thể thực hiện các hành động được dự định rõ ràng, xác thực, có thể kiểm tra và nằm trong giới hạn chi phí và ngưỡng rủi ro đã định. Điều này giúp bảo vệ chống lại các mối đe dọa như Xâm phạm Hệ thống Tự động, Lạm dụng Công cụ, Phát hiện Vòng lặp Tác nhân, Chiếm đoạt Giao tiếp, Giả mạo Danh tính, Điều khiển Đàn và Thao túng Ý định.

---

### 9.1 Ngân sách Lập kế hoạch Nhiệm vụ Tác nhân & Đệ quy

Giới hạn các kế hoạch đệ quy và buộc các điểm kiểm tra do con người thực hiện đối với các hành động có đặc quyền.

 #9.1.1    Level: 1    Role: D/V
 Xác minh rằng độ sâu đệ quy tối đa, độ rộng, thời gian thực tế, số lượng token và chi phí tiền tệ cho mỗi lần thực thi đại lý đều được cấu hình tập trung và kiểm soát phiên bản.
 #9.1.2    Level: 1    Role: D/V
 Xác minh rằng các hành động đặc quyền hoặc không thể thu hồi (ví dụ: cam kết mã, chuyển tiền tài chính) yêu cầu sự phê duyệt rõ ràng của con người qua một kênh có thể kiểm tra được trước khi thực hiện.
 #9.1.3    Level: 2    Role: D
 Xác minh rằng các bộ giám sát tài nguyên thời gian thực kích hoạt ngắt mạch đảo khi bất kỳ ngưỡng ngân sách nào bị vượt quá, ngăn chặn việc mở rộng tác vụ tiếp theo.
 #9.1.4    Level: 2    Role: D/V
 Xác minh rằng các sự kiện ngắt mạch được ghi lại với ID đại lý, điều kiện kích hoạt, và trạng thái kế hoạch được ghi nhận để xem xét pháp y.
 #9.1.5    Level: 3    Role: V
 Xác minh rằng các bài kiểm tra bảo mật bao phủ các kịch bản cạn kiệt ngân sách và kế hoạch chạy vượt giới hạn, xác nhận việc dừng an toàn mà không mất dữ liệu.
 #9.1.6    Level: 3    Role: D
 Xác minh rằng các chính sách ngân sách được thể hiện dưới dạng chính sách dưới dạng mã (policy-as-code) và được thực thi trong CI/CD để ngăn chặn sự lệch cấu hình.

---

### 9.2 Cách ly Plugin Công cụ

Cô lập các tương tác công cụ để ngăn chặn truy cập hệ thống hoặc thực thi mã trái phép.

 #9.2.1    Level: 1    Role: D/V
 Xác minh rằng mọi công cụ/plugin đều thực thi bên trong hệ điều hành, container hoặc sandbox cấp độ WASM với các chính sách ít đặc quyền nhất về hệ thống tệp, mạng và gọi hệ thống.
 #9.2.2    Level: 1    Role: D/V
 Xác nhận rằng các hạn mức tài nguyên sandbox (CPU, bộ nhớ, đĩa, băng thông mạng ra ngoài) và thời gian chờ thực thi được thực thi và ghi lại.
 #9.2.3    Level: 2    Role: D/V
 Xác minh rằng các nhị phân hoặc mô tả công cụ được ký số; các chữ ký được xác thực trước khi tải.
 #9.2.4    Level: 2    Role: V
 Xác minh rằng dữ liệu telemetry từ sandbox được truyền đến hệ thống SIEM; các bất thường (ví dụ, các kết nối outbound cố gắng thực hiện) sẽ kích hoạt cảnh báo.
 #9.2.5    Level: 3    Role: V
 Xác minh rằng các plugin có nguy cơ cao được kiểm tra bảo mật và thử nghiệm xâm nhập trước khi triển khai vào môi trường sản xuất.
 #9.2.6    Level: 3    Role: D/V
 Xác minh rằng các cố gắng thoát khỏi vùng an toàn (sandbox) được tự động chặn và plugin vi phạm bị cách ly để chờ điều tra.

---

### 9.3 Vòng Lặp Tự Động & Giới Hạn Chi Phí

Phát hiện và ngăn chặn đệ quy không kiểm soát giữa các tác nhân và sự bùng nổ chi phí.

 #9.3.1    Level: 1    Role: D/V
 Xác minh rằng các cuộc gọi giữa các tác nhân bao gồm một giới hạn số bước nhảy hoặc TTL mà môi trường thực thi sẽ giảm giá trị và thực thi.
 #9.3.2    Level: 2    Role: D
 Xác minh rằng các tác nhân duy trì một ID đồ thị gọi duy nhất để phát hiện tự gọi hoặc các mô hình chu kỳ.
 #9.3.3    Level: 2    Role: D/V
 Xác minh rằng bộ đếm tổng hợp đơn vị tính toán và chi tiêu được theo dõi theo chuỗi yêu cầu; việc vượt quá giới hạn sẽ hủy bỏ chuỗi.
 #9.3.4    Level: 3    Role: V
 Xác minh rằng phân tích hình thức hoặc kiểm tra mô hình chứng minh không có sự đệ quy không giới hạn trong các giao thức tác nhân.
 #9.3.5    Level: 3    Role: D
 Xác minh rằng các sự kiện hủy vòng lặp tạo ra cảnh báo và cung cấp các chỉ số cải tiến liên tục.

---

### 9.4 Bảo vệ chống lạm dụng trên cấp độ giao thức

Kênh giao tiếp an toàn giữa các tác nhân và hệ thống bên ngoài để ngăn chặn việc chiếm đoạt hoặc thao túng.

 #9.4.1    Level: 1    Role: D/V
 Xác minh rằng tất cả các tin nhắn giữa tác nhân và công cụ cũng như giữa các tác nhân với nhau đều được xác thực (ví dụ: TLS hai chiều hoặc JWT) và mã hóa đầu cuối.
 #9.4.2    Level: 1    Role: D
 Xác minh rằng các lược đồ được xác thực một cách nghiêm ngặt; các trường không xác định hoặc thông điệp bị sai định dạng sẽ bị từ chối.
 #9.4.3    Level: 2    Role: D/V
 Xác minh rằng các kiểm tra toàn vẹn (MAC hoặc chữ ký số) bao phủ toàn bộ phần trọng tải tin nhắn bao gồm cả các tham số công cụ.
 #9.4.4    Level: 2    Role: D
 Xác minh rằng tính năng chống phát lại (nonces hoặc cửa sổ dấu thời gian) được thực thi ở lớp giao thức.
 #9.4.5    Level: 3    Role: V
 Xác minh rằng các triển khai giao thức được tiến hành fuzzing và phân tích tĩnh để phát hiện lỗi tiêm nhiễm hoặc phân giải.

---

### 9.5 Định danh tác nhân & Bằng chứng chống giả mạo

Đảm bảo các hành động có thể truy nguyên và các sửa đổi có thể phát hiện được.

 #9.5.1    Level: 1    Role: D/V
 Xác minh rằng mỗi thực thể tác nhân sở hữu một định danh mật mã duy nhất (cặp khóa hoặc chứng chỉ gốc phần cứng).
 #9.5.2    Level: 2    Role: D/V
 Xác minh rằng tất cả các hành động của tác nhân đều được ký và đóng dấu thời gian; nhật ký bao gồm chữ ký để đảm bảo không thể chối bỏ.
 #9.5.3    Level: 2    Role: V
 Xác minh rằng các bản ghi chống giả mạo được lưu trữ trong một phương tiện chỉ cho phép ghi thêm hoặc chỉ ghi một lần.
 #9.5.4    Level: 3    Role: D
 Xác minh rằng các khóa định danh được thay đổi theo lịch trình đã định và khi có dấu hiệu bị xâm phạm.
 #9.5.5    Level: 3    Role: D/V
 Xác minh rằng các cố gắng giả mạo hoặc xung đột khóa kích hoạt cách ly ngay lập tức đối với tác nhân bị ảnh hưởng.

---

### 9.6 Giảm Rủi Ro Đàn Đa Tác Nhân

Giảm thiểu các nguy cơ từ hành vi tập thể thông qua cách ly và mô hình hóa an toàn chính thức.

 #9.6.1    Level: 1    Role: D/V
 Xác minh rằng các tác nhân hoạt động trong các miền bảo mật khác nhau được thực thi trong các môi trường chạy biệt lập hoặc các phân đoạn mạng riêng biệt.
 #9.6.2    Level: 3    Role: V
 Xác minh rằng các hành vi bầy đàn được mô hình hóa và kiểm tra chính thức về tính sống động và an toàn trước khi triển khai.
 #9.6.3    Level: 3    Role: D
 Xác minh rằng các bộ giám sát thời gian chạy phát hiện các mẫu nguy hiểm mới xuất hiện (ví dụ, dao động, tình trạng treo) và khởi động các hành động sửa chữa.

---

### 9.7 Xác thực / Ủy quyền Người dùng và Công cụ

Thực hiện kiểm soát truy cập chặt chẽ cho mọi hành động được kích hoạt bởi tác nhân.

 #9.7.1    Level: 1    Role: D/V
 Xác minh rằng các tác nhân xác thực như các chính thể hạng nhất đối với các hệ thống hạ nguồn, không bao giờ tái sử dụng thông tin xác thực của người dùng cuối.
 #9.7.2    Level: 2    Role: D
 Xác minh rằng các chính sách ủy quyền chi tiết hạn chế công cụ mà đại lý có thể gọi và các tham số mà nó có thể cung cấp.
 #9.7.3    Level: 2    Role: V
 Xác minh rằng các kiểm tra đặc quyền được đánh giá lại ở mỗi lần gọi (ủy quyền liên tục), không chỉ khi bắt đầu phiên làm việc.
 #9.7.4    Level: 3    Role: D
 Xác minh rằng các đặc quyền được ủy quyền tự động hết hạn và yêu cầu đồng ý lại sau khi hết thời gian hoặc thay đổi phạm vi.

---

### 9.8 Bảo mật Giao tiếp giữa các Đại lý

Mã hóa và bảo vệ toàn vẹn tất cả các tin nhắn giữa các tác nhân để ngăn chặn việc nghe trộm và giả mạo.

 #9.8.1    Level: 1    Role: D/V
 Xác nhận rằng xác thực lẫn nhau và mã hóa bí mật chuyển tiếp hoàn hảo (ví dụ: TLS 1.3) là bắt buộc đối với các kênh đại lý.
 #9.8.2    Level: 1    Role: D
 Xác minh rằng tính toàn vẹn và nguồn gốc của tin nhắn được xác thực trước khi xử lý; nếu không thành công sẽ phát cảnh báo và loại bỏ tin nhắn.
 #9.8.3    Level: 2    Role: D/V
 Xác minh rằng siêu dữ liệu truyền thông (dấu thời gian, số thứ tự) được ghi lại để hỗ trợ tái tạo pháp y.
 #9.8.4    Level: 3    Role: V
 Xác minh rằng xác minh hình thức hoặc kiểm tra mô hình xác nhận rằng các máy trạng thái giao thức không thể bị đưa vào các trạng thái không an toàn.

---

### 9.9 Xác minh Ý định và Thực thi Ràng buộc

Xác nhận rằng các hành động của đại lý phù hợp với ý định đã nêu của người dùng và các giới hạn của hệ thống.

 #9.9.1    Level: 1    Role: D
 Xác minh rằng bộ giải ràng buộc trước khi thực thi kiểm tra các hành động đề xuất dựa trên các quy tắc an toàn và chính sách được mã hóa cứng.
 #9.9.2    Level: 2    Role: D/V
 Xác minh rằng các hành động có tác động lớn (tài chính, phá hoại, nhạy cảm về quyền riêng tư) yêu cầu xác nhận ý định rõ ràng từ người dùng khởi tạo.
 #9.9.3    Level: 2    Role: V
 Xác minh rằng kiểm tra hậu điều kiện xác nhận các hành động hoàn thành đã đạt được hiệu quả dự kiến mà không có tác dụng phụ; bất kỳ sai lệch nào sẽ kích hoạt việc hoàn tác.
 #9.9.4    Level: 3    Role: V
 Xác minh rằng các phương pháp hình thức (ví dụ: kiểm tra mô hình, chứng minh định lý) hoặc các bài kiểm tra dựa trên thuộc tính chứng minh rằng các kế hoạch của đại lý đáp ứng tất cả các ràng buộc đã khai báo.
 #9.9.5    Level: 3    Role: D
 Xác minh rằng các sự cố không khớp ý định hoặc vi phạm ràng buộc được đưa vào các chu trình cải tiến liên tục và chia sẻ thông tin tình báo về mối đe dọa.

---

### 9.10 Chiến lược Lập luận của Tác nhân về An ninh

Lựa chọn và thực thi an toàn các chiến lược suy luận khác nhau bao gồm các phương pháp ReAct, Chain-of-Thought và Tree-of-Thoughts.

 #9.10.1    Level: 1    Role: D/V
 Xác minh rằng việc lựa chọn chiến lược suy luận sử dụng các tiêu chí xác định (độ phức tạp đầu vào, loại nhiệm vụ, bối cảnh bảo mật) và các đầu vào giống hệt nhau tạo ra các lựa chọn chiến lược giống nhau trong cùng một bối cảnh bảo mật.
 #9.10.2    Level: 1    Role: D/V
 Xác minh rằng mỗi chiến lược luận lý (ReAct, Chain-of-Thought, Tree-of-Thoughts) có xác thực đầu vào riêng biệt, làm sạch đầu ra, và giới hạn thời gian thực thi cụ thể cho phương pháp nhận thức của nó.
 #9.10.3    Level: 2    Role: D/V
 Xác minh rằng các chuyển đổi chiến lược lập luận được ghi lại với bối cảnh đầy đủ bao gồm đặc điểm đầu vào, giá trị tiêu chí lựa chọn và siêu dữ liệu thực thi để tái tạo dấu vết kiểm toán.
 #9.10.4    Level: 2    Role: D/V
 Xác nhận rằng phương pháp suy luận Tree-of-Thoughts bao gồm các cơ chế cắt nhánh nhằm chấm dứt việc khám phá khi phát hiện vi phạm chính sách, giới hạn tài nguyên hoặc ranh giới an toàn.
 #9.10.5    Level: 2    Role: D/V
 Xác nhận rằng các chu kỳ ReAct (Lý luận-Hành động-Quan sát) bao gồm các điểm kiểm tra xác thực tại mỗi giai đoạn: xác minh bước lý luận, ủy quyền hành động và làm sạch quan sát trước khi tiếp tục.
 #9.10.6    Level: 3    Role: D/V
 Xác minh rằng các chỉ số hiệu suất của chiến lược suy luận (thời gian thực thi, sử dụng tài nguyên, chất lượng đầu ra) được giám sát với cảnh báo tự động khi các chỉ số vượt quá ngưỡng đã cấu hình.
 #9.10.7    Level: 3    Role: D/V
 Xác minh rằng các phương pháp suy luận lai kết hợp nhiều chiến lược duy trì việc xác thực đầu vào và các ràng buộc đầu ra của tất cả các chiến lược thành phần mà không bỏ qua bất kỳ biện pháp kiểm soát bảo mật nào.
 #9.10.8    Level: 3    Role: D/V
 Xác minh rằng việc kiểm thử bảo mật chiến lược suy luận bao gồm việc thử nghiệm fuzzing với các đầu vào bị làm sai định dạng, các lời nhắc đối kháng được thiết kế để buộc chuyển đổi chiến lược, và kiểm thử điều kiện giới hạn cho mỗi phương pháp nhận thức.

---

### 9.11 Quản lý trạng thái vòng đời tác nhân & Bảo mật

Khởi tạo đại lý bảo mật, chuyển đổi trạng thái và kết thúc với đường mòn kiểm toán mật mã và các quy trình phục hồi đã được định nghĩa.

 #9.11.1    Level: 1    Role: D/V
 Xác minh rằng việc khởi tạo tác nhân bao gồm thiết lập danh tính mật mã với chứng chỉ được hỗ trợ phần cứng và các nhật ký kiểm toán khởi động không thể thay đổi chứa ID tác nhân, dấu thời gian, băm cấu hình và các tham số khởi tạo.
 #9.11.2    Level: 2    Role: D/V
 Xác minh rằng các chuyển đổi trạng thái của đại lý được ký điện tử bằng mật mã, đóng dấu thời gian và ghi lại với ngữ cảnh đầy đủ bao gồm các sự kiện kích hoạt, băm trạng thái trước đó, băm trạng thái mới và các kiểm tra bảo mật đã thực hiện.
 #9.11.3    Level: 2    Role: D/V
 Xác minh rằng các quy trình tắt agent bao gồm việc xóa bộ nhớ an toàn bằng cách xóa mật mã hoặc ghi đè nhiều lần, thu hồi chứng chỉ cùng thông báo với cơ quan cấp chứng chỉ, và tạo ra các chứng chỉ chấm dứt có khả năng phát hiện việc can thiệp.
 #9.11.4    Level: 3    Role: D/V
 Xác minh rằng các cơ chế phục hồi tác nhân xác thực tính toàn vẹn của trạng thái bằng cách sử dụng các tổng kiểm tra mật mã (tối thiểu SHA-256) và hoàn nguyên về trạng thái đã biết là tốt khi phát hiện sự cố hỏng với các cảnh báo tự động và yêu cầu phê duyệt thủ công.
 #9.11.5    Level: 3    Role: D/V
 Xác minh rằng các cơ chế duy trì trạng thái của tác nhân mã hóa dữ liệu trạng thái nhạy cảm bằng khóa AES-256 riêng cho từng tác nhân và thực hiện xoay khóa an toàn theo lịch cấu hình được (tối đa 90 ngày) với việc triển khai không gián đoạn.

---

### 9.12 Khung Bảo Mật Tích Hợp Công Cụ

Các biện pháp kiểm soát bảo mật cho việc tải công cụ động, thực thi và xác thực kết quả với các quy trình đánh giá rủi ro và phê duyệt đã được định nghĩa.

 #9.12.1    Level: 1    Role: D/V
 Xác minh rằng mô tả công cụ bao gồm siêu dữ liệu bảo mật chỉ định các quyền cần thiết (đọc/ghi/thực thi), mức độ rủi ro (thấp/trung bình/cao), giới hạn tài nguyên (CPU, bộ nhớ, mạng) và các yêu cầu xác thực được ghi trong bản khai công cụ.
 #9.12.2    Level: 1    Role: D/V
 Xác minh rằng kết quả thực thi công cụ được xác thực dựa trên các sơ đồ mong đợi (JSON Schema, XML Schema) và chính sách bảo mật (lọc sạch đầu ra, phân loại dữ liệu) trước khi tích hợp với giới hạn thời gian chờ và các quy trình xử lý lỗi.
 #9.12.3    Level: 2    Role: D/V
 Xác minh rằng các nhật ký tương tác công cụ bao gồm ngữ cảnh bảo mật chi tiết bao gồm việc sử dụng đặc quyền, mẫu truy cập dữ liệu, thời gian thực thi, mức tiêu thụ tài nguyên và mã trả về với việc ghi nhật ký có cấu trúc để tích hợp SIEM.
 #9.12.4    Level: 2    Role: D/V
 Xác minh rằng các cơ chế tải công cụ động kiểm tra chữ ký số sử dụng hạ tầng PKI và thực hiện các giao thức tải an toàn với cách ly sandbox và xác minh quyền trước khi thực thi.
 #9.12.5    Level: 3    Role: D/V
 Xác minh rằng các đánh giá bảo mật công cụ được kích hoạt tự động cho các phiên bản mới với các cổng phê duyệt bắt buộc bao gồm phân tích tĩnh, kiểm tra động và xem xét của nhóm bảo mật với các tiêu chí phê duyệt được tài liệu hóa và các yêu cầu SLA.

---

#### Tài liệu tham khảo

MITRE ATLAS tactics ML09
Circuit-breaker research for AI agents — Zou et al., 2024
Trend Micro analysis of sandbox escapes in AI agents — Park, 2025
Auth0 guidance on human-in-the-loop authorization for agents — Martinez, 2025
Medium deep-dive on MCP & A2A protocol hijacking — ForAISec, 2025
Rapid7 fundamentals on spoofing attack prevention — 2024
Imperial College verification of swarm systems — Lomuscio et al.
NIST AI Risk Management Framework 1.0, 2023
WIRED security briefing on encryption best practices, 2024
OWASP Top 10 for LLM Applications, 2025
Comprehensive Vulnerability Analysis is Necessary for Trustworthy LLM-MAS
[How Is LLM Reasoning Distracted by Irrelevant Context?
An Analysis Using a Controlled Benchmark](https://www.arxiv.org/pdf/2505.18761)
Large Language Model Sentinel: LLM Agent for Adversarial Purification
Securing Agentic AI: A Comprehensive Threat Model and Mitigation Framework for Generative AI Agents

## 10 Độ Bền Chống Đối Kháng & Phòng Thủ Quyền Riêng Tư

### Mục tiêu Kiểm soát

Đảm bảo rằng các mô hình AI vẫn đáng tin cậy, bảo vệ quyền riêng tư và chống lạm dụng khi đối mặt với các cuộc tấn công né tránh, suy luận, trích xuất hoặc đầu độc.

---

### 10.1 Căn chỉnh Mô hình & An toàn

Phòng tránh các đầu ra có hại hoặc vi phạm chính sách.

 #10.1.1    Level: 1    Role: D/V
 Xác minh rằng bộ kiểm tra sự phù hợp (các lời nhắc đội đỏ, các truy vấn vượt rào, nội dung bị cấm) được quản lý phiên bản và chạy trên mỗi lần phát hành mô hình.
 #10.1.2    Level: 1    Role: D
 Xác minh rằng các biện pháp từ chối và bảo vệ hoàn thành an toàn được thực thi.
 #10.1.3    Level: 2    Role: D/V
 Xác minh rằng một bộ đánh giá tự động đo tỷ lệ nội dung gây hại và báo hiệu các sự suy giảm vượt quá ngưỡng đã đặt.
 #10.1.4    Level: 2    Role: D
 Xác minh rằng việc đào tạo chống vượt ngục được ghi chép và có thể tái hiện.
 #10.1.5    Level: 3    Role: V
 Xác minh rằng các bằng chứng tuân thủ chính sách chính thức hoặc giám sát được chứng nhận bao phủ các lĩnh vực quan trọng.

---

### 10.2 Củng cố chống lại ví dụ đối kháng

Tăng cường khả năng chống chịu trước các đầu vào bị thao túng. Huấn luyện đối kháng mạnh mẽ và đánh giá điểm chuẩn hiện là thực tiễn tốt nhất.

 #10.2.1    Level: 1    Role: D
 Xác minh rằng các kho lưu trữ dự án bao gồm các cấu hình huấn luyện đối kháng với các hạt giống có thể tái tạo.
 #10.2.2    Level: 2    Role: D/V
 Xác minh rằng việc phát hiện các ví dụ đối kháng phát ra cảnh báo chặn trong các quy trình sản xuất.
 #10.2.4    Level: 3    Role: V
 Xác minh rằng các bằng chứng chắc chắn về độ bền được chứng nhận hoặc chứng chỉ giới hạn khoảng bao phủ ít nhất các lớp quan trọng hàng đầu.
 #10.2.5    Level: 3    Role: V
 Xác minh rằng các bài kiểm tra hồi quy sử dụng các cuộc tấn công thích ứng để xác nhận không có sự giảm độ bền đo được.

---

### 10.3 Giảm thiểu rò rỉ thông tin thành viên (Membership-Inference)

Giới hạn khả năng quyết định xem một bản ghi có nằm trong dữ liệu đào tạo hay không. Bảo mật vi phân và che dấu điểm tin cậy vẫn là các phương pháp phòng thủ hiệu quả nhất được biết đến.

 #10.3.1    Level: 1    Role: D
 Xác minh rằng việc điều chuẩn entropy theo từng truy vấn hoặc điều chỉnh nhiệt độ giảm các dự đoán quá tự tin.
 #10.3.2    Level: 2    Role: D
 Xác nhận rằng việc đào tạo sử dụng tối ưu hóa bảo mật vi phân giới hạn bởi ε cho các bộ dữ liệu nhạy cảm.
 #10.3.3    Level: 2    Role: V
 Xác minh rằng các mô phỏng tấn công (mô hình bóng hoặc hộp đen) cho thấy AUC tấn công ≤ 0,60 trên dữ liệu giữ lại.

---

### 10.4 Kháng Chống Đảo Ngược Mô Hình

Ngăn chặn việc tái tạo các thuộc tính riêng tư. Các khảo sát gần đây nhấn mạnh việc cắt ngắn đầu ra và đảm bảo DP như các biện pháp phòng thủ thực tiễn.

 #10.4.1    Level: 1    Role: D
 Xác minh rằng các thuộc tính nhạy cảm không bao giờ được xuất trực tiếp; khi cần, hãy sử dụng các nhóm hoặc biến đổi một chiều.
 #10.4.2    Level: 1    Role: D/V
 Xác minh rằng giới hạn tần suất truy vấn kiểm soát các truy vấn thích ứng lặp lại từ cùng một chủ thể.
 #10.4.3    Level: 2    Role: D
 Xác nhận rằng mô hình được huấn luyện với nhiễu bảo vệ quyền riêng tư.

---

### 10.5 Phòng chống trích xuất mô hình

Phát hiện và ngăn chặn việc sao chép trái phép. Nên sử dụng kỹ thuật đóng dấu (watermarking) và phân tích mẫu truy vấn.

 #10.5.1    Level: 1    Role: D
 Xác minh rằng các cổng suy luận thực thi giới hạn tỷ lệ toàn cầu và trên từng khóa API được điều chỉnh phù hợp với ngưỡng ghi nhớ của mô hình.
 #10.5.2    Level: 2    Role: D/V
 Xác minh rằng thống kê entropy-truy vấn và đa dạng đầu vào cung cấp dữ liệu cho bộ phát hiện trích xuất tự động.
 #10.5.3    Level: 2    Role: V
 Xác minh rằng các watermark dễ vỡ hoặc xác suất có thể được chứng minh với p < 0,01 trong ≤ 1.000 truy vấn chống lại một bản sao nghi ngờ.
 #10.5.4    Level: 3    Role: D
 Xác minh rằng các khóa watermark và bộ kích hoạt được lưu trữ trong mô-đun bảo mật phần cứng và được thay đổi mỗi năm.
 #10.5.5    Level: 3    Role: V
 Xác minh rằng các sự kiện cảnh báo trích xuất bao gồm các truy vấn vi phạm và được tích hợp với sách hướng dẫn ứng phó sự cố.

---

### 10.6 Phát hiện dữ liệu đầu vào bị nhiễm độc vào thời điểm suy luận

Xác định và trung hòa các đầu vào có cửa hậu hoặc bị đầu độc.

 #10.6.1    Level: 1    Role: D
 Xác minh rằng các đầu vào được chuyển qua bộ phát hiện bất thường (ví dụ: STRIP, điểm số nhất quán) trước khi suy luận mô hình.
 #10.6.2    Level: 1    Role: V
 Xác minh rằng các ngưỡng bộ phát hiện được điều chỉnh trên các bộ dữ liệu xác thực sạch/đã bị nhiễm độc để đạt được tỷ lệ dương tính giả dưới 5%.
 #10.6.3    Level: 2    Role: D
 Xác minh rằng các đầu vào bị đánh dấu là bị nhiễm độc kích hoạt việc chặn mềm và quy trình xem xét của con người.
 #10.6.4    Level: 2    Role: V
 Xác minh rằng các bộ phát hiện được kiểm tra độ bền với các cuộc tấn công cửa hậu không kích hoạt thích ứng.
 #10.6.5    Level: 3    Role: D
 Xác minh rằng các chỉ số hiệu quả phát hiện được ghi lại và định kỳ đánh giá lại với thông tin tình báo về mối đe dọa mới.

---

### 10.7 Điều chỉnh Chính sách Bảo mật Động

Cập nhật chính sách bảo mật theo thời gian thực dựa trên thông tin tình báo mối đe dọa và phân tích hành vi.

 #10.7.1    Level: 1    Role: D/V
 Xác minh rằng các chính sách bảo mật có thể được cập nhật động mà không cần khởi động lại agent đồng thời duy trì tính toàn vẹn của phiên bản chính sách.
 #10.7.2    Level: 2    Role: D/V
 Xác minh rằng các cập nhật chính sách được ký bằng mật mã bởi nhân viên an ninh có thẩm quyền và được xác thực trước khi áp dụng.
 #10.7.3    Level: 2    Role: D/V
 Xác minh rằng các thay đổi chính sách động được ghi lại với toàn bộ hồ sơ kiểm toán bao gồm lý do, chuỗi phê duyệt và quy trình hoàn tác.
 #10.7.4    Level: 3    Role: D/V
 Xác minh rằng các cơ chế bảo mật thích ứng điều chỉnh độ nhạy phát hiện mối đe dọa dựa trên bối cảnh rủi ro và các mẫu hành vi.
 #10.7.5    Level: 3    Role: D/V
 Xác minh rằng các quyết định điều chỉnh chính sách có thể giải thích được và bao gồm dấu vết bằng chứng để nhóm bảo mật xem xét.

---

### 10.8 Phân tích Bảo mật Dựa trên Phản chiếu

Xác thực bảo mật thông qua phản ánh tự động của tác nhân và phân tích siêu nhận thức.

 #10.8.1    Level: 1    Role: D/V
 Xác minh rằng các cơ chế phản chiếu của đại lý bao gồm việc tự đánh giá các quyết định và hành động với trọng tâm an ninh.
 #10.8.2    Level: 2    Role: D/V
 Xác minh rằng các đầu ra phản chiếu được kiểm tra để ngăn chặn việc thao túng các cơ chế tự đánh giá bởi các đầu vào đối kháng.
 #10.8.3    Level: 2    Role: D/V
 Xác minh rằng phân tích bảo mật siêu nhận thức xác định được sự thiên vị tiềm ẩn, thao túng hoặc sự xâm phạm trong các quá trình lập luận của tác nhân.
 #10.8.4    Level: 3    Role: D/V
 Xác minh rằng các cảnh báo bảo mật dựa trên phản chiếu kích hoạt giám sát nâng cao và các quy trình can thiệp của con người tiềm năng.
 #10.8.5    Level: 3    Role: D/V
 Xác minh rằng việc học liên tục từ các phản ánh về bảo mật cải thiện phát hiện mối đe dọa mà không làm giảm chức năng hợp lệ.

---

### 10.9 An ninh Tiến hóa & Tự Cải thiện

Kiểm soát an ninh cho các hệ thống tác nhân có khả năng tự sửa đổi và tiến hóa.

 #10.9.1    Level: 1    Role: D/V
 Xác minh rằng khả năng tự chỉnh sửa bị giới hạn trong các khu vực an toàn được chỉ định với các ranh giới xác minh chính thức.
 #10.9.2    Level: 2    Role: D/V
 Xác minh rằng các đề xuất phát triển được tiến hành đánh giá tác động bảo mật trước khi triển khai.
 #10.9.3    Level: 2    Role: D/V
 Xác minh rằng các cơ chế tự cải tiến bao gồm khả năng phục hồi với việc kiểm tra tính toàn vẹn.
 #10.9.4    Level: 3    Role: D/V
 Xác minh rằng bảo mật meta-learning ngăn chặn việc thao túng đối nghịch các thuật toán cải tiến.
 #10.9.5    Level: 3    Role: D/V
 Xác minh rằng việc tự cải tiến đệ quy bị giới hạn bởi các ràng buộc an toàn hình thức với các chứng minh toán học về sự hội tụ.

---

#### Tài liệu tham khảo

MITRE ATLAS adversary tactics for ML
NIST AI Risk Management Framework 1.0, 2023
OWASP Top 10 for LLM Applications, 2025
Adversarial Training: A Survey — Zhao et al., 2024
RobustBench adversarial-robustness benchmark
Membership-Inference & Model-Inversion Risk Survey, 2025
PURIFIER: Confidence-Score Defense against MI Attacks — AAAI 2023
Model-Inversion Attacks & Defenses Survey — AI Review, 2025
Comprehensive Defense Framework Against Model Extraction — IEEE TDSC 2024
Fragile Model Watermarking Survey — 2025
Data Poisoning in Deep Learning: A Survey — Zhao et al., 2025
BDetCLIP: Multimodal Prompting Backdoor Detection — Niu et al., 2024

## 11 Bảo vệ quyền riêng tư & Quản lý dữ liệu cá nhân

### Mục tiêu Kiểm soát

Duy trì các cam kết bảo mật nghiêm ngặt suốt toàn bộ vòng đời AI — từ thu thập, đào tạo, suy luận đến phản ứng sự cố — để dữ liệu cá nhân chỉ được xử lý khi có sự đồng ý rõ ràng, phạm vi cần thiết tối thiểu, khả năng chứng minh việc xóa dữ liệu và các đảm bảo bảo mật chính thức.

---

### 11.1 Ẩn danh & Tối thiểu hóa dữ liệu

 #11.1.1    Level: 1    Role: D/V
 Xác minh rằng các nhận dạng trực tiếp và nhận dạng gần đúng đã được loại bỏ hoặc băm.
 #11.1.2    Level: 2    Role: D/V
 Xác minh rằng các cuộc kiểm toán tự động đo lường k-ẩn danh/l-đa dạng và cảnh báo khi các ngưỡng giảm xuống dưới chính sách.
 #11.1.3    Level: 2    Role: V
 Xác minh rằng các báo cáo tầm quan trọng tính năng của mô hình chứng minh không có rò rỉ định danh vượt quá ε = 0,01 thông tin hỗ tương.
 #11.1.4    Level: 3    Role: V
 Xác minh rằng các bằng chứng chính thức hoặc chứng nhận dữ liệu tổng hợp cho thấy rủi ro tái nhận dạng ≤ 0,05 ngay cả dưới các cuộc tấn công liên kết.

---

### 11.2 Quyền được Xóa và Thực thi Xóa dữ liệu

 #11.2.1    Level: 1    Role: D/V
 Xác minh rằng các yêu cầu xóa dữ liệu của đối tượng được truyền đến các bộ dữ liệu thô, điểm kiểm tra, nhúng, nhật ký và các bản sao lưu trong phạm vi thỏa thuận cấp dịch vụ dưới 30 ngày.
 #11.2.2    Level: 2    Role: D
 Xác minh rằng các quy trình "machine-unlearning" thực sự tái đào tạo hoặc xấp xỉ loại bỏ bằng cách sử dụng các thuật toán unlearning đã được chứng nhận.
 #11.2.3    Level: 2    Role: V
 Xác minh rằng đánh giá mô hình bóng chứng minh các bản ghi đã quên ảnh hưởng dưới 1% các kết quả sau khi học lại.
 #11.2.4    Level: 3    Role: V
 Xác minh rằng các sự kiện xóa được ghi lại một cách không thể thay đổi và có thể kiểm tra đối với các nhà quản lý.

---

### 11.3 Các Biện pháp Bảo vệ Quyền Riêng tư Khác biệt

 #11.3.1    Level: 2    Role: D/V
 Xác minh rằng bảng điều khiển theo dõi mất mát quyền riêng tư cảnh báo khi ε tích lũy vượt quá ngưỡng chính sách.
 #11.3.2    Level: 2    Role: V
 Xác minh rằng các cuộc kiểm toán quyền riêng tư hộp đen ước lượng ε̂ trong phạm vi 10% so với giá trị đã công bố.
 #11.3.3    Level: 3    Role: V
 Xác nhận rằng các chứng minh hình thức bao gồm tất cả các việc tinh chỉnh sau khi đào tạo và các biểu diễn nhúng.

---

### 11.4 Hạn chế Mục đích & Bảo vệ khỏi Tràn Phạm vi

 #11.4.1    Level: 1    Role: D
 Xác minh rằng mọi bộ dữ liệu và điểm kiểm tra mô hình đều mang thẻ mục đích có thể đọc được bằng máy, phù hợp với sự đồng thuận ban đầu.
 #11.4.2    Level: 1    Role: D/V
 Xác minh rằng các bộ giám sát thời gian chạy phát hiện các truy vấn không nhất quán với mục đích đã công bố và kích hoạt từ chối mềm.
 #11.4.3    Level: 3    Role: D
 Xác minh rằng các cổng chính sách dưới dạng mã ngăn chặn việc triển khai lại các mô hình sang các miền mới mà không có đánh giá DPIA.
 #11.4.4    Level: 3    Role: V
 Xác minh rằng các bằng chứng truy xuất nguồn gốc chính thức cho thấy mọi vòng đời dữ liệu cá nhân đều nằm trong phạm vi đã được đồng ý.

---

### 11.5 Quản lý sự đồng ý & theo dõi cơ sở hợp pháp

 #11.5.1    Level: 1    Role: D/V
 Xác minh rằng Nền tảng Quản lý Đồng ý (CMP) ghi lại trạng thái đồng ý, mục đích và thời gian lưu trữ của từng cá nhân dữ liệu.
 #11.5.2    Level: 2    Role: D
 Xác minh rằng các API phô bày token đồng thuận; các mô hình phải xác thực phạm vi token trước khi suy diễn.
 #11.5.3    Level: 2    Role: D/V
 Xác minh rằng việc từ chối hoặc rút lại sự đồng ý sẽ dừng các quy trình xử lý trong vòng 24 giờ.

---

### 11.6 Học Liên Liền với Các Kiểm Soát Quyền Riêng Tư

 #11.6.1    Level: 1    Role: D
 Xác minh rằng các cập nhật của khách hàng sử dụng thêm nhiễu bảo mật vi sai cục bộ trước khi tổng hợp.
 #11.6.2    Level: 2    Role: D/V
 Xác minh rằng các chỉ số huấn luyện tuân thủ ưu tiên tuyệt đối về quyền riêng tư và không bao giờ tiết lộ tổn thất của từng khách hàng riêng biệt.
 #11.6.3    Level: 2    Role: V
 Xác nhận rằng phương pháp tổng hợp chống đầu độc (ví dụ, Krum/Trimmed-Mean) đã được kích hoạt.
 #11.6.4    Level: 3    Role: V
 Xác minh rằng các chứng minh hình thức trình bày tổng ngân sách ε với mức mất mát tiện ích dưới 5.

---

#### Tài liệu tham khảo

GDPR & AI Compliance Best Practices
EU Parliament Study on GDPR & AI, 2020
ISO 31700-1:2023 — Privacy by Design for Consumer Products
NIST Privacy Framework 1.1 (2025 Draft)
Machine Unlearning: Right-to-Be-Forgotten Techniques
A Survey of Machine Unlearning, 2024
Auditing DP-SGD — ArXiv 2024
DP-SGD Explained — PyTorch Blog
Purpose-Limitation for AI — IJLIT 2025
Data-Protection Considerations for AI — URM Consulting
Top Consent-Management Platforms, 2025
Secure Aggregation in DP Federated Learning — ArXiv 2024

## C12 Giám sát, Ghi nhật ký & Phát hiện Dị thường

### Mục tiêu kiểm soát

Phần này cung cấp các yêu cầu để cung cấp khả năng quan sát theo thời gian thực và phân tích pháp y về những gì mô hình và các thành phần AI khác nhìn thấy, thực hiện và trả về, nhằm phát hiện, phân loại và rút ra bài học từ các mối đe dọa.

### C12.1 Ghi nhật ký Yêu cầu & Phản hồi

 #12.1.1    Level: 1    Role: D/V
 Xác nhận rằng tất cả các lời nhắc của người dùng và phản hồi của mô hình được ghi lại cùng với siêu dữ liệu thích hợp (ví dụ: dấu thời gian, ID người dùng, ID phiên, phiên bản mô hình).
 #12.1.2    Level: 1    Role: D/V
 Xác minh rằng các bản ghi được lưu trữ trong các kho lưu trữ an toàn, có kiểm soát quyền truy cập với các chính sách lưu giữ phù hợp và quy trình sao lưu đúng đắn.
 #12.1.3    Level: 1    Role: D/V
 Xác minh rằng các hệ thống lưu trữ nhật ký thực hiện mã hóa dữ liệu khi lưu trữ và trong quá trình truyền để bảo vệ thông tin nhạy cảm có trong nhật ký.
 #12.1.4    Level: 1    Role: D/V
 Xác minh rằng dữ liệu nhạy cảm trong các lệnh nhắc và kết quả đầu ra được tự động che mờ hoặc mã hóa trước khi ghi nhật ký, với các quy tắc làm mờ có thể cấu hình cho thông tin nhận dạng cá nhân (PII), thông tin đăng nhập và thông tin độc quyền.
 #12.1.5    Level: 2    Role: D/V
 Xác minh rằng các quyết định chính sách và hành động lọc an toàn được ghi lại với chi tiết đầy đủ nhằm cho phép kiểm tra và gỡ lỗi hệ thống kiểm duyệt nội dung.
 #12.1.6    Level: 2    Role: D/V
 Xác minh rằng tính toàn vẹn của nhật ký được bảo vệ thông qua ví dụ như chữ ký mã hóa hoặc lưu trữ chỉ ghi.

---

### C12.2 Phát hiện và Cảnh báo Lạm dụng

 #12.2.1    Level: 1    Role: D/V
 Xác minh rằng hệ thống phát hiện và cảnh báo các mẫu jailbreak đã biết, các cố gắng tiêm nhiễm prompt và các đầu vào đối kháng bằng cách sử dụng phương pháp phát hiện dựa trên chữ ký.
 #12.2.2    Level: 1    Role: D/V
 Xác minh rằng hệ thống tích hợp với các nền tảng Quản lý Thông tin và Sự kiện Bảo mật (SIEM) hiện có bằng cách sử dụng các định dạng và giao thức nhật ký tiêu chuẩn.
 #12.2.3    Level: 2    Role: D/V
 Xác minh rằng các sự kiện bảo mật được tăng cường bao gồm bối cảnh đặc thù AI như các định danh mô hình, điểm độ tin cậy và quyết định bộ lọc an toàn.
 #12.2.4    Level: 2    Role: D/V
 Xác minh rằng phát hiện bất thường hành vi nhận dạng các mẫu hội thoại bất thường, số lần thử lại quá mức hoặc các hành vi dò xét có hệ thống.
 #12.2.5    Level: 2    Role: D/V
 Xác nhận rằng các cơ chế cảnh báo thời gian thực thông báo cho các nhóm an ninh khi phát hiện các vi phạm chính sách tiềm năng hoặc các nỗ lực tấn công.
 #12.2.6    Level: 2    Role: D/V
 Xác minh rằng các quy tắc tùy chỉnh được bao gồm để phát hiện các mẫu mối đe dọa đặc thù của AI bao gồm các nỗ lực phá rào phối hợp, chiến dịch tiêm nhắc lệnh và các cuộc tấn công trích xuất mô hình.
 #12.2.7    Level: 3    Role: D/V
 Xác minh rằng các quy trình phản ứng sự cố tự động có thể cô lập các mô hình bị xâm phạm, chặn người dùng độc hại và nâng cao các sự kiện bảo mật quan trọng.

---

### C12.3 Phát Hiện Sự Trôi Dạt Mô Hình

 #12.3.1    Level: 1    Role: D/V
 Xác nhận rằng hệ thống theo dõi các chỉ số hiệu suất cơ bản như độ chính xác, điểm tin cậy, độ trễ và tỷ lệ lỗi qua các phiên bản mô hình và khoảng thời gian.
 #12.3.2    Level: 2    Role: D/V
 Xác minh rằng hệ thống cảnh báo tự động được kích hoạt khi các chỉ số hiệu suất vượt quá ngưỡng suy giảm đã định trước hoặc có sự sai lệch đáng kể so với các đường cơ sở.
 #12.3.3    Level: 2    Role: D/V
 Xác minh rằng các công cụ giám sát phát hiện ảo giác nhận diện và đánh dấu các trường hợp khi đầu ra của mô hình chứa thông tin không chính xác về mặt thực tế, không nhất quán hoặc giả mạo.

---

### C12.4 Hiệu suất & Telemetry Hành vi

 #12.4.1    Level: 1    Role: D/V
 Xác minh rằng các chỉ số vận hành bao gồm độ trễ yêu cầu, mức tiêu thụ token, sử dụng bộ nhớ và thông lượng được liên tục thu thập và giám sát.
 #12.4.2    Level: 1    Role: D/V
 Xác minh rằng tỷ lệ thành công và thất bại được theo dõi với việc phân loại các loại lỗi và nguyên nhân gốc rễ của chúng.
 #12.4.3    Level: 2    Role: D/V
 Xác minh rằng việc giám sát sử dụng tài nguyên bao gồm sử dụng GPU/CPU, tiêu thụ bộ nhớ và yêu cầu lưu trữ với cảnh báo khi vượt ngưỡng.

---

### C12.5 Lập kế hoạch và Triển khai Ứng phó Sự cố AI

 #12.5.1    Level: 1    Role: D/V
 Xác minh rằng các kế hoạch ứng phó sự cố đặc biệt đề cập đến các sự kiện bảo mật liên quan đến AI bao gồm việc xâm phạm mô hình, đầu độc dữ liệu và các cuộc tấn công đối kháng.
 #12.5.2    Level: 2    Role: D/V
 Xác minh rằng các nhóm ứng phó sự cố có quyền truy cập vào các công cụ pháp y chuyên biệt cho AI và chuyên môn để điều tra hành vi mô hình và các vectơ tấn công.
 #12.5.3    Level: 3    Role: D/V
 Xác minh rằng phân tích sau sự cố bao gồm các cân nhắc về huấn luyện lại mô hình, cập nhật bộ lọc an toàn, và tích hợp bài học kinh nghiệm vào các biện pháp kiểm soát bảo mật.

---

### C12.5 Phát hiện sự suy giảm hiệu năng AI

Giám sát và phát hiện suy giảm trong hiệu suất và chất lượng của mô hình AI theo thời gian.

 #12.5.1    Level: 1    Role: D/V
 Xác minh rằng độ chính xác, độ chính xác (precision), độ hồi tưởng (recall) và điểm F1 của mô hình được liên tục theo dõi và so sánh với các ngưỡng cơ sở.
 #12.5.2    Level: 1    Role: D/V
 Xác minh rằng việc phát hiện trôi dữ liệu giám sát sự thay đổi trong phân phối đầu vào có thể ảnh hưởng đến hiệu suất mô hình.
 #12.5.3    Level: 2    Role: D/V
 Xác minh rằng phát hiện trôi khái niệm có thể nhận diện các thay đổi trong mối quan hệ giữa đầu vào và đầu ra dự kiến.
 #12.5.4    Level: 2    Role: D/V
 Xác minh rằng sự suy giảm hiệu suất kích hoạt cảnh báo tự động và khởi động các quy trình tái huấn luyện hoặc thay thế mô hình.
 #12.5.5    Level: 3    Role: V
 Xác nhận rằng phân tích nguyên nhân gốc rễ suy giảm liên kết sự sụt giảm hiệu suất với các thay đổi dữ liệu, sự cố hạ tầng hoặc các yếu tố bên ngoài.

---

### C12.6 Hình ảnh DAG & Bảo mật Quy trình làm việc

Bảo vệ hệ thống trực quan hóa quy trình làm việc khỏi rò rỉ thông tin và các tấn công thao túng.

 #12.6.1    Level: 1    Role: D/V
 Xác minh rằng dữ liệu trực quan hóa DAG được làm sạch để loại bỏ thông tin nhạy cảm trước khi lưu trữ hoặc truyền tải.
 #12.6.2    Level: 1    Role: D/V
 Xác minh rằng các kiểm soát truy cập trực quan hóa luồng công việc đảm bảo chỉ những người dùng được ủy quyền mới có thể xem đường đi quyết định của tác nhân và các dấu vết lập luận.
 #12.6.3    Level: 2    Role: D/V
 Xác minh rằng tính toàn vẹn dữ liệu DAG được bảo vệ thông qua chữ ký mật mã và các cơ chế lưu trữ chống giả mạo.
 #12.6.4    Level: 2    Role: D/V
 Xác minh rằng hệ thống trực quan hóa quy trình làm việc thực hiện xác thực đầu vào để ngăn chặn các cuộc tấn công chèn mã thông qua các dữ liệu nút hoặc cạnh được tạo thủ công.
 #12.6.5    Level: 3    Role: D/V
 Xác minh rằng việc cập nhật DAG theo thời gian thực được giới hạn tốc độ và xác thực để ngăn chặn các cuộc tấn công từ chối dịch vụ vào hệ thống trực quan hóa.

---

### C12.7 Giám sát Hành vi An ninh Chủ động

Phát hiện và ngăn chặn các mối đe dọa bảo mật thông qua phân tích hành vi đại lý chủ động.

 #12.7.1    Level: 1    Role: D/V
 Xác minh rằng các hành vi của tác nhân chủ động đã được kiểm chứng về an ninh trước khi thực thi với tích hợp đánh giá rủi ro.
 #12.7.2    Level: 2    Role: D/V
 Xác nhận rằng các tác nhân khởi xướng tự động bao gồm đánh giá bối cảnh bảo mật và đánh giá cảnh quan mối đe dọa.
 #12.7.3    Level: 2    Role: D/V
 Xác minh rằng các mẫu hành vi chủ động được phân tích để đánh giá các tác động bảo mật tiềm năng và các hậu quả không mong muốn.
 #12.7.4    Level: 3    Role: D/V
 Xác minh rằng các hành động chủ động quan trọng về bảo mật yêu cầu chuỗi phê duyệt rõ ràng kèm theo dấu vết kiểm tra.
 #12.7.5    Level: 3    Role: D/V
 Xác minh rằng phát hiện bất thường hành vi xác định những sai lệch trong các mẫu tác nhân chủ động có thể chỉ ra sự xâm phạm.

---

### Tài liệu tham khảo

NIST AI Risk Management Framework 1.0 - Manage 4.1 and 4.3
ISO/IEC 42001:2023 — AI Management Systems Requirements - Annex B 6.2.6
EU AI Act — Article 12, 13, 16 and 19 on Logging and Record-keeping

## C13 Giám sát Con người, Trách nhiệm & Quản trị

### Mục tiêu kiểm soát

Chương này cung cấp các yêu cầu để duy trì sự giám sát của con người và các chuỗi trách nhiệm rõ ràng trong các hệ thống AI, đảm bảo khả năng giải thích, minh bạch và quản lý đạo đức xuyên suốt vòng đời của AI.

---

### C13.1 Cơ chế Ngắt Kết nối và Ghi đè

Cung cấp các phương án tắt hoặc quay lại khi phát hiện hành vi không an toàn của hệ thống AI.

 #13.1.1    Level: 1    Role: D/V
 Xác minh rằng có cơ chế công tắc ngắt thủ công để ngay lập tức dừng việc suy diễn và đầu ra của mô hình AI.
 #13.1.2    Level: 1    Role: D
 Xác minh rằng các kiểm soát ghi đè chỉ có thể truy cập được bởi nhân sự được ủy quyền.
 #13.1.3    Level: 3    Role: D/V
 Xác minh rằng các quy trình hoàn tác có thể khôi phục về các phiên bản mô hình trước đó hoặc các hoạt động chế độ an toàn.
 #13.1.4    Level: 3    Role: V
 Xác minh rằng các cơ chế ghi đè được kiểm tra thường xuyên.

---

### C13.2 Các Điểm Kiểm Tra Quyết Định Có Con Người Tham Gia

Yêu cầu phê duyệt của con người khi mức độ rủi ro vượt qua ngưỡng đã định trước.

 #13.2.1    Level: 1    Role: D/V
 Xác minh rằng các quyết định AI có rủi ro cao cần được sự duyệt xét rõ ràng của con người trước khi thực hiện.
 #13.2.2    Level: 1    Role: D
 Xác minh rằng ngưỡng rủi ro được định nghĩa rõ ràng và tự động kích hoạt các quy trình xem xét của con người.
 #13.2.3    Level: 2    Role: D
 Xác minh rằng các quyết định nhạy cảm về thời gian có quy trình dự phòng khi không thể nhận được sự phê duyệt của con người trong khoảng thời gian yêu cầu.
 #13.2.4    Level: 3    Role: D/V
 Xác minh rằng các quy trình leo thang đã định nghĩa rõ ràng các cấp độ thẩm quyền cho các loại quyết định khác nhau hoặc các danh mục rủi ro, nếu có thể áp dụng.

---

### C13.3 Chuỗi Trách Nhiệm & Khả Năng Kiểm Toán

Ghi lại các hành động của người vận hành và các quyết định của mô hình.

 #13.3.1    Level: 1    Role: D/V
 Xác minh rằng tất cả các quyết định của hệ thống AI và các can thiệp của con người đều được ghi lại với dấu thời gian, danh tính người dùng và lý do quyết định.
 #13.3.2    Level: 2    Role: D
 Xác minh rằng các nhật ký kiểm toán không thể bị làm giả và bao gồm các cơ chế xác minh tính toàn vẹn.

---

### C13.4 Kỹ thuật AI Có thể Giải thích được

Tầm quan trọng của đặc trưng bề mặt, các phản thực, và giải thích cục bộ.

 #13.4.1    Level: 1    Role: D/V
 Xác minh rằng các hệ thống AI cung cấp các giải thích cơ bản cho quyết định của chúng dưới định dạng dễ đọc đối với con người.
 #13.4.2    Level: 2    Role: V
 Xác minh rằng chất lượng giải thích được xác nhận thông qua các nghiên cứu đánh giá của con người và các chỉ số.
 #13.4.3    Level: 3    Role: D/V
 Xác minh rằng các điểm quan trọng của đặc trưng hoặc các phương pháp gán thuộc tính (SHAP, LIME, v.v.) có sẵn cho các quyết định quan trọng.
 #13.4.4    Level: 3    Role: V
 Xác minh rằng các giải thích phản thực (counterfactual explanations) cho thấy cách các đầu vào có thể được điều chỉnh để thay đổi kết quả, nếu áp dụng được cho trường hợp sử dụng và lĩnh vực tương ứng.

---

### C13.5 Thẻ Mô Hình & Công Bố Sử Dụng

Duy trì thẻ mô hình cho mục đích sử dụng, các chỉ số hiệu suất và các cân nhắc đạo đức.

 #13.5.1    Level: 1    Role: D
 Xác minh rằng các thẻ mô hình ghi lại các trường hợp sử dụng dự kiến, giới hạn và các chế độ lỗi đã biết.
 #13.5.2    Level: 1    Role: D/V
 Xác minh rằng các chỉ số hiệu suất trong các trường hợp sử dụng áp dụng khác nhau đã được công bố.
 #13.5.3    Level: 2    Role: D
 Xác minh rằng các cân nhắc đạo đức, đánh giá thiên vị, đánh giá công bằng, đặc điểm dữ liệu tập huấn, và các hạn chế dữ liệu tập huấn đã biết được ghi chép và cập nhật thường xuyên.
 #13.5.4    Level: 2    Role: D/V
 Xác minh rằng thẻ mô hình được kiểm soát phiên bản và duy trì trong suốt vòng đời của mô hình với việc theo dõi thay đổi.

---

### C13.6 Định lượng bất định

Truyền đạt điểm tin cậy hoặc các đo lường entropy trong các phản hồi.

 #13.6.1    Level: 1    Role: D
 Xác minh rằng các hệ thống AI cung cấp điểm tin cậy hoặc các thước đo độ không chắc chắn cùng với kết quả đầu ra của chúng.
 #13.6.2    Level: 2    Role: D/V
 Xác minh rằng các ngưỡng không chắc chắn kích hoạt việc đánh giá thêm bởi con người hoặc các con đường quyết định thay thế.
 #13.6.3    Level: 2    Role: V
 Xác minh rằng các phương pháp lượng hóa không chắc chắn đã được hiệu chuẩn và xác thực dựa trên dữ liệu thực tế.
 #13.6.4    Level: 3    Role: D/V
 Xác minh rằng sự lan truyền bất định được duy trì qua các quy trình làm việc AI đa bước.

---

### C13.7 Báo Cáo Minh Bạch Hướng Đến Người Dùng

Cung cấp các báo cáo định kỳ về các sự cố, sự thay đổi (drift), và việc sử dụng dữ liệu.

 #13.7.1    Level: 1    Role: D/V
 Xác minh rằng các chính sách sử dụng dữ liệu và thực hành quản lý sự đồng ý của người dùng được truyền đạt rõ ràng đến các bên liên quan.
 #13.7.2    Level: 2    Role: D/V
 Xác minh rằng các đánh giá tác động AI được tiến hành và kết quả được bao gồm trong báo cáo.
 #13.7.3    Level: 2    Role: D/V
 Xác minh rằng các báo cáo minh bạch được công bố định kỳ tiết lộ các sự cố AI và các chỉ số hoạt động một cách chi tiết hợp lý.

#### Tài liệu tham khảo

EU Artificial Intelligence Act — Regulation (EU) 2024/1689 (Official Journal, 12 July 2024)
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
ISO/IEC 42001:2023 — AI Management Systems Requirements
NIST AI Risk Management Framework 1.0
NIST SP 800-53 Revision 5 — Security and Privacy Controls
A Unified Approach to Interpreting Model Predictions (SHAP, ICML 2017)
Model Cards for Model Reporting (Mitchell et al., 2018)
Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning (Gal & Ghahramani, 2016)
ISO/IEC 24029-2:2023 — Robustness of Neural Networks — Methodology for Formal Methods
IEEE 7001-2021 — Transparency of Autonomous Systems
GDPR — Article 5 "Transparency Principle" (Regulation (EU) 2016/679)
Human Oversight under Article 14 of the EU AI Act (Fink, 2025)

## Phụ lục A: Bảng chú giải thuật ngữ

Bảng thuật ngữ toàn diện này cung cấp định nghĩa các thuật ngữ chính về trí tuệ nhân tạo (AI), học máy (ML) và bảo mật được sử dụng trong toàn bộ AISVS nhằm đảm bảo sự rõ ràng và hiểu biết chung.
​
Ví dụ đối kháng: Một đầu vào được tạo ra có chủ ý nhằm khiến mô hình AI mắc lỗi, thường bằng cách thêm các biến đổi tinh vi mà con người không thể nhận thấy.
​
Độ bền chống lại tấn công đối kháng – Độ bền chống lại tấn công đối kháng trong AI đề cập đến khả năng của một mô hình duy trì hiệu suất và chống lại việc bị đánh lừa hoặc thao túng bởi các đầu vào độc hại được tạo ra có chủ ý nhằm gây ra lỗi.
​
Tác nhân – Tác nhân AI là các hệ thống phần mềm sử dụng trí tuệ nhân tạo để theo đuổi các mục tiêu và hoàn thành các nhiệm vụ thay mặt người dùng. Chúng thể hiện khả năng lý luận, lập kế hoạch và ghi nhớ, đồng thời có mức độ tự chủ để đưa ra quyết định, học hỏi và thích nghi.
​
AI có tính tác nhân: Các hệ thống AI có thể hoạt động với một mức độ tự chủ nhất định để đạt được mục tiêu, thường đưa ra quyết định và thực hiện hành động mà không cần sự can thiệp trực tiếp của con người.
​
Kiểm soát Truy cập Dựa trên Thuộc tính (ABAC): Một mô hình kiểm soát truy cập trong đó các quyết định ủy quyền dựa trên các thuộc tính của người dùng, tài nguyên, hành động và môi trường, được đánh giá tại thời điểm truy vấn.
​
Tấn công Cửa hậu: Một loại tấn công đầu độc dữ liệu trong đó mô hình được huấn luyện để phản ứng theo một cách cụ thể với các kích hoạt nhất định trong khi vẫn hoạt động bình thường ở các trường hợp khác.
​
Định kiến: Các lỗi hệ thống trong đầu ra của mô hình AI có thể dẫn đến kết quả không công bằng hoặc phân biệt đối xử đối với một số nhóm hoặc trong các bối cảnh cụ thể.
​
Khai thác định kiến: Một kỹ thuật tấn công lợi dụng các định kiến đã biết trong các mô hình AI để điều khiển kết quả đầu ra hoặc kết quả tổng thể.
​
Cedar: Ngôn ngữ và công cụ chính sách của Amazon cho các quyền truy cập chi tiết được sử dụng trong việc triển khai ABAC cho các hệ thống AI.
​
Chuỗi suy nghĩ: Một kỹ thuật để cải thiện khả năng lý luận trong các mô hình ngôn ngữ bằng cách tạo ra các bước suy luận trung gian trước khi đưa ra câu trả lời cuối cùng.
​
Rơle ngắt mạch: Cơ chế tự động dừng hoạt động của hệ thống AI khi vượt quá ngưỡng rủi ro cụ thể.
​
Rò rỉ dữ liệu: Tiếp xúc không mong muốn với thông tin nhạy cảm thông qua kết quả hoặc hành vi của mô hình AI.
​
Độc hại dữ liệu: Việc cố ý làm hỏng dữ liệu huấn luyện để làm suy giảm tính toàn vẹn của mô hình, thường nhằm cài đặt cửa hậu hoặc làm giảm hiệu suất.
​
Bảo mật vi sai – Bảo mật vi sai là một khuôn khổ toán học nghiêm ngặt để công bố thông tin thống kê về các bộ dữ liệu trong khi bảo vệ quyền riêng tư của các cá nhân trong dữ liệu. Nó cho phép người giữ dữ liệu chia sẻ các mẫu tổng hợp của nhóm trong khi giới hạn thông tin bị rò rỉ về các cá nhân cụ thể.
​
Embedding: Biểu diễn vector dày đặc của dữ liệu (văn bản, hình ảnh, v.v.) để nắm bắt ý nghĩa ngữ nghĩa trong không gian chiều cao.
​
Giải thích được – Giải thích được trong AI là khả năng của hệ thống AI cung cấp các lý do dễ hiểu đối với con người cho các quyết định và dự đoán của nó, đồng thời cung cấp cái nhìn sâu sắc về cách hoạt động bên trong của hệ thống.
​
Trí tuệ nhân tạo có thể giải thích được (XAI): Hệ thống AI được thiết kế để cung cấp các giải thích mà con người có thể hiểu được về các quyết định và hành vi của chúng thông qua các kỹ thuật và khung làm việc khác nhau.
​
Học Liên Liên Đới: Một phương pháp học máy trong đó các mô hình được huấn luyện trên nhiều thiết bị phân tán giữ các mẫu dữ liệu cục bộ, mà không trao đổi dữ liệu gốc.
​
Hàng rào bảo vệ: Các giới hạn được áp dụng để ngăn hệ thống AI tạo ra các kết quả gây hại, thiên vị hoặc không mong muốn khác.
​
Ảo giác – Ảo giác AI đề cập đến hiện tượng một mô hình AI tạo ra thông tin không chính xác hoặc gây hiểu lầm, không dựa trên dữ liệu đào tạo của nó hoặc thực tế khách quan.
​
Con người tham gia trực tiếp (HITL): Hệ thống được thiết kế đòi hỏi sự giám sát, xác minh hoặc can thiệp của con người tại các điểm quyết định quan trọng.
​
Hạ tầng dưới dạng mã (IaC): Quản lý và cung cấp hạ tầng thông qua mã thay vì quy trình thủ công, cho phép quét bảo mật và triển khai nhất quán.
​
Jailbreak: Các kỹ thuật được sử dụng để vượt qua các hàng rào an toàn trong hệ thống AI, đặc biệt là trong các mô hình ngôn ngữ lớn, nhằm tạo ra nội dung bị cấm.
​
Nguyên tắc Ít Quyền: Nguyên tắc bảo mật chỉ cấp quyền truy cập tối thiểu cần thiết cho người dùng và các tiến trình.
​
LIME (Giải thích Mô hình Độc lập tại cục bộ): Một kỹ thuật để giải thích các dự đoán của bất kỳ bộ phân loại học máy nào bằng cách xấp xỉ nó tại khu vực cục bộ với một mô hình có thể giải thích được.
​
Cuộc tấn công suy luận thành viên: Một cuộc tấn công nhằm xác định xem một điểm dữ liệu cụ thể có được sử dụng để đào tạo mô hình học máy hay không.
​
MITRE ATLAS: Cảnh quan mối đe dọa đối kháng cho hệ thống Trí tuệ Nhân tạo; một cơ sở tri thức về các chiến thuật và kỹ thuật đối kháng chống lại hệ thống AI.
​
Thẻ Mô Hình – Thẻ mô hình là một tài liệu cung cấp thông tin chuẩn hóa về hiệu suất của mô hình AI, các hạn chế, các mục đích sử dụng dự kiến và các cân nhắc đạo đức nhằm thúc đẩy sự minh bạch và phát triển AI có trách nhiệm.
​
Chiết xuất mô hình: Một cuộc tấn công mà kẻ thù liên tục truy vấn một mô hình mục tiêu để tạo ra một bản sao có chức năng tương tự mà không được phép.
​
Đảo ngược mô hình: Một cuộc tấn công cố gắng tái tạo dữ liệu huấn luyện bằng cách phân tích đầu ra của mô hình.
​
Quản lý Vòng đời Mô hình – Quản lý vòng đời mô hình AI là quá trình giám sát tất cả các giai đoạn tồn tại của một mô hình AI, bao gồm thiết kế, phát triển, triển khai, giám sát, bảo trì và cuối cùng là loại bỏ, nhằm đảm bảo mô hình luôn hiệu quả và phù hợp với các mục tiêu.
​
Đầu độc mô hình: Giới thiệu các lỗ hổng hoặc cửa hậu trực tiếp vào mô hình trong quá trình huấn luyện.
​
Trộm/Cắp Mô Hình: Trích xuất bản sao hoặc xấp xỉ của một mô hình độc quyền thông qua các truy vấn lặp lại.
​
Hệ thống đa tác nhân: Một hệ thống bao gồm nhiều tác nhân AI tương tác với nhau, mỗi tác nhân có thể có các khả năng và mục tiêu khác nhau.
​
OPA (Open Policy Agent): Một công cụ chính sách mã nguồn mở cho phép thi hành chính sách thống nhất trên toàn bộ hệ thống.
​
Học Máy Bảo Vệ Quyền Riêng Tư (PPML): Các kỹ thuật và phương pháp để huấn luyện và triển khai các mô hình học máy trong khi bảo vệ quyền riêng tư của dữ liệu huấn luyện.
​
Chèn Lệnh Gợi Ý: Một cuộc tấn công trong đó các chỉ dẫn độc hại được nhúng trong đầu vào nhằm ghi đè hành vi dự định của mô hình.
​
RAG (Sinh Tạo Bổ Sung Tìm Kiếm): Một kỹ thuật nâng cao các mô hình ngôn ngữ lớn bằng cách truy xuất thông tin liên quan từ các nguồn kiến thức bên ngoài trước khi tạo ra phản hồi.
​
Red-Teaming: Thực hành kiểm tra chủ động các hệ thống AI bằng cách mô phỏng các cuộc tấn công đối kháng nhằm xác định các điểm yếu.
​
SBOM (Bảng kê nguyên vật liệu phần mềm): Một bản ghi chính thức chứa chi tiết và các mối quan hệ trong chuỗi cung ứng của các thành phần khác nhau được sử dụng trong việc xây dựng phần mềm hoặc mô hình AI.
​
SHAP (Giải thích cộng thêm Shapley): Một phương pháp lý thuyết trò chơi để giải thích kết quả của bất kỳ mô hình học máy nào bằng cách tính đóng góp của từng đặc trưng vào dự đoán.
​
Tấn công Chuỗi Cung Ứng: Xâm nhập hệ thống bằng cách nhắm vào các thành phần có bảo mật thấp hơn trong chuỗi cung ứng của nó, chẳng hạn như thư viện bên thứ ba, bộ dữ liệu hoặc mô hình được huấn luyện trước.
​
Học chuyển tiếp: Một kỹ thuật trong đó một mô hình được phát triển cho một nhiệm vụ được tái sử dụng làm điểm khởi đầu cho một mô hình cho nhiệm vụ thứ hai.
​
Cơ sở dữ liệu Vector: Một cơ sở dữ liệu chuyên dụng được thiết kế để lưu trữ các vector có chiều cao (embedding) và thực hiện các tìm kiếm tương đồng hiệu quả.
​
Quét lỗ hổng bảo mật: Công cụ tự động xác định các lỗ hổng bảo mật đã biết trong các thành phần phần mềm, bao gồm các khung AI và các phụ thuộc.
​
Đóng dấu bản quyền: Các kỹ thuật nhúng các dấu hiệu không thể nhận thấy vào nội dung do AI tạo ra để theo dõi nguồn gốc hoặc phát hiện sự tạo ra bởi AI.
​
Lỗ hổng Zero-Day: Một lỗ hổng chưa được biết đến trước đây mà kẻ tấn công có thể khai thác trước khi các nhà phát triển tạo và triển khai bản vá.

## Phụ lục B: Tài liệu Tham khảo

### TODO

## Phụ lục C: Quản trị An ninh AI & Tài liệu

### Mục tiêu

Phụ lục này cung cấp các yêu cầu cơ bản để thiết lập cấu trúc tổ chức, chính sách và quy trình nhằm quản lý an ninh AI trong suốt vòng đời hệ thống.

---

### AC.1 Áp dụng Khung Quản lý Rủi ro AI

Cung cấp một khuôn khổ chính thức để xác định, đánh giá và giảm thiểu các rủi ro riêng biệt của AI trong suốt vòng đời hệ thống.

 #AC.1.1    Level: 1    Role: D/V
 Xác minh rằng phương pháp đánh giá rủi ro dành riêng cho AI đã được tài liệu hóa và triển khai.
 #AC.1.2    Level: 2    Role: D
 Xác minh rằng các đánh giá rủi ro được thực hiện tại các điểm quan trọng trong vòng đời AI và trước các thay đổi đáng kể.
 #AC.1.3    Level: 3    Role: D/V
 Xác minh rằng khung quản lý rủi ro phù hợp với các tiêu chuẩn đã được thiết lập (ví dụ: NIST AI RMF).

---

### AC.2 Chính sách & Quy trình An ninh AI

Định nghĩa và thực thi các tiêu chuẩn tổ chức cho phát triển, triển khai và vận hành AI an toàn.

 #AC.2.1    Level: 1    Role: D/V
 Xác minh rằng các chính sách bảo mật AI được tài liệu hóa đã tồn tại.
 #AC.2.2    Level: 2    Role: D
 Xác minh rằng các chính sách được xem xét và cập nhật ít nhất hàng năm và sau khi có những thay đổi đáng kể trong cảnh quan mối đe dọa.
 #AC.2.3    Level: 3    Role: D/V
 Xác minh rằng các chính sách bao phủ tất cả các loại AISVS và các yêu cầu quy định áp dụng.

---

### AC.3 Vai trò & Trách nhiệm cho An ninh AI

Thiết lập trách nhiệm rõ ràng về an ninh AI trên toàn tổ chức.

 #AC.3.1    Level: 1    Role: D/V
 Xác minh rằng các vai trò và trách nhiệm bảo mật AI đã được ghi chép.
 #AC.3.2    Level: 2    Role: D
 Xác minh rằng các cá nhân chịu trách nhiệm có chuyên môn bảo mật phù hợp.
 #AC.3.3    Level: 3    Role: D/V
 Xác nhận rằng một ủy ban đạo đức AI hoặc ban quản trị đã được thành lập cho các hệ thống AI có rủi ro cao.

---

### AC.4 Thực thi Hướng dẫn AI Đạo đức

Đảm bảo các hệ thống AI hoạt động theo các nguyên tắc đạo đức đã được thiết lập.

 #AC.4.1    Level: 1    Role: D/V
 Xác minh rằng các hướng dẫn đạo đức cho việc phát triển và triển khai AI đã tồn tại.
 #AC.4.2    Level: 2    Role: D
 Xác minh rằng các cơ chế đã được thiết lập để phát hiện và báo cáo các vi phạm đạo đức.
 #AC.4.3    Level: 3    Role: D/V
 Xác minh rằng các đợt đánh giá đạo đức định kỳ đối với các hệ thống AI đã triển khai được thực hiện.

---

### AC.5 Giám sát Tuân thủ Quy định AI

Duy trì nhận thức và tuân thủ các quy định AI đang phát triển.

 #AC.5.1    Level: 1    Role: D/V
 Xác minh rằng có các quy trình để xác định các quy định AI áp dụng.
 #AC.5.2    Level: 2    Role: D
 Xác minh rằng việc tuân thủ tất cả các yêu cầu quy định được đánh giá.
 #AC.5.3    Level: 3    Role: D/V
 Xác minh rằng các thay đổi quy định kích hoạt việc xem xét và cập nhật kịp thời các hệ thống AI.

#### Tài liệu tham khảo

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
ISO/IEC 23894:2023 — Artificial Intelligence — Guidance on Risk Management
EU Artificial Intelligence Act — Regulation (EU) 2024/1689
ISO/IEC 24029‑2:2023 — Robustness of Neural Networks — Methodology for Formal Methods

## Phụ lục D: Quản trị và Xác minh Mã hóa An toàn Hỗ trợ bởi AI

### Mục tiêu

Chương này xác định các kiểm soát tổ chức cơ bản để sử dụng an toàn và hiệu quả các công cụ mã hóa hỗ trợ AI trong quá trình phát triển phần mềm, đảm bảo an ninh và khả năng truy xuất trong suốt vòng đời phát triển phần mềm (SDLC).

---

### AD.1 Quy trình lập trình bảo mật được hỗ trợ bởi AI

Tích hợp công cụ AI vào vòng đời phát triển phần mềm an toàn (SSDLC) của tổ chức mà không làm suy yếu các cổng bảo mật hiện có.

 #AD.1.1    Level: 1    Role: D/V
 Xác minh rằng quy trình làm việc đã được ghi chép mô tả khi nào và cách thức các công cụ AI có thể tạo ra, tái cấu trúc hoặc xem xét mã nguồn.
 #AD.1.2    Level: 2    Role: D
 Xác minh rằng quy trình làm việc tương ứng với từng giai đoạn của SSDLC (thiết kế, triển khai, rà soát mã, kiểm thử, triển khai).
 #AD.1.3    Level: 3    Role: D/V
 Xác minh rằng các chỉ số (ví dụ, mật độ lỗ hổng, thời gian trung bình để phát hiện) được thu thập trên mã do AI tạo ra và được so sánh với các nền tảng chỉ do con người tạo ra.

---

### AD.2 Đánh giá Công cụ AI & Mô hình hóa Mối đe dọa

Đảm bảo các công cụ mã hóa AI được đánh giá về khả năng bảo mật, rủi ro và tác động chuỗi cung ứng trước khi áp dụng.

 #AD.2.1    Level: 1    Role: D/V
 Xác minh rằng mô hình mối đe dọa cho mỗi công cụ AI xác định được các rủi ro về sử dụng sai mục đích, đảo ngược mô hình, rò rỉ dữ liệu và chuỗi phụ thuộc.
 #AD.2.2    Level: 2    Role: D
 Xác minh rằng các đánh giá công cụ bao gồm phân tích tĩnh/động của bất kỳ thành phần cục bộ nào và đánh giá các điểm cuối SaaS (TLS, xác thực/ủy quyền, ghi nhật ký).
 #AD.2.3    Level: 3    Role: D/V
 Xác minh rằng các đánh giá tuân theo một khung công tác được công nhận và được thực hiện lại sau các thay đổi phiên bản lớn.

---

### AD.3 Quản lý Bảo mật Lời nhắc và Ngữ cảnh

Ngăn ngừa rò rỉ bí mật, mã nguồn độc quyền và dữ liệu cá nhân khi xây dựng các lời nhắc hoặc ngữ cảnh cho mô hình AI.

 #AD.3.1    Level: 1    Role: D/V
 Xác nhận rằng hướng dẫn bằng văn bản nghiêm cấm việc gửi thông tin bí mật, thông tin đăng nhập hoặc dữ liệu mật trong các câu nhắc.
 #AD.3.2    Level: 2    Role: D
 Xác minh rằng các biện pháp kiểm soát kỹ thuật (lọc bối cảnh được phê duyệt, xóa nội dung phía khách hàng) tự động loại bỏ các thông tin nhạy cảm.
 #AD.3.3    Level: 3    Role: D/V
 Xác minh rằng các prompt và phản hồi được phân tách token, mã hóa trong quá trình truyền và lưu trữ, đồng thời thời gian lưu trữ tuân thủ chính sách phân loại dữ liệu.

---

### AD.4 Xác thực mã do AI tạo ra

Phát hiện và khắc phục các lỗ hổng bảo mật do kết quả đầu ra của AI gây ra trước khi mã được hợp nhất hoặc triển khai.

 #AD.4.1    Level: 1    Role: D/V
 Xác nhận rằng mã do AI tạo ra luôn được kiểm tra bởi con người.
 #AD.4.2    Level: 2    Role: D
 Xác minh rằng các trình quét tự động (SAST/IAST/DAST) được chạy trên mọi pull request chứa mã do AI tạo và chặn việc gộp nếu phát hiện các lỗi nghiêm trọng.
 #AD.4.3    Level: 3    Role: D/V
 Xác minh rằng việc kiểm thử ngẫu nhiên phân biệt hoặc kiểm thử dựa trên thuộc tính chứng minh các hành vi quan trọng về bảo mật (ví dụ: xác thực đầu vào, logic ủy quyền).

---

### AD.5 Khả năng giải thích và truy xuất nguồn gốc của các gợi ý mã nguồn

Cung cấp cho kiểm toán viên và nhà phát triển cái nhìn sâu sắc về lý do tại sao một đề xuất được đưa ra và cách nó phát triển như thế nào.

 #AD.5.1    Level: 1    Role: D/V
 Xác minh rằng các cặp câu lệnh/phản hồi được ghi lại cùng với các ID cam kết.
 #AD.5.2    Level: 2    Role: D
 Xác nhận rằng các nhà phát triển có thể hiển thị các trích dẫn mô hình (đoạn trích đào tạo, tài liệu) hỗ trợ một đề xuất.
 #AD.5.3    Level: 3    Role: D/V
 Xác minh rằng các báo cáo giải thích được lưu trữ cùng với hiện vật thiết kế và được tham chiếu trong các đánh giá bảo mật, đảm bảo tuân thủ các nguyên tắc truy xuất nguồn gốc của ISO/IEC 42001.

---

### AD.6 Phản hồi liên tục & Tinh chỉnh mô hình

Cải thiện hiệu suất bảo mật mô hình theo thời gian trong khi ngăn chặn sự trượt tiêu cực.

 #AD.6.1    Level: 1    Role: D/V
 Xác nhận rằng các nhà phát triển có thể đánh dấu các đề xuất không an toàn hoặc không tuân thủ, và các đánh dấu này được theo dõi.
 #AD.6.2    Level: 2    Role: D
 Xác nhận rằng phản hồi tổng hợp được sử dụng để điều chỉnh tinh chỉnh định kỳ hoặc tạo ra nội dung tăng cường truy xuất với các tập hợp mã hóa bảo mật đã được kiểm duyệt (ví dụ: Bảng mẹo OWASP).
 #AD.6.3    Level: 3    Role: D/V
 Xác minh rằng bộ công cụ đánh giá vòng kín chạy các bài kiểm tra hồi quy sau mỗi lần tinh chỉnh; các chỉ số bảo mật phải đạt hoặc vượt mức chuẩn trước đó trước khi triển khai.

---

#### Tài liệu tham khảo

NIST AI Risk Management Framework 1.0
ISO/IEC 42001:2023 — AI Management Systems Requirements
OWASP Secure Coding Practices — Quick Reference Guide

## Phụ lục E: Ví dụ về công cụ và khung làm việc

### Mục tiêu

Chương này cung cấp các ví dụ về công cụ và khung làm việc có thể hỗ trợ việc triển khai hoặc thực hiện một yêu cầu AISVS cụ thể. Những ví dụ này không được xem như là khuyến nghị hay xác nhận bởi nhóm AISVS hoặc dự án An ninh GenAI của OWASP.

---

### AE.1 Quản trị Dữ liệu Đào tạo & Quản lý Thiên lệch

Công cụ được sử dụng cho phân tích dữ liệu, quản trị và quản lý thiên vị.

 #AE.1.1    Section: 1.1
 Công cụ kiểm kê dữ liệu: Các công cụ quản lý kiểm kê dữ liệu như...
 #AE.1.2    Section: 1.2
 Mã hóa khi truyền dữ liệu Sử dụng TLS cho các ứng dụng dựa trên HTTPS, với các công cụ như openSSL và python's`ssl`thư viện.

---

### AE.2 Xác thực đầu vào của người dùng

Công cụ để xử lý và xác thực dữ liệu đầu vào của người dùng.

 #AE.2.1    Section: 2.1
 Công cụ phòng thủ tấn công Prompt Injection: Sử dụng các công cụ guardrail như NeMo của NVIDIA hoặc Guardrails AI.

---

## Quản trị Dữ liệu Đào tạo C1 & Quản lý Thiên kiến

### C1.1 Nguồn gốc Dữ liệu Đào tạo

Duy trì một kho dữ liệu có thể kiểm chứng tất cả các bộ dữ liệu, chỉ chấp nhận các nguồn tin cậy, và ghi lại mọi thay đổi để có thể kiểm tra.

 #1.1.1    Level: 1    Role: D/V
 Xác nhận rằng một danh mục cập nhật về mọi nguồn dữ liệu huấn luyện (nguồn gốc, người quản lý/chủ sở hữu, giấy phép, phương pháp thu thập, các ràng buộc sử dụng dự định và lịch sử xử lý) được duy trì.


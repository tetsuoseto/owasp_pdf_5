# Sử dụng AISVS

Tiêu chuẩn Xác minh An ninh Trí tuệ Nhân tạo (AISVS) quy định các yêu cầu an ninh cho các ứng dụng và dịch vụ AI hiện đại, tập trung vào các khía cạnh trong tầm kiểm soát của nhà phát triển ứng dụng.

AISVS dành cho bất kỳ ai phát triển hoặc đánh giá bảo mật các ứng dụng AI, bao gồm các nhà phát triển, kiến trúc sư, kỹ sư bảo mật và kiểm toán viên. Chương này giới thiệu cấu trúc và cách sử dụng AISVS, bao gồm các cấp độ xác minh và các trường hợp sử dụng dự kiến.

## Các cấp độ xác minh bảo mật Trí tuệ Nhân tạo

AISVS xác định ba cấp độ xác minh bảo mật tăng dần. Mỗi cấp độ thêm chiều sâu và độ phức tạp, cho phép các tổ chức điều chỉnh mức độ bảo mật phù hợp với mức độ rủi ro của hệ thống AI của họ.

Các tổ chức có thể bắt đầu từ Cấp 1 và dần dần áp dụng các cấp cao hơn khi mức độ trưởng thành về bảo mật và mức độ tiếp xúc với mối đe dọa tăng lên.

### Định nghĩa các cấp độ

Mỗi yêu cầu trong AISVS phiên bản 1.0 được phân loại vào một trong các cấp độ sau:

#### Yêu cầu cấp độ 1

Cấp độ 1 bao gồm các yêu cầu bảo mật quan trọng và nền tảng nhất. Chúng tập trung vào việc ngăn chặn các cuộc tấn công phổ biến không phụ thuộc vào các điều kiện tiên quyết hoặc lỗ hổng khác. Hầu hết các biện pháp kiểm soát ở Cấp độ 1 đều dễ thực hiện hoặc đủ thiết yếu để biện minh cho nỗ lực triển khai.

#### Yêu cầu cấp độ 2

Cấp độ 2 giải quyết các cuộc tấn công nâng cao hơn hoặc ít phổ biến hơn, cũng như các biện pháp phòng thủ nhiều lớp chống lại các mối đe dọa phổ biến. Những yêu cầu này có thể bao gồm logic phức tạp hơn hoặc nhắm vào các điều kiện tiên quyết cụ thể của cuộc tấn công.

#### Yêu cầu cấp độ 3

Cấp độ 3 bao gồm các biện pháp kiểm soát thường khó thực hiện hơn hoặc áp dụng theo tình huống. Những biện pháp này thường đại diện cho các cơ chế phòng thủ sâu hoặc các biện pháp giảm thiểu tấn công đặc thù, có mục tiêu hoặc có độ phức tạp cao.

### Vai trò (D/V)

Mỗi yêu cầu AISVS được đánh dấu theo đối tượng chính:

* D – Các yêu cầu tập trung vào nhà phát triển
* V – Yêu cầu tập trung vào người kiểm tra/đánh giá
* D/V – Liên quan đến cả nhà phát triển và người kiểm chứng


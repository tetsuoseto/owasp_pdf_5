# Bảo mật Hạ tầng, Cấu hình và Triển khai C4

## Mục tiêu Kiểm soát

Hạ tầng AI phải được củng cố để chống lại việc leo thang đặc quyền, can thiệp chuỗi cung ứng, và di chuyển ngang thông qua cấu hình bảo mật, cách ly trong thời gian chạy, quy trình triển khai tin cậy, và giám sát toàn diện. Chỉ có các thành phần và cấu hình hạ tầng được ủy quyền, xác thực mới được đưa vào sản xuất thông qua các quy trình kiểm soát đảm bảo an ninh, tính toàn vẹn, và khả năng kiểm tra.

Mục tiêu bảo mật cốt lõi: Chỉ các thành phần hạ tầng được ký mật mã và quét lỗ hổng mới được đưa vào môi trường sản xuất thông qua các đường ống kiểm tra tự động, đảm bảo thực thi chính sách bảo mật và duy trì các bản ghi kiểm toán không thể thay đổi.

---

## C4.1 Cô lập Môi trường Chạy thời gian

Ngăn chặn việc thoát khỏi container và leo thang đặc quyền thông qua các nguyên thủy cách ly ở cấp nhân và các kiểm soát truy cập bắt buộc.

|   #   | Description                                                                                                                                                                                                                   | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.1.1 | Xác minh rằng tất cả các container AI loại bỏ TẤT CẢ các quyền hạn Linux ngoại trừ CAP_SETUID, CAP_SETGID và các quyền hạn được yêu cầu rõ ràng đã được ghi chép trong các tiêu chuẩn bảo mật.                                |   1   | D/V  |
| 4.1.2 | Xác minh rằng các hồ sơ seccomp chặn tất cả các syscall ngoại trừ những syscall có trong danh sách cho phép đã được phê duyệt trước, với các vi phạm sẽ kết thúc container và tạo ra các cảnh báo bảo mật.                    |   1   | D/V  |
| 4.1.3 | Xác minh rằng các khối lượng công việc AI chạy với hệ thống tập tin gốc chỉ đọc, tmpfs cho dữ liệu tạm thời, và các ổ đĩa được đặt tên cho dữ liệu bền với tùy chọn gắn noexec được thực thi.                                 |   2   | D/V  |
| 4.1.4 | Xác minh rằng việc giám sát thời gian thực dựa trên eBPF (Falco, Tetragon hoặc tương đương) phát hiện các cố gắng leo thang đặc quyền và tự động chấm dứt các tiến trình vi phạm trong thời gian đáp ứng yêu cầu của tổ chức. |   2   | D/V  |
| 4.1.5 | Xác minh rằng các khối lượng công việc AI có nguy cơ cao được thực thi trong môi trường cách ly phần cứng (Intel TXT, AMD SVM hoặc các nút bare-metal chuyên dụng) với việc xác thực chứng nhận.                              |   3   | D/V  |

---

## C4.2 Đường ống Xây dựng & Triển khai An toàn

Đảm bảo tính toàn vẹn mật mã và an ninh chuỗi cung ứng thông qua các bản build có thể tái tạo và các sản phẩm được ký số.

|   #   | Description                                                                                                                                                                                        | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.2.1 | Xác minh rằng hạ tầng dưới dạng mã được quét bằng công cụ (tfsec, Checkov hoặc Terrascan) trên mỗi lần commit, chặn các lần hợp nhất có phát hiện mức độ nghiêm trọng CAO hoặc NGHIÊM TRỌNG.       |   1   | D/V  |
| 4.2.2 | Xác minh rằng việc xây dựng container có thể tái tạo với các hàm băm SHA256 giống hệt nhau giữa các lần xây dựng và tạo các chứng nhận nguồn gốc SLSA Cấp độ 3 được ký bằng Sigstore.              |   1   | D/V  |
| 4.2.3 | Xác minh rằng các hình ảnh container nhúng CycloneDX hoặc SPDX SBOM và được ký bằng Cosign trước khi đẩy lên registry, với các hình ảnh chưa ký bị từ chối khi triển khai.                         |   2   | D/V  |
| 4.2.4 | Xác minh rằng các pipeline CI/CD sử dụng token OIDC từ HashiCorp Vault, vai trò IAM của AWS, hoặc Azure Managed Identity với thời gian tồn tại không vượt quá giới hạn chính sách bảo mật tổ chức. |   2   | D/V  |
| 4.2.5 | Xác minh rằng các chữ ký Cosign và nguồn gốc SLSA được kiểm tra hợp lệ trong quá trình triển khai trước khi thực thi container và các lỗi xác minh sẽ khiến việc triển khai bị thất bại.           |   2   | D/V  |
| 4.2.6 | Xác minh rằng các môi trường xây dựng chạy trong các container hoặc máy ảo tạm thời không có lưu trữ lâu dài và được cách ly mạng khỏi các VPC sản xuất.                                           |   2   | D/V  |

---

## C4.3 An ninh Mạng & Kiểm soát Truy cập

Triển khai mạng không tin cậy với các chính sách từ chối mặc định và truyền thông được mã hóa.

|   #   | Description                                                                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.3.1 | Xác minh rằng Kubernetes NetworkPolicies hoặc bất kỳ giải pháp tương đương nào thực hiện việc từ chối mặc định đối với ingress/egress với các quy tắc cho phép rõ ràng cho các cổng cần thiết (443, 8080, v.v.). |   1   | D/V  |
| 4.3.2 | Xác minh rằng SSH (cổng 22), RDP (cổng 3389) và các điểm cuối metadata đám mây (169.254.169.254) bị chặn hoặc yêu cầu xác thực dựa trên chứng chỉ.                                                               |   1   | D/V  |
| 4.3.3 | Xác minh rằng lưu lượng ra được lọc qua các proxy HTTP/HTTPS (Squid, Istio hoặc các cổng NAT đám mây) với danh sách cho phép theo miền và các yêu cầu bị chặn được ghi nhật ký.                                  |   2   | D/V  |
| 4.3.4 | Xác minh rằng giao tiếp giữa các dịch vụ sử dụng TLS hai chiều với các chứng chỉ được luân chuyển theo chính sách tổ chức và việc xác thực chứng chỉ được thực thi (không sử dụng cờ bỏ qua xác minh).           |   2   | D/V  |
| 4.3.5 | Xác minh rằng hạ tầng AI hoạt động trong các VPC/VNet riêng biệt không có truy cập internet trực tiếp và chỉ giao tiếp qua các gateway NAT hoặc máy chủ trung gian (bastion hosts).                              |   2   | D/V  |

---

## C4.4 Quản lý Bí mật & Khóa Mã hóa

Bảo vệ thông tin đăng nhập thông qua lưu trữ được hỗ trợ phần cứng và xoay vòng tự động với truy cập không tin cậy.

|   #   | Description                                                                                                                                                                                              | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.4.1 | Xác minh rằng các bí mật được lưu trữ trong HashiCorp Vault, AWS Secrets Manager, Azure Key Vault, hoặc Google Secret Manager với mã hóa khi lưu trữ sử dụng AES-256.                                    |   1   | D/V  |
| 4.4.2 | Xác minh rằng các khóa mật mã được tạo ra trong các thiết bị HSM đạt chuẩn FIPS 140-2 Cấp 2 (AWS CloudHSM, Azure Dedicated HSM) với việc xoay vòng khóa theo chính sách mật mã của tổ chức.              |   1   | D/V  |
| 4.4.3 | Xác nhận rằng việc xoay vòng bí mật được tự động hóa với triển khai không gián đoạn cùng với việc xoay vòng ngay lập tức được kích hoạt bởi các thay đổi nhân sự hoặc sự cố an ninh.                     |   2   | D/V  |
| 4.4.4 | Xác minh rằng các ảnh container được quét bằng các công cụ (GitLeaks, TruffleHog hoặc detect-secrets) để chặn các bản build chứa khóa API, mật khẩu hoặc chứng chỉ.                                      |   2   | D/V  |
| 4.4.5 | Xác minh rằng việc truy cập bí mật sản xuất yêu cầu MFA với các token phần cứng (YubiKey, FIDO2) và được ghi lại bởi các nhật ký kiểm toán không thể thay đổi với danh tính người dùng và dấu thời gian. |   2   | D/V  |
| 4.4.6 | Xác minh rằng các bí mật được tiêm qua Kubernetes secrets, các volume được gắn kết hoặc các init container và đảm bảo rằng bí mật không bao giờ được nhúng trong biến môi trường hoặc hình ảnh.          |   2   | D/V  |

---

## C4.5 Phân vùng tải công việc AI và Xác thực

Cô lập các mô hình AI không đáng tin cậy trong các hộp cát an toàn với phân tích hành vi toàn diện.

|   #   | Description                                                                                                                                                                                                                                | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.5.1 | Xác nhận rằng các mô hình AI bên ngoài thực thi trong gVisor, microVMs (chẳng hạn như Firecracker, CrossVM) hoặc các container Docker với các cờ --security-opt=no-new-privileges và --read-only.                                          |   1   | D/V  |
| 4.5.2 | Xác nhận rằng các môi trường sandbox không có kết nối mạng (--network=none) hoặc chỉ truy cập localhost với tất cả các yêu cầu bên ngoài bị chặn bởi quy tắc iptables.                                                                     |   1   | D/V  |
| 4.5.3 | Xác minh rằng việc xác nhận mô hình AI bao gồm kiểm tra nhóm đỏ tự động với phạm vi kiểm tra được tổ chức xác định và phân tích hành vi để phát hiện cửa hậu.                                                                              |   2   | D/V  |
| 4.5.4 | Xác minh rằng trước khi một mô hình AI được đưa vào sản xuất, kết quả trong môi trường thử nghiệm (sandbox) của nó được ký số bằng mật mã bởi nhân sự an ninh được ủy quyền và được lưu trữ trong các nhật ký kiểm tra không thể thay đổi. |   2   | D/V  |
| 4.5.5 | Xác minh rằng các môi trường sandbox được hủy và tái tạo từ hình ảnh gốc giữa các lần đánh giá với việc làm sạch hoàn toàn hệ thống tập tin và bộ nhớ.                                                                                     |   2   | D/V  |

---

## C4.6 Giám sát An ninh Hạ tầng

Liên tục quét và giám sát hạ tầng với khắc phục tự động và cảnh báo thời gian thực.

|   #   | Description                                                                                                                                                                                                     | Level | Role |
| :---: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.6.1 | Xác minh rằng các ảnh container được quét theo lịch trình của tổ chức với các lỗ hổng NGHIÊM TRỌNG (CRITICAL) ngăn chặn việc triển khai dựa trên các ngưỡng rủi ro của tổ chức.                                 |   1   | D/V  |
| 4.6.2 | Xác minh rằng hạ tầng đáp ứng các tiêu chuẩn CIS Benchmarks hoặc các kiểm soát NIST 800-53 với các ngưỡng tuân thủ do tổ chức xác định và tự động xử lý khắc phục cho các kiểm tra không đạt.                   |   1   | D/V  |
| 4.6.3 | Xác minh rằng các lỗ hổng có mức độ nghiêm trọng CAO được vá theo các mốc thời gian quản lý rủi ro của tổ chức với các quy trình khẩn cấp cho các CVE đang bị khai thác tích cực.                               |   2   | D/V  |
| 4.6.4 | Xác minh rằng các cảnh báo bảo mật tích hợp với các nền tảng SIEM (Splunk, Elastic hoặc Sentinel) sử dụng định dạng CEF hoặc STIX/TAXII với việc làm giàu tự động.                                              |   2   |  V   |
| 4.6.5 | Xác minh rằng các chỉ số hạ tầng được xuất khẩu tới hệ thống giám sát (Prometheus, DataDog) với bảng điều khiển SLA và báo cáo dành cho lãnh đạo.                                                               |   3   |  V   |
| 4.6.6 | Xác minh rằng sự sai lệch cấu hình được phát hiện bằng cách sử dụng các công cụ (Chef InSpec, AWS Config) theo yêu cầu giám sát của tổ chức với khả năng hoàn tác tự động đối với các thay đổi không được phép. |   2   | D/V  |

---

## C4.7 Quản lý Tài nguyên Hạ tầng AI

Ngăn chặn các cuộc tấn công làm cạn kiệt tài nguyên và đảm bảo phân bổ tài nguyên công bằng thông qua hạn ngạch và giám sát.

|   #   | Description                                                                                                                                                                                                      | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.7.1 | Xác minh rằng việc sử dụng GPU/TPU được giám sát với cảnh báo được kích hoạt tại các ngưỡng được tổ chức xác định và tự động mở rộng hoặc cân bằng tải được kích hoạt dựa trên các chính sách quản lý công suất. |   1   | D/V  |
| 4.7.2 | Xác minh rằng các chỉ số khối lượng công việc AI (độ trễ suy luận, thông lượng, tỷ lệ lỗi) được thu thập theo yêu cầu giám sát của tổ chức và được đối chiếu với việc sử dụng hạ tầng.                           |   1   | D/V  |
| 4.7.3 | Xác minh rằng Kubernetes ResourceQuotas hoặc các cơ chế tương đương giới hạn từng workload theo chính sách phân bổ tài nguyên của tổ chức với các giới hạn cứng được thực thi.                                   |   2   | D/V  |
| 4.7.4 | Xác minh rằng việc giám sát chi phí theo dõi chi tiêu theo từng khối lượng công việc/người thuê với các cảnh báo dựa trên ngưỡng ngân sách tổ chức và các kiểm soát tự động để ngăn ngừa vượt ngân sách.         |   2   |  V   |
| 4.7.5 | Xác minh rằng lập kế hoạch dung lượng sử dụng dữ liệu lịch sử với các khoảng thời gian dự báo được tổ chức xác định và cung cấp tài nguyên tự động dựa trên các mẫu nhu cầu.                                     |   3   |  V   |
| 4.7.6 | Xác minh rằng việc cạn kiệt tài nguyên kích hoạt các công tắc ngắt theo yêu cầu phản hồi của tổ chức, bao gồm giới hạn tốc độ dựa trên chính sách năng lực và cô lập khối lượng công việc.                       |   2   | D/V  |

---

## C4.8 Kiểm soát Tách biệt Môi trường & Thúc đẩy

Thiết lập ranh giới môi trường nghiêm ngặt với các cổng thăng tiến tự động và xác thực bảo mật.

|   #   | Description                                                                                                                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.8.1 | Xác minh rằng các môi trường phát triển/kiểm thử/sản xuất chạy trong các VPC/VNet riêng biệt mà không có vai trò IAM, nhóm bảo mật hoặc kết nối mạng dùng chung.                                                                    |   1   | D/V  |
| 4.8.2 | Xác nhận rằng việc thăng môi trường yêu cầu phê duyệt từ nhân sự được tổ chức xác định có thẩm quyền, kèm theo chữ ký mật mã và nhật ký kiểm toán không thể thay đổi.                                                               |   1   | D/V  |
| 4.8.3 | Xác nhận rằng các môi trường sản xuất chặn truy cập SSH, vô hiệu hóa các điểm cuối gỡ lỗi và yêu cầu các yêu cầu thay đổi kèm theo thông báo trước theo quy định của tổ chức, ngoại trừ các trường hợp khẩn cấp.                    |   2   | D/V  |
| 4.8.4 | Xác minh rằng các thay đổi hạ tầng dưới dạng mã yêu cầu phải được đồng nghiệp xem xét kèm kiểm thử tự động và quét bảo mật trước khi gộp vào nhánh chính.                                                                           |   2   | D/V  |
| 4.8.5 | Xác minh rằng dữ liệu không thuộc môi trường sản xuất được ẩn danh theo các yêu cầu bảo mật của tổ chức, tạo dữ liệu tổng hợp hoặc che dấu dữ liệu hoàn toàn với việc loại bỏ thông tin cá nhân nhận dạng (PII) đã được kiểm chứng. |   2   | D/V  |
| 4.8.6 | Xác minh rằng các cổng thăng tiến bao gồm các bài kiểm tra bảo mật tự động (SAST, DAST, quét container) với yêu cầu không có phát hiện CRITICAL để được phê duyệt.                                                                  |   2   | D/V  |

---

## Sao lưu & Phục hồi Cơ sở hạ tầng C4.9

Đảm bảo độ bền vững của hạ tầng thông qua các bản sao lưu tự động, quy trình khôi phục đã được kiểm tra và khả năng phục hồi sau thảm họa.

|   #   | Description                                                                                                                                                              | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.9.1 | Xác minh rằng các cấu hình hạ tầng được sao lưu theo lịch sao lưu của tổ chức tới các khu vực địa lý tách biệt, với việc triển khai chiến lược sao lưu 3-2-1.            |   1   | D/V  |
| 4.9.2 | Xác minh rằng các hệ thống sao lưu hoạt động trong mạng riêng biệt với thông tin xác thực riêng và lưu trữ cách ly để bảo vệ chống lại ransomware.                       |   2   | D/V  |
| 4.9.3 | Xác minh rằng các thủ tục phục hồi được kiểm tra và xác nhận thông qua kiểm thử tự động theo lịch trình tổ chức với các mục tiêu RTO và RPO đáp ứng yêu cầu của tổ chức. |   2   |  V   |
| 4.9.4 | Xác minh rằng khôi phục sau thảm họa bao gồm các sách hướng dẫn chạy riêng cho AI với việc phục hồi trọng số mô hình, xây dựng lại cụm GPU và bản đồ phụ thuộc dịch vụ.  |   3   |  V   |

---

## C4.10 Tuân thủ và Quản trị Hạ tầng

Duy trì tuân thủ quy định thông qua đánh giá liên tục, ghi chép và kiểm soát tự động hóa.

|   #    | Description                                                                                                                                                          | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.10.1 | Xác minh rằng việc tuân thủ hạ tầng được đánh giá theo lịch trình tổ chức dựa trên các kiểm soát SOC 2, ISO 27001 hoặc FedRAMP với việc thu thập bằng chứng tự động. |   2   | D/V  |
| 4.10.2 | Xác minh rằng tài liệu hạ tầng bao gồm sơ đồ mạng, bản đồ luồng dữ liệu và mô hình đe dọa được cập nhật theo các yêu cầu quản lý thay đổi tổ chức.                   |   2   |  V   |
| 4.10.3 | Xác minh rằng các thay đổi cơ sở hạ tầng trải qua đánh giá tác động tuân thủ tự động với quy trình phê duyệt theo quy định cho các sửa đổi có rủi ro cao.            |   3   | D/V  |

---

## C4.11 An ninh Phần cứng AI

Bảo mật các thành phần phần cứng đặc thù cho AI bao gồm GPU, TPU và các bộ tăng tốc AI chuyên dụng.

|   #    | Description                                                                                                                                                                                        | Level | Role |
| :----: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.11.1 | Xác minh rằng firmware bộ tăng tốc AI (BIOS GPU, firmware TPU) được xác thực bằng chữ ký mật mã và được cập nhật theo lịch trình quản lý bản vá của tổ chức.                                       |   2   | D/V  |
| 4.11.2 | Xác minh rằng trước khi thực hiện tải công việc, tính toàn vẹn của bộ tăng tốc AI được xác nhận bởi chứng thực phần cứng sử dụng TPM 2.0, Intel TXT hoặc AMD SVM.                                  |   2   | D/V  |
| 4.11.3 | Xác minh rằng bộ nhớ GPU được cô lập giữa các khối lượng công việc bằng cách sử dụng SR-IOV, MIG (GPU đa thể hiện), hoặc phân vùng phần cứng tương đương với việc làm sạch bộ nhớ giữa các tác vụ. |   2   | D/V  |
| 4.11.4 | Xác minh rằng chuỗi cung ứng phần cứng AI bao gồm việc kiểm tra nguồn gốc bằng chứng chỉ từ nhà sản xuất và xác minh bao bì chống giả mạo.                                                         |   3   |  V   |
| 4.11.5 | Xác minh rằng các mô-đun bảo mật phần cứng (HSM) bảo vệ trọng số mô hình AI và khóa mật mã với chứng nhận FIPS 140-2 Cấp 3 hoặc Tiêu chí Chung EAL4+.                                              |   3   | D/V  |

---

## C4.12 Cơ sở hạ tầng AI Biên & Phân tán

Triển khai AI phân tán an toàn bao gồm điện toán biên, học liên kết và kiến trúc đa địa điểm.

|   #    | Description                                                                                                                                                                    | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.12.1 | Xác minh rằng các thiết bị AI biên xác thực với hạ tầng trung tâm sử dụng mutual TLS với chứng chỉ thiết bị được xoay vòng theo chính sách quản lý chứng chỉ của tổ chức.      |   2   | D/V  |
| 4.12.2 | Xác minh rằng các thiết bị biên thực hiện cơ chế khởi động an toàn với chữ ký đã được xác minh và bảo vệ chống quay lui, ngăn chặn các cuộc tấn công hạ cấp phần mềm hệ thống. |   2   | D/V  |
| 4.12.3 | Xác minh rằng sự phối hợp AI phân tán sử dụng các thuật toán đồng thuận chịu lỗi Byzantine với việc xác thực người tham gia và phát hiện nút độc hại.                          |   3   | D/V  |
| 4.12.4 | Xác minh rằng giao tiếp từ edge đến cloud bao gồm điều tiết băng thông, nén dữ liệu và khả năng hoạt động ngoại tuyến với lưu trữ cục bộ an toàn.                              |   3   | D/V  |

---

## C4.13 An ninh Hạ tầng Đa Đám mây & Hỗn hợp

Bảo mật khối lượng công việc AI trên nhiều nhà cung cấp đám mây và triển khai đám mây lai kết hợp với tại chỗ.

|   #    | Description                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.13.1 | Xác minh rằng các triển khai AI đa đám mây sử dụng liên kết danh tính không phụ thuộc vào nền tảng đám mây (OIDC, SAML) với quản lý chính sách tập trung trên các nhà cung cấp.                |   2   | D/V  |
| 4.13.2 | Xác minh rằng việc chuyển dữ liệu đa đám mây sử dụng mã hóa đầu cuối với khóa do khách hàng quản lý và các kiểm soát cư trú dữ liệu được thi hành theo từng khu vực pháp lý.                   |   2   | D/V  |
| 4.13.3 | Xác minh rằng các khối lượng công việc AI đám mây lai thực hiện chính sách bảo mật nhất quán trên cả môi trường tại chỗ và đám mây với việc giám sát và cảnh báo thống nhất.                   |   2   | D/V  |
| 4.13.4 | Xác minh rằng việc ngăn chặn khóa nhà cung cấp đám mây bao gồm cơ sở hạ tầng dưới dạng mã có thể di động, API chuẩn hóa và khả năng xuất dữ liệu với công cụ chuyển đổi định dạng.             |   3   |  V   |
| 4.13.5 | Xác minh rằng tối ưu hóa chi phí đa đám mây bao gồm các biện pháp kiểm soát bảo mật ngăn chặn việc phân tán tài nguyên cũng như các khoản phí chuyển dữ liệu không được phép giữa các đám mây. |   3   |  V   |

---

## C4.14 Tự động hóa Hạ tầng & Bảo mật GitOps

Tự động hóa các đường ống hạ tầng bảo mật và quy trình làm việc GitOps cho quản lý hạ tầng AI.

|   #    | Description                                                                                                                                                                                    | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.14.1 | Xác minh rằng các kho GitOps yêu cầu các commit được ký bằng khóa GPG và áp dụng các quy tắc bảo vệ nhánh ngăn cấm đẩy trực tiếp vào các nhánh chính.                                          |   2   | D/V  |
| 4.14.2 | Xác minh rằng tự động hóa hạ tầng bao gồm phát hiện sai lệch với khả năng khắc phục tự động và hoàn tác được kích hoạt theo yêu cầu phản hồi của tổ chức đối với các thay đổi không được phép. |   2   | D/V  |
| 4.14.3 | Xác minh rằng việc cung cấp hạ tầng tự động bao gồm xác thực chính sách bảo mật với việc chặn triển khai đối với các cấu hình không tuân thủ.                                                  |   2   | D/V  |
| 4.14.4 | Xác minh rằng các bí mật tự động hóa hạ tầng được quản lý thông qua các bộ điều khiển bí mật bên ngoài (External Secrets Operator, Bank-Vaults) với việc xoay vòng tự động.                    |   2   | D/V  |
| 4.14.5 | Xác minh rằng hạ tầng tự phục hồi bao gồm việc kết hợp sự kiện bảo mật với phản ứng sự cố tự động và quy trình thông báo các bên liên quan.                                                    |   3   |  V   |

---

## C4.15 An ninh Hạ tầng Kháng Lượng tử

Chuẩn bị cơ sở hạ tầng AI để đối phó với các mối đe dọa từ máy tính lượng tử thông qua mật mã hậu lượng tử và các giao thức an toàn lượng tử.

|   #    | Description                                                                                                                                                                                                  | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.15.1 | Xác minh rằng cơ sở hạ tầng AI triển khai các thuật toán mật mã hậu lượng tử được NIST phê duyệt (CRYSTALS-Kyber, CRYSTALS-Dilithium, SPHINCS+) cho trao đổi khóa và chữ ký số.                              |   3   | D/V  |
| 4.15.2 | Xác minh rằng các hệ thống phân phối khóa lượng tử (QKD) được triển khai cho các liên lạc AI bảo mật cao với các giao thức quản lý khóa an toàn trước lượng tử.                                              |   3   | D/V  |
| 4.15.3 | Xác minh rằng các khung công tác linh hoạt mật mã cho phép di chuyển nhanh chóng sang các thuật toán hậu lượng tử mới với việc tự động xoay vòng chứng chỉ và khóa.                                          |   3   | D/V  |
| 4.15.4 | Xác minh rằng mô hình hóa mối đe dọa lượng tử đánh giá mức độ dễ tổn thương của cơ sở hạ tầng AI đối với các cuộc tấn công lượng tử cùng với các thời hạn di chuyển đã được ghi chép và các đánh giá rủi ro. |   3   |  V   |
| 4.15.5 | Xác minh rằng các hệ thống mật mã lai cổ điển-lượng tử cung cấp phương pháp phòng thủ đa lớp trong giai đoạn chuyển tiếp lượng tử với việc giám sát hiệu suất.                                               |   3   | D/V  |

---

## C4.16 Tính Toán Bảo Mật & Khu Vực An Toàn

Bảo vệ khối lượng công việc AI và trọng số mô hình bằng cách sử dụng môi trường thực thi đáng tin cậy dựa trên phần cứng và công nghệ điện toán bảo mật.

|   #    | Description                                                                                                                                                              | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.16.1 | Xác minh rằng các mô hình AI nhạy cảm được thực thi bên trong các vùng bảo vệ Intel SGX, AMD SEV-SNP hoặc ARM TrustZone với bộ nhớ được mã hóa và xác thực chứng nhận.   |   3   | D/V  |
| 4.16.2 | Xác minh rằng các container bảo mật (Kata Containers, gVisor với tính toán bảo mật) cách ly các khối lượng công việc AI bằng mã hóa bộ nhớ được thực thi phần cứng.      |   3   | D/V  |
| 4.16.3 | Xác minh rằng xác thực từ xa kiểm tra tính toàn vẹn của enclave trước khi tải các mô hình AI với bằng chứng mật mã về tính xác thực của môi trường thực thi.             |   3   | D/V  |
| 4.16.4 | Xác minh rằng các dịch vụ suy luận AI bảo mật ngăn chặn việc trích xuất mô hình thông qua tính toán mã hóa với trọng số mô hình được niêm phong và thực thi được bảo vệ. |   3   | D/V  |
| 4.16.5 | Xác minh rằng việc điều phối môi trường thực thi tin cậy quản lý vòng đời khu vực bảo mật với xác thực từ xa và kênh truyền thông được mã hóa.                           |   3   | D/V  |
| 4.16.6 | Xác minh rằng tính toán đa bên bảo mật (SMPC) cho phép đào tạo trí tuệ nhân tạo hợp tác mà không tiết lộ bộ dữ liệu cá nhân hoặc các tham số mô hình.                    |   3   | D/V  |

---

## C4.17 Cơ sở hạ tầng Không Kiến thức

Triển khai các hệ thống bằng chứng không tiết lộ kiến thức (zero-knowledge proof) để xác minh và chứng thực AI bảo vệ quyền riêng tư mà không tiết lộ thông tin nhạy cảm.

|   #    | Description                                                                                                                                                                                         | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.17.1 | Xác minh rằng các bằng chứng không tiết lộ thông tin (ZK-SNARKs, ZK-STARKs) xác thực tính toàn vẹn của mô hình AI và nguồn gốc huấn luyện mà không làm lộ trọng số mô hình hoặc dữ liệu huấn luyện. |   3   | D/V  |
| 4.17.2 | Xác minh rằng các hệ thống xác thực dựa trên ZK cho phép xác thực người dùng bảo vệ quyền riêng tư đối với các dịch vụ AI mà không tiết lộ thông tin liên quan đến danh tính.                       |   3   | D/V  |
| 4.17.3 | Xác nhận rằng các giao thức giao điểm tập hợp riêng tư (PSI) cho phép khớp dữ liệu an toàn cho AI liên kết mà không làm lộ các bộ dữ liệu riêng lẻ.                                                 |   3   | D/V  |
| 4.17.4 | Xác minh rằng các hệ thống học máy không tri thức (ZKML) cho phép suy luận AI có thể xác minh với bằng chứng mật mã về tính toán đúng đắn.                                                          |   3   | D/V  |
| 4.17.5 | Xác minh rằng ZK-rollups cung cấp xử lý giao dịch AI có khả năng mở rộng và bảo vệ quyền riêng tư với việc xác minh theo lô và giảm tải tính toán.                                                  |   3   | D/V  |

---

## C4.18 Phòng chống tấn công kênh phụ

Bảo vệ hạ tầng AI khỏi các cuộc tấn công kênh bên dựa trên thời gian, năng lượng, điện từ và bộ nhớ đệm có thể làm rò rỉ thông tin nhạy cảm.

|   #    | Description                                                                                                                                                                                   | Level | Role |
| :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.18.1 | Xác minh rằng thời gian suy luận AI được chuẩn hóa bằng cách sử dụng các thuật toán thời gian không đổi và kỹ thuật đệm để ngăn chặn các cuộc tấn công trích xuất mô hình dựa trên thời gian. |   3   | D/V  |
| 4.18.2 | Xác nhận rằng bảo vệ phân tích công suất bao gồm việc tiêm nhiễu, lọc đường nguồn và các mẫu thực thi ngẫu nhiên cho phần cứng AI.                                                            |   3   | D/V  |
| 4.18.3 | Xác minh rằng biện pháp giảm thiểu kênh phụ dựa trên bộ nhớ đệm sử dụng phân vùng bộ nhớ đệm, ngẫu nhiên hóa và lệnh xóa để ngăn chặn rò rỉ thông tin.                                        |   3   | D/V  |
| 4.18.4 | Xác minh rằng bảo vệ phát xạ điện từ bao gồm che chắn, lọc tín hiệu và xử lý ngẫu nhiên để ngăn chặn các cuộc tấn công kiểu TEMPEST.                                                          |   3   | D/V  |
| 4.18.5 | Xác minh rằng các biện pháp phòng chống kênh bên vi kiến trúc bao gồm các kiểm soát thực thi suy đoán và che giấu mẫu truy cập bộ nhớ.                                                        |   3   | D/V  |

---

## C4.19 Bảo mật Phần cứng AI Chuyên biệt & Nhận dạng thần kinh

Bảo mật các kiến trúc phần cứng AI mới nổi bao gồm chip thần kinh (neuromorphic), FPGA, ASIC tùy chỉnh và hệ thống tính toán quang học.

|   #    | Description                                                                                                                                                         | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.19.1 | Xác nhận rằng bảo mật chip neuromorphic bao gồm mã hóa mẫu xung, bảo vệ trọng số kết nối synaptic và xác thực quy tắc học dựa trên phần cứng.                       |   3   | D/V  |
| 4.19.2 | Xác minh rằng các bộ tăng tốc AI dựa trên FPGA thực hiện mã hóa luồng bit, cơ chế chống giả mạo và tải cấu hình an toàn với các bản cập nhật có xác thực.           |   3   | D/V  |
| 4.19.3 | Xác minh rằng bảo mật ASIC tùy chỉnh bao gồm các bộ xử lý bảo mật trên chip, gốc tin cậy phần cứng và lưu trữ khóa an toàn với khả năng phát hiện xâm nhập.         |   3   | D/V  |
| 4.19.4 | Xác minh rằng các hệ thống tính toán quang học thực hiện mã hóa quang học an toàn trước lượng tử, chuyển mạch quang tử bảo mật và xử lý tín hiệu quang được bảo vệ. |   3   | D/V  |
| 4.19.5 | Xác nhận rằng các chip AI lai analog-kỹ thuật số bao gồm tính toán analog an toàn, lưu trữ trọng số được bảo vệ và chuyển đổi analog-số được xác thực.              |   3   | D/V  |

---

## C4.20 Cơ sở hạ tầng tính toán bảo vệ quyền riêng tư

Triển khai các biện pháp kiểm soát hạ tầng cho tính toán bảo vệ quyền riêng tư để bảo vệ dữ liệu nhạy cảm trong quá trình xử lý và phân tích AI.

|   #    | Description                                                                                                                                                                                | Level | Role |
| :----: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 4.20.1 | Xác minh rằng hạ tầng mã hóa đồng dạng cho phép tính toán trên dữ liệu mã hóa đối với các khối lượng công việc AI nhạy cảm với việc xác minh tính toàn vẹn mật mã và giám sát hiệu suất.   |   3   | D/V  |
| 4.20.2 | Xác minh rằng các hệ thống truy xuất thông tin riêng tư cho phép truy vấn cơ sở dữ liệu mà không tiết lộ mẫu truy vấn thông qua bảo vệ mật mã đối với các mẫu truy cập.                    |   3   | D/V  |
| 4.20.3 | Xác minh rằng các giao thức tính toán đa bên bảo mật cho phép suy luận AI bảo vệ quyền riêng tư mà không tiết lộ các đầu vào cá nhân hoặc các phép tính trung gian.                        |   3   | D/V  |
| 4.20.4 | Xác minh rằng quản lý khóa bảo vệ quyền riêng tư bao gồm tạo khóa phân tán, mật mã ngưỡng, và xoay khóa an toàn với bảo vệ được hỗ trợ phần cứng.                                          |   3   | D/V  |
| 4.20.5 | Xác minh rằng hiệu suất tính toán bảo vệ quyền riêng tư được tối ưu hóa thông qua việc nhóm lệnh, lưu trữ tạm thời và tăng tốc phần cứng trong khi vẫn duy trì các đảm bảo bảo mật mật mã. |   3   | D/V  |

---

## C4.15 Bảo mật Tích hợp Đám mây Khung Đại lý & Triển khai Hỗn hợp

Các biện pháp kiểm soát bảo mật cho các khung tác nhân tích hợp đám mây với kiến trúc lai tại chỗ/đám mây.

|   #    | Description                                                                                                                        | Level | Role |
| :----: | ---------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 4.15.1 | Xác minh rằng tích hợp lưu trữ đám mây sử dụng mã hóa đầu cuối với quản lý khóa do đại lý kiểm soát.                               |   1   | D/V  |
| 4.15.2 | Xác minh rằng các ranh giới bảo mật của triển khai lai được xác định rõ ràng với các kênh truyền thông được mã hóa.                |   2   | D/V  |
| 4.15.3 | Xác minh rằng việc truy cập tài nguyên đám mây bao gồm xác thực không tin cậy (zero-trust) với xác thực liên tục.                  |   2   | D/V  |
| 4.15.4 | Xác minh rằng các yêu cầu về cư trú dữ liệu được thực thi thông qua xác nhận mật mã về vị trí lưu trữ.                             |   3   | D/V  |
| 4.15.5 | Xác minh rằng các đánh giá bảo mật của nhà cung cấp đám mây bao gồm mô hình hóa mối đe dọa cụ thể cho tác nhân và đánh giá rủi ro. |   3   | D/V  |

---

## Tài liệu tham khảo

* [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework)
* [CIS Controls v8](https://www.cisecurity.org/controls/v8)
* [OWASP Container Security Verification Standard](https://github.com/OWASP/Container-Security-Verification-Standard)
* [Kubernetes Security Best Practices](https://kubernetes.io/docs/concepts/security/)
* [SLSA Supply Chain Security Framework](https://slsa.dev/)
* [NIST SP 800-190: Application Container Security Guide](https://csrc.nist.gov/publications/detail/sp/800-190/final)
* [Cloud Security Alliance: Cloud Controls Matrix](https://cloudsecurityalliance.org/research/cloud-controls-matrix/)
* [ENISA: Secure Infrastructure Design](https://www.enisa.europa.eu/topics/critical-information-infrastructures-and-services)
* [NIST SP 800-53: Security Controls for Federal Information Systems](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)
* [ISO 27001:2022 Information Security Management](https://www.iso.org/standard/27001)
* [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
* [CIS Kubernetes Benchmark](https://www.cisecurity.org/benchmark/kubernetes)
* [FIPS 140-2 Security Requirements](https://csrc.nist.gov/publications/detail/fips/140/2/final)
* [NIST SP 800-207: Zero Trust Architecture](https://csrc.nist.gov/publications/detail/sp/800-207/final)
* [IEEE 2857: Privacy Engineering for AI Systems](https://standards.ieee.org/ieee/2857/7273/)
* [NIST SP 800-161: Cybersecurity Supply Chain Risk Management](https://csrc.nist.gov/publications/detail/sp/800-161/rev-1/final)
* [NIST Post-Quantum Cryptography Standards](https://csrc.nist.gov/Projects/post-quantum-cryptography)
* [Intel SGX Developer Guide](https://www.intel.com/content/www/us/en/developer/tools/software-guard-extensions/overview.html)
* [AMD SEV-SNP White Paper](https://www.amd.com/system/files/TechDocs/SEV-SNP-strengthening-vm-isolation-with-integrity-protection-and-more.pdf)
* [ARM TrustZone Technology](https://developer.arm.com/ip-products/security-ip/trustzone)
* [ZK-SNARKs: A Gentle Introduction](https://blog.ethereum.org/2016/12/05/zksnarks-in-a-nutshell/)
* [NIST SP 800-57: Cryptographic Key Management](https://csrc.nist.gov/publications/detail/sp/800-57-part-1/rev-5/final)
* [Side-Channel Attack Countermeasures](https://link.springer.com/book/10.1007/978-3-319-75268-6)
* [Neuromorphic Computing Security Challenges](https://ieeexplore.ieee.org/document/9458103)
* [FPGA Security: Fundamentals, Evaluation, and Countermeasures](https://link.springer.com/book/10.1007/978-3-319-90385-9)
* [Microsoft SEAL: Homomorphic Encryption Library](https://github.com/Microsoft/SEAL)
* [HElib: Homomorphic Encryption Library](https://github.com/homenc/HElib)
* [PALISADE Lattice Cryptography Library](https://palisade-crypto.org/)
* [Differential Privacy: A Survey of Results](https://link.springer.com/chapter/10.1007/978-3-540-79228-4_1)
* [Secure Aggregation for Federated Learning](https://eprint.iacr.org/2017/281.pdf)
* [Private Information Retrieval: Concepts and Constructions](https://link.springer.com/book/10.1007/978-3-030-16234-8)


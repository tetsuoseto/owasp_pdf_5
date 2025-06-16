# C6 Bảo mật chuỗi cung ứng cho Mô hình, Khung và Dữ liệu

## Mục tiêu Kiểm soát

Các cuộc tấn công chuỗi cung ứng AI khai thác các mô hình, khung làm việc hoặc bộ dữ liệu của bên thứ ba để chèn cửa hậu, thiên vị hoặc mã có thể khai thác. Những biện pháp kiểm soát này cung cấp khả năng truy xuất nguồn gốc từ đầu đến cuối, quản lý lỗ hổng và giám sát nhằm bảo vệ toàn bộ vòng đời mô hình.

---

## C6.1 Kiểm tra và Xuất xứ Mô hình Được Huấn luyện Trước

Đánh giá và xác thực nguồn gốc, giấy phép và hành vi ẩn của mô hình bên thứ ba trước khi bất kỳ việc tinh chỉnh hay triển khai nào.

|   #   | Description                                                                                                                                                               | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.1.1 | Xác minh rằng mọi bản sao mô hình bên thứ ba đều bao gồm một hồ sơ nguồn gốc được ký xác nhận, trong đó xác định kho lưu trữ nguồn và mã băm cam kết.                     |   1   | D/V  |
| 6.1.2 | Xác minh rằng các mô hình được quét để phát hiện các lớp độc hại hoặc kích hoạt Trojan bằng các công cụ tự động trước khi nhập.                                           |   1   | D/V  |
| 6.1.3 | Xác minh rằng việc tinh chỉnh học chuyển giao vượt qua đánh giá kẻ thù để phát hiện các hành vi ẩn.                                                                       |   2   |  D   |
| 6.1.4 | Xác nhận rằng giấy phép mô hình, thẻ kiểm soát xuất khẩu và tuyên bố nguồn gốc dữ liệu được ghi lại trong mục ML-BOM.                                                     |   2   |  V   |
| 6.1.5 | Xác minh rằng các mô hình rủi ro cao (trọng số được tải lên công khai, người tạo chưa được xác minh) vẫn bị cách ly cho đến khi được kiểm tra và phê duyệt bởi con người. |   3   | D/V  |

---

## C6.2 Quét Khung Công Tác & Thư Viện

Liên tục quét các khung và thư viện ML để tìm các CVE và mã độc nhằm giữ cho ngăn xếp runtime được bảo mật.

|   #   | Description                                                                                                                           | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.2.1 | Xác minh rằng các pipeline CI chạy các công cụ quét phụ thuộc trên các framework AI và các thư viện quan trọng.                       |   1   | D/V  |
| 6.2.2 | Xác minh rằng các lỗ hổng nghiêm trọng (CVSS ≥ 7.0) chặn việc thúc đẩy lên các ảnh sản xuất.                                          |   1   | D/V  |
| 6.2.3 | Xác minh rằng phân tích mã tĩnh được thực hiện trên các thư viện ML được fork hoặc vendor hóa.                                        |   2   |  D   |
| 6.2.4 | Xác nhận rằng các đề xuất nâng cấp khung làm việc bao gồm đánh giá tác động bảo mật tham chiếu đến các nguồn thông tin CVE công khai. |   2   |  V   |
| 6.2.5 | Xác minh rằng các cảm biến thời gian chạy cảnh báo khi có tải thư viện động không mong đợi mà lệch khỏi SBOM đã được ký.              |   3   |  V   |

---

## C6.3 Ghim và Xác minh Phụ thuộc

Ghim mọi phụ thuộc vào các bản tổng hợp không thay đổi và tái tạo các bản xây dựng để đảm bảo các sản phẩm là giống hệt nhau và không bị giả mạo.

|   #   | Description                                                                                                                      | Level | Role |
| :---: | -------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.3.1 | Xác minh rằng tất cả các trình quản lý gói đều thực thi việc cố định phiên bản thông qua các file khóa.                          |   1   | D/V  |
| 6.3.2 | Xác minh rằng các giá trị băm không thay đổi được sử dụng thay vì các thẻ có thể thay đổi trong các tham chiếu container.        |   1   | D/V  |
| 6.3.3 | Xác minh rằng các kiểm tra xây dựng có thể tái tạo so sánh các giá trị băm qua các lần chạy CI để đảm bảo đầu ra giống hệt nhau. |   2   |  D   |
| 6.3.4 | Xác minh rằng chứng thực xây dựng được lưu trữ trong 18 tháng để đảm bảo khả năng truy xuất kiểm toán.                           |   2   |  V   |
| 6.3.5 | Xác minh rằng các phụ thuộc đã hết hạn kích hoạt PR tự động để cập nhật hoặc tách phiên bản được cố định.                        |   3   |  D   |

---

## C6.4 Thực thi Nguồn Tin cậy

Chỉ cho phép tải xuống tác phẩm từ các nguồn được tổ chức phê duyệt và xác minh bằng mã hóa, đồng thời chặn mọi nguồn khác.

|   #   | Description                                                                                                                         | Level | Role |
| :---: | ----------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.4.1 | Xác minh rằng các trọng số mô hình, bộ dữ liệu và container chỉ được tải xuống từ các miền được phê duyệt hoặc các registry nội bộ. |   1   | D/V  |
| 6.4.2 | Xác minh rằng các chữ ký Sigstore/Cosign xác nhận danh tính nhà xuất bản trước khi các tác phẩm được lưu vào bộ nhớ đệm cục bộ.     |   1   | D/V  |
| 6.4.3 | Xác minh rằng các proxy egress chặn việc tải xuống artifact không xác thực để thực thi chính sách nguồn tin cậy.                    |   2   |  D   |
| 6.4.4 | Xác minh rằng danh sách cho phép của kho lưu trữ được xem xét hàng quý với bằng chứng về sự biện minh kinh doanh cho mỗi mục.       |   2   |  V   |
| 6.4.5 | Xác minh rằng các vi phạm chính sách kích hoạt việc cách ly các hiện vật và hoàn tác các lần chạy đường ống phụ thuộc.              |   3   |  V   |

---

## C6.5 Đánh giá Rủi ro Bộ dữ liệu Bên thứ ba

Đánh giá các bộ dữ liệu bên ngoài về khả năng bị đầu độc, thiên vị và tuân thủ pháp lý, đồng thời giám sát chúng trong suốt vòng đời của chúng.

|   #   | Description                                                                                                                                            | Level | Role |
| :---: | ------------------------------------------------------------------------------------------------------------------------------------------------------ | :---: | :--: |
| 6.5.1 | Xác minh rằng các bộ dữ liệu bên ngoài trải qua đánh giá rủi ro nhiễm độc (ví dụ: tạo dấu vân tay dữ liệu, phát hiện điểm ngoại lai).                  |   1   | D/V  |
| 6.5.2 | Xác nhận rằng các chỉ số thiên vị (cân bằng dân số, cơ hội công bằng) được tính toán trước khi phê duyệt bộ dữ liệu.                                   |   1   |  D   |
| 6.5.3 | Xác minh rằng nguồn gốc và điều khoản cấp phép cho các tập dữ liệu được ghi lại trong các mục ML-BOM.                                                  |   2   |  V   |
| 6.5.4 | Xác minh rằng việc giám sát định kỳ phát hiện sự trôi dạt hoặc hỏng hóc trong các bộ dữ liệu được lưu trữ.                                             |   2   |  V   |
| 6.5.5 | Xác minh rằng nội dung không được phép (bản quyền, thông tin cá nhân nhạy cảm) đã được loại bỏ thông qua quá trình làm sạch tự động trước khi đào tạo. |   3   |  D   |

---

## C6.6 Giám sát tấn công chuỗi cung ứng

Phát hiện các mối đe dọa chuỗi cung ứng từ sớm thông qua nguồn dữ liệu CVE, phân tích nhật ký kiểm toán và mô phỏng đội tấn công.

|   #   | Description                                                                                                                                                                  | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.6.1 | Xác minh rằng nhật ký kiểm toán CI/CD được truyền đến hệ thống SIEM để phát hiện các hành vi bất thường trong việc kéo gói hoặc các bước xây dựng bị thay đổi.               |   1   |  V   |
| 6.6.2 | Xác minh rằng các kịch bản ứng phó sự cố bao gồm các thủ tục khôi phục cho các mô hình hoặc thư viện bị xâm phạm.                                                            |   2   |  D   |
| 6.6.3 | Xác minh rằng việc làm giàu thông tin tình báo về mối đe dọa gắn thẻ các chỉ số cụ thể của ML (ví dụ: các chỉ số IoC về đầu độc mô hình) trong quá trình phân loại cảnh báo. |   3   |  V   |

---

## C6.7 ML‑BOM cho các Tác phẩm Mô hình

Tạo và ký các SBOM chi tiết dành riêng cho ML (ML-BOM) để người tiêu dùng hạ nguồn có thể xác minh tính toàn vẹn của các thành phần khi triển khai.

|   #   | Description                                                                                                                                    | Level | Role |
| :---: | ---------------------------------------------------------------------------------------------------------------------------------------------- | :---: | :--: |
| 6.7.1 | Xác minh rằng mọi artefact mô hình đều công bố một ML-BOM liệt kê các bộ dữ liệu, trọng số, siêu tham số và giấy phép.                         |   1   | D/V  |
| 6.7.2 | Xác minh rằng việc tạo ML-BOM và ký Cosign được tự động hóa trong CI và là yêu cầu bắt buộc để hợp nhất.                                       |   1   | D/V  |
| 6.7.3 | Xác minh rằng các kiểm tra đầy đủ ML-BOM sẽ làm cho quá trình xây dựng thất bại nếu thiếu bất kỳ siêu dữ liệu thành phần nào (băm, giấy phép). |   2   |  D   |
| 6.7.4 | Xác minh rằng người tiêu dùng hạ nguồn có thể truy vấn ML-BOMs qua API để xác thực các mô hình đã nhập khi triển khai.                         |   2   |  V   |
| 6.7.5 | Xác minh rằng ML-BOM được kiểm soát phiên bản và so sánh sự khác biệt để phát hiện các sửa đổi trái phép.                                      |   3   |  V   |

---

## Tài liệu tham khảo

* [ML Supply Chain Compromise – MITRE ATLAS](https://misp-galaxy.org/mitre-atlas-attack-pattern/)
* [Supply‑chain Levels for Software Artifacts (SLSA)](https://slsa.dev/)
* [CycloneDX – Machine Learning Bill of Materials](https://cyclonedx.org/capabilities/mlbom/)
* [What is Data Poisoning? – SentinelOne](https://www.sentinelone.com/cybersecurity-101/cybersecurity/data-poisoning/)
* [Transfer Learning Attack – OWASP ML Security Top 10](https://owasp.org/www-project-machine-learning-security-top-10/docs/ML07_2023-Transfer_Learning_Attack)
* [AI Data Security Best Practices – CISA](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-142a)
* [Secure CI/CD Supply Chain – Sumo Logic](https://www.sumologic.com/blog/secure-azure-devops-github-supply-chain-attacks)
* [AI & Transparency: Protect ML Models – ReversingLabs](https://www.reversinglabs.com/blog/ai-and-transparency-how-ml-model-creators-can-protect-against-supply-chain-attacks)
* [SBOM Overview – CISA](https://www.cisa.gov/sbom)
* [Training Data Poisoning Guide – Lakera.ai](https://www.lakera.ai/blog/training-data-poisoning)
* [Dependency Pinning for Reproducible Python – Medium](https://medium.com/data-science-collective/guarantee-a-locked-reproducible-environment-with-every-python-run-c0e2bf19fb53)


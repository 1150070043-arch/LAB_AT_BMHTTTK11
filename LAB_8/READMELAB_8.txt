Tên :Nguyễn Song Anh Thuần
Lớp : 11_ĐH_HTTT
LAB_8
README – Tiến trình thực hiện LAB Local DNS Attack trên pfSense
1. Mục tiêu bài lab
Thực hành mô hình DNS nội bộ trong mạng lab cô lập để:
- Cấu hình pfSense làm thiết bị định tuyến và lọc lưu lượng giữa các mạng.
- Cấu hình DNS-SERVER Ubuntu Server sử dụng BIND9.
- Kiểm tra phân giải tên miền bằng dig.
- Quan sát lưu lượng DNS bằng Wireshark hoặc tcpdump.
- Tìm hiểu tác động của chỉnh sửa /etc/hosts, giả mạo phản hồi DNS và đầu độc bộ nhớ đệm DNS trong phạm vi lab.
- Khôi phục cấu hình sau thực nghiệm và đề xuất biện pháp phòng vệ.
Lưu ý: Chỉ thực hiện các thử nghiệm trong mạng lab cô lập 10.9.0.0/24 và tên miền thử nghiệm .test. Không thực hiện trên mạng thật hoặc hệ thống không được phép kiểm thử.

2. Mô hình mạng dự kiến
Máy / thành phần	Địa chỉ IP	Vai trò	Trạng thái theo tiến trình hiện có
pfSense DNSLAB	10.9.0.1/24	Gateway và firewall cho mạng DNSLAB	Đã kiểm tra/cấu hình các rule DNSLAB theo xác nhận của người thực hiện
DNS-SERVER – Ubuntu Server	10.9.0.10	Máy chủ DNS BIND9	Chưa xác nhận đã hoàn tất cấu hình BIND9
VICTIM – Ubuntu	10.9.0.100	Máy khách kiểm thử phân giải DNS	Chưa xác nhận đã kiểm tra
ATTACKER – Kali Linux	10.9.0.200	Máy kiểm thử trong lab	Chưa xác nhận đã thực hiện thử nghiệm
APP-TEST / AUTH-DNS	172.16.6.20	Máy dịch vụ DNS thử nghiệm	Chưa xác nhận đã kiểm tra kết nối
DMZ-WEB	172.16.6.10	Web thử nghiệm	Chưa xác nhận đã kiểm tra truy cập


Các địa chỉ trên là địa chỉ theo tài liệu lab. Cần đối chiếu với cấu hình thực tế trên VMware trước khi chạy lệnh.
3. Những việc đã thực hiện được
3.1. Môi trường thực hành
- Đã xác định sử dụng VMware Workstation để triển khai máy ảo.
- Đã tiến hành cấu hình và kiểm tra các quy tắc firewall trên giao diện DNSLAB của pfSense.
3.2. Firewall pfSense
Theo xác nhận trước đó, phần kiểm tra Bước 7 – Firewall DNSLAB đã hoàn tất. Các quy tắc mục tiêu của lab gồm:
1. Cho phép DNS-SERVER 10.9.0.10 truy vấn máy DNS thử nghiệm 172.16.6.20 qua UDP/TCP cổng 53.
2. Cho phép mạng DNSLAB 10.9.0.0/24 truy cập DMZ-WEB 172.16.6.10 qua TCP cổng 80.
3. Chặn và ghi log truy cập từ DNSLAB đến LAN 10.6.0.0/24.
4. Chặn và ghi log truy cập từ DNSLAB đến MGMT 192.168.56.0/24.
5. Chặn và ghi log các lưu lượng còn lại từ DNSLAB theo phạm vi rule cuối.
Lưu ý: README ghi nhận việc hoàn thành bước firewall dựa trên xác nhận của người thực hiện; chưa có bằng chứng trong tiến trình hiện tại để xác nhận từng rule đã được kiểm thử bằng packet capture hoặc log.
4. Những việc chưa thực hiện hoặc chưa xác nhận hoàn tất
Các mục dưới đây được đánh dấu chưa hoàn tất vì chưa có xác nhận kết quả thực tế trong tiến trình hiện tại.
- [ ] Cài đặt và kiểm tra BIND9 trên DNS-SERVER Ubuntu Server.
- [ ] Cấu hình DNS resolver/cache và các zone thuận/ngược theo tài liệu lab.
- [ ] Kiểm tra cú pháp cấu hình BIND9 và trạng thái dịch vụ.
- [ ] Kiểm tra phân giải tên miền cơ sở bằng dig, gồm tên www.external.lab9.test trả về 172.16.6.10.
- [ ] Kiểm tra kết nối từ VICTIM đến DNS-SERVER.
- [ ] Bắt và phân tích gói DNS bằng Wireshark hoặc tcpdump.
- [ ] Thực hiện tình huống chỉnh sửa /etc/hosts trên VICTIM và so sánh với truy vấn DNS trực tiếp.
- [ ] Thực hiện các tình huống giả mạo DNS/đầu độc cache chỉ trong môi trường lab được cô lập, theo hướng dẫn và phạm vi được cho phép.
- [ ] Khôi phục cache/cấu hình DNS sau kiểm thử.
- [ ] Hoàn thiện ảnh chụp màn hình, kết quả kiểm thử và phần nhận xét của báo cáo.
Tên : Nguyễn Song Anh Thuần
Lớp : 11_ĐH_TMĐT
MSSV : 1150070043
README – LAB 10: REMOTE DNS CACHE POISONING
1. Mục tiêu
Thực hành mô phỏng tấn công đầu độc bộ nhớ đệm DNS trong môi trường VMware Workstation cô lập và tìm hiểu các biện pháp phòng chống.
2. Môi trường thực hiện
- VMware Workstation.
- pfSense.
- Kali Linux.
- DNS-SERVER.
- VICTIM.
- Các máy Ubuntu phục vụ mô hình bổ trợ.
3. Nội dung đã thực hiện
- Kiểm tra các máy ảo hiện có.
- Kiểm tra cấu hình card mạng pfSense.
- Cấu hình mạng ATTACKNET.
- Thiết lập Kali Linux với IP 10.10.0.200.
- Thiết lập pfSense ATTACKNET với IP 10.10.0.1.
- Tách Kali khỏi mạng DNSLAB.
4. Nội dung chưa hoàn thành
- Cấu hình DNS-SERVER và VICTIM.
- Hoàn thiện mạng DMZ.
- Cấu hình dịch vụ DNS và AUTH-DNS.
- Thực hiện mô phỏng DNS Cache Poisoning.
- Kiểm tra kết quả bằng Wireshark.
- Khôi phục và tăng cường bảo mật DNS.
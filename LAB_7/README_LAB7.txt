Tên :Nguyễn Song Anh Thuần
Lớp :11_ĐH_TMĐT
MSSV:1150070043
em0       192.168.153.137/24       WAN
  em1       192.168.56.254/24        OPT1 / MGMT
  em2       10.6.0.1/24              LAN
  em3       172.16.6.1/24            OPT2 / DMZ

Trong VMware, đã xác định được các LAN Segment: - lab6_Lan: mạng LAN
dự kiến dùng cho Client-A và WEB-PROXY. - lab6_dmz: mạng DMZ.
2. Những việc đã làm được
- Đã mở và kiểm tra console pfSense.
- Đã chạy ifconfig trên pfSense và xác định được các giao diện cùng
  địa chỉ IP.
- Đã kiểm tra cài đặt Network Adapter của máy pfSense trong VMware.
- Đã xác định LAN Segment lab6_Lan và DMZ Segment lab6_dmz.
- Đã kiểm tra thông tin mạng của Ubuntu thuanmaya01.
- Đã xác định card mạng Ubuntu là ens33.
- Đã xác định Ubuntu đang dùng NetworkManager để quản lý mạng.
- Đã xác định tên kết nối NetworkManager chính xác là
  Wired connection 1.
- Đã kiểm tra được IP cũ của Ubuntu là 172.16.16.10/24, gateway cũ
  là 172.16.16.16.
- Đã thử ping từ Ubuntu đến pfSense LAN 10.6.0.1, nhưng kết nối chưa
  thành công.
3. Những việc chưa làm được hoặc chưa xác nhận
- Chưa xác nhận chắc chắn Ubuntu thuanmaya01 đã kết nối đúng vào
  lab6_Lan.
- Chưa cấu hình thành công IP tĩnh cho WEB-PROXY. IP 10.6.0.30/24
  mới là địa chỉ mục tiêu, chưa được xác nhận đã áp dụng.
Tình huống còn lỗi chưa hoàn thành4
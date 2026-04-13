Task 1: Khởi tạo bảng DynamoDB
DynamoDB không lưu dữ liệu vào các bảng có hàng và cột cố định. Thay vào đó, nó sử dụng Primary Key để quản lý dữ liệu.

Tìm dịch vụ DynamoDB trên thanh tìm kiếm.

Nhấn Create table và cấu hình như sau:

Table name: Music

Partition key: Artist (Chọn kiểu String). Đây là chìa khóa chính để phân tán dữ liệu.

Sort key: Song (Chọn kiểu String). Giúp bạn sắp xếp các bài hát của cùng một nghệ sĩ.

Giữ các thiết lập khác mặc định và nhấn Create table.
![alt text](asset6/image.png) 


Task 2: Thêm dữ liệu (Items)
Một điểm "ăn tiền" của NoSQL là mỗi dòng dữ liệu (Item) có thể có các thuộc tính (Attributes) hoàn toàn khác nhau.

Vào mục Explore items ở menu bên trái > Chọn bảng Music.
![alt text](asset6/image1.png) 


Nhấn Create item và bắt đầu thêm các "siêu sao" vào thư viện:
![alt text](asset6/image2.png) 


Item,Artist (Partition Key),Song (Sort Key),Các thuộc tính thêm vào
1,Pink Floyd,Money,"Album: The Dark Side of the Moon, Year: 1973"
2,John Lennon,Imagine,"Album: Imagine, Year: 1971, Genre: Soft rock"
3,Psy,Gangnam Style,"Album: Psy 6, Year: 2011, LengthSeconds: 219"
![alt text](asset6/image3.png) 


Task 3: Chỉnh sửa dữ liệu
Việc cập nhật trong DynamoDB rất đơn giản:

Chọn bài hát của Psy trong danh sách.

Vào Actions > Edit item.
![alt text](asset6/image4.png) 

Đổi năm từ 2011 thành 2012 (năm thực tế cơn sốt này bùng nổ).

Nhấn Save.

Task 4: Truy vấn dữ liệu (Query vs Scan)
Đây là phần quan trọng nhất để bạn hiểu cách lấy dữ liệu hiệu quả.

1. Query (Truy vấn - Nhanh & Rẻ)
Tìm chính xác dựa trên Key.

Chọn Query.

Nhập Partition key Artist và Sort key Song .

Kết quả: Trả về ngay lập tức vì hệ thống biết chính xác dữ liệu nằm ở đâu.
![alt text](asset6/image5.png) 


2. Scan (Quét - Chậm & Tốn kém)
Hệ thống phải đọc qua tất cả các dòng trong bảng để tìm kết quả.

Chọn Scan.

Thêm Filter: Year (Number) Equal to 1971.

Kết quả: Tìm thấy John Lennon, nhưng nếu bảng có 1 tỷ dòng, lệnh này sẽ rất chậm.

Task 5: Dọn dẹp tài nguyên
Đừng để bảng chạy lãng phí tài nguyên nếu bạn đã xong việc.

Vào mục Tables ở bên trái.

Chọn bảng Music và nhấn Delete.

Gõ confirm vào ô xác nhận để xóa sạch bảng và dữ liệu bên trong.
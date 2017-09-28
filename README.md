# cPOS-4-_well
Big Project (POS System for *WELL restaurant)
**Main Feature:**
Phần mềm quản lý nhà hàng (cung cấp các dịch vụ ăn uống, kho trữ, thống kê...)
  - Phục vụ đặt hàng/gọi món, nhập đơn hàng kho, Cho phép nhên viên đăng nhập và tự động chấm công khi đăng xuất
  - Quản lý nguyên vật liệu trong kho (giám sát/thông báo các trạng thái nguyên vật liệu: còn, hết)
  - Phần mềm được chia cấp: dành cho nhân viên và dành cho quản lý
    + Employee: thực hiện order, điều chỉnh tài khoản của bản thân, nhập hoá đơn nguyên liệu vào kho, thực hiện order cho khách hàng,...
    + Admin: quản lý thông tin nhân viên, lương, lịch làm việc, nguyên liệu trong kho, menu sản phẩm (món ăn,...), tài khoản admin
  - Hiển thị Thống kê Thu chi theo tuần/tháng/năm

Phần mềm được viết trên nền tảng C# .NET với giao diện đồ hoạ WPF, Material Design. Kết hợp một số thư viện mở MaterialdesigninXAML, dragablz, mahapp.metro, ADO.NET, EntityFramework...
Đây là phiên bản chính thức dựa trên một số nền tảng của ứng dụng POS trước

**Product Owner Story:**
  - Hiển thị sơ đồ bàn cho phép nhân viên thao tác chọn và thực hiện order. Sơ đồ có thể sẽ bị thay đổi trong tương lai bởi quản lý
  - Thao tác in hoá đơn cho một order:  

**Note:**
 - File "nn" là file rỗng, bù nhìn, giúp giữ cho folder tồn tại khi mà folder không chưa file nào khác
 - Các thành viên tham gia phát triển hãy xem kĩ phần code style requirement
 - Phần precession trong readme.md dùng để báo cáo tiến độ phát triển, do các thành phiên được phân chia để code và cập nhật các trạng thái mới nhất của project (có thể báo các phần đã xong, chưa hoàn thành, gặp khó khăn, yêu cầu bàn luận giúp đỡ, lỗi, vướng mắt,.....). Các phần phân công được chia ra rõ ràng vì vậy khi cập nhật tiến trình cho phần nào thì chỉ viết nội dung liên quan đến phần đó, nếu ngoài lề sẽ bị xoá


# Project's procession:
  - **Database and WebService**:


  - **FrLogin**:
    + chưa xong : đăng nhập cho nhân viên và quản lý
    + chưa xong : cập nhật thêm chức năng thay đổi cấu hình đăng nhập database, sau khi chỉnh sửa và đăng nhập thành công, chương trình tự động lưu dữ liệu của database đó (lần sau không cần điều chỉnh nữa). Thông tin database sẽ được lưu vào databaseinfo.txt
    + chưa xong : cho phép người dùng mở cả Window admin và Window employee và Window warehouse song song, nhưng mỗi frame chỉ được mở một lần 
    + chưa xong : mã hoá mật khẩu người dùng

  - **EmployeeWorkspaceWindow**:
    + chưa xong : đăng nhập/xuất của nhân viên. Tự động chấm công và phát sinh WorkingLog trong ngày, bảng lương của tháng hiện tại vào trong database
    + chưa xong : các khung xuất menu (thêm ảnh cho món ăn nếu cần)
    + chưa xong : của sổ hiển thị sơ đồ chỗ ngồi (dựa trên map của nhà hàng)
    + chưa xong : cửa sổ nhập bill order, sau khi khách hàng tính tiền sẽ tự động sinh dữ liệu Order và OrderDetails trong database
    + chưa xong : xây dựng của sổ Setting cho các tuỳ chỉnh trong EmployeeWorkspaceWindow, các tuỳ chỉnh lưu vào settinginfo.txt
    + chưa xong : xây dựng chức năng cho phép nhân viên chỉnh sủa tài khoản cá nhân
    + chưa xong : In bill thông qua printer. Tính năng tuỳ chỉnh hiển thị văn bản in trước khi in
    + chưa xong : In thêm note của từng món ăn trong bill (kitchen print)
    + chưa xong : In report (theo dạng tài liệu pdf hoặc dạng hoá đơn liệt kê) sau một ngày làm việc
    + chưa xong : thêm chức năng lưu nhật kí phòng trường hợp chương trình bị đóng đột ngột (Nhưng lưu thông tin nhân viên thì chưa khả thi)
    + chưa xong : swap/merge table
    + chưa xong : xuất bill dưới dạng pdf
    + chưa xong : cho phép chia bill ra để thanh toán theo từng đợt
    
(*) dự kiến :  Bổ sung thông tin khách hàng, thêm chức năng xuất thông tin và hình ảnh nhận diện khách hàng quen thuộc, khi xuất danh sách khách hàng cho nhân viên xem có thể sort theo số lần khách hàng đã đến quán, thêm chức năng gửi nhận tin nhắn qua mạng internet


  - **WareHouseWindow**:
    + chưa xong : xây dựng cửa sổ theo dõi lượng nguyên liệu sử dụng và lương nguyên liệu đưa vào kho
    + chưa xong : chức năng kiểm tra và thông báo khi lượng nguyên liệu gần hết
    + chưa xong : xây dựng cửa sổ nhập đơn hàng, sau khi nhân viên nhập đơn hàng sẽ tự động sinh dữ liệu ReceitpNote và ReceiptNoteDetails trong database


  - **AdminWorkspaceWindow**:
  	+ chưa xong : Employee information form (giao diện/xem/xoá**/sửa thông tin/tìm kiếm(theo tên, ?))
    + chưa xong : Salary N`ote information form (giao diện/xem/xoá**/sửa thông tin)
  	+ chưa xong : Customer information form (giao diện/xem/xoá**/sửa thông tin/tìm kiếm(theo tên, ?))
  	+ chưa xong : Food information form (giao diện/xem/xoá**/sửa thông tin/tìm kiếm(theo tên, ?))
  	+ chưa xong : Ingredient information form (giao diện/xem/xoá**/sửa thông tin/tìm kiếm(theo tên, ?))
  	+ chưa xong : Order information form (giao diện/xem/tìm kiếm(theo ngày, ?))
    + chưa xong : ReceiptNote information form (giao diện/xem/tìm kiếm(theo ngày, ?))
  	+ chưa xong : Admin profile information form (giao diện/xem/sửa thông tin) _ không có quyền xóa bất kì admin nào
  	+ chưa xong : xuất report cho dữ liệu order/order details, empschedule/salarynote
    + chưa xong : xuất report cho dữ liệu receiptnote/receiptnote details
	  + chưa xong : hiển thị data chart cho order/order details, empschedule/salarynote, receipnote/receiptnote details
    
(*) dự kiến : Chức năng cho phép admin thêm lịch làm việc cho nhân viên hằng tuần, và nhân viên chỉ có thể login trong khung giờ mà admin đã sắp xếp (nếu login trễ hơn tức là đã đi làm trễ, logout sớm hơn giờ đã định => thông báo cho admin, trừ lương). Chức năng kiểm toán thu chi theo ngày/tháng/năm. Chức năng đồ hoạ vẽ biểu đồ thu nhập (bằng JFreeChart, datascient library). 

# Quản lý bến xe khách

Đây là project về bài tập lớn của môn học Hệ cơ sở dữ liệu (Database) của nhóm chúng mình. Nhóm chúng mình gồm có:

- Trần Bảo Phúc - 2114452
- Nguyễn Quốc Thắng - 2114837
- Dương Phúc Thắng - 2112327
- Trần Tiến Đạt - 2113162
- Dương Trọng Khôi - 2113786

## Mô tả chung
Đây là hệ thống cơ sở dữ liệu của bến xe, về cơ bản sẽ bao gồm:

***1. Thực thể***


**Thực thể mạnh**: Nhà xe, xe, chuyến đi, hành khách, phòng ban, nhân viên bến xe, nhân viên nhà xe (tài xế, phụ xe), hoá đơn, vé, tài khoản, huyện, đường.


**Thực thể yếu**: chặng đường (phụ thuộc vào tuyến đƯờng).

**Quan hệ Specialization**: Lớp cha nhân viên nhà xe chứa 2 lớp con là tài xế và phụ xe.

***2. Thuộc tính***


**Nhà xe**: 

- *Khóa*: Mã số nhà xe.
- *Thuộc* tính đơn: Ngày đăng kí hợp đồng với bến xe, ngày kết thúc hợp đồng với bến xe.
- *Thuộc tính đa trị*: Số điện thoại

**Phòng ban**:

- Khóa: Mã số phòng ban.
- Thuộc tính đơn: Tên phòng ban.
- Thuộc tính dẫn xuất: Số lượng nhân viên trong phòng ban (tính bằng số lượng nhân viên bến xe quản lý hoặc làm việc cho phòng ban)

**Nhân viên bến xe**:

- Khóa: Mã số nhân viên, CCCD.
- Thuộc tính đơn: ngày sinh, giới tính, loại nhân viên.
- Thuộc tính tổ hợp: Tên nhân viên (gồm họ và tên đệm, tên)
- Thuộc tính đa trị: Email, số điện thoại.
- Thuộc tính phức hợp: Địa chỉ (gồm số nhà, tên đường, quận/huyện, tỉnh/thành phố).


**Tài khoản nhân viên bến xe**:
- Khóa: Mã số tài khoản.
- Thuộc tính đơn: Trạng thái, tên đăng nhập, mật khẩu
- Thuộc tính dẫn xuất: Loại tài khoản (suy ra từ loại nhân viên bến xe sở hữu tài khoản)


**Nhân viên nhà xe**:
- Khóa: Mã số nhân viên, CCCD.
- Thuộc tính đơn: Ngày sinh, giới tính, loại nhân viên (chỉ gồm 2 giá trị là tài xế hoặc phụ xe).
- Thuộc tính tổ hợp: Tên nhân viên (gồm họ và tên đệm, tên)
- Thuộc tính đa trị: Email, số điện thoại.
- Thuộc tính phức hợp: Địa chỉ (gồm số nhà, tên đường, quận/huyện, tỉnh/thành phố).

**Tài xế**:
- Khóa: Mã số bằng lái.
- Thuộc tính đơn: Loại bằng lái.

**Xe**:
- Khóa: Mã số xe, biển số xe
- Thuộc tính đơn: Loại xe, số chỗ ngồi, trạng thái.
Chuyến đi:
- Khóa: Mã chuyến đi.
- Thuộc tính đơn: Giờ khởi hành, số lượng ghế bán tối đa, số lượng ghế đã bán.
- Thuộc tính dẫn xuất: Giờ đến nơi (suy ra từ giờ khởi hành của chuyến đi, khoảng cách của tuyến đường mà nó đi).


**Tuyến đường**:
- Khóa: Mã tuyến đường đi.
- Thuộc tính dẫn xuất: Khoảng cách (suy ra từ điểm bắt đầu và kết thúc của tuyến đường)


**Chặng đường**:
- Khóa: Mã chặng đường.
- Thuộc tính đơn: Giá cả.
- Thuộc tính dẫn xuất: Khoảng cách (tính bằng điểm bắt đầu của chuyến đi chứa nó và điểm dừng lại lại của chặng đó)


**Tỉnh**:
- Khóa: Mã số tỉnh.
- Thuộc tính đơn: Tên tỉnh.

**Huyện**:
- Khóa: Mã số huyện
- Thuộc tính đơn: Tên huyện.

**Hành khách**:
- Khóa: CCCD
- Thuộc tính đơn: Tên, ngày sinh, giới tính.
- Thuộc tính đa trị: Email, số điện thoại.
- Thuộc tính phức hợp: Địa chỉ (gồm số nhà, tên đường, quận/huyện, tỉnh/thành phố).

**Vé**:
- Khóa: Mã số vé.
- Thuộc tính đơn: Vị trí ghế

**Hóa đơn**:
- Khóa: Mã số hóa đơn, mã số thuế.
- Thuộc tính dẫn xuất: Số lượng vé mua (suy ra từ số vé mà hóa đơn chứa), tổng số tiền (suy từ tổng tiền của mỗi vé trong hóa đơn).

## Sơ đồ
Mối liên kết giữa các thực thể được thể hiện qua sơ đồ EERD sau đây: 
[Diagram](https://drive.google.com/file/d/14LIIG-D62tGI7PogU6BuOzHknUMHhkVH/view?usp=sharing)

Sơ đồ sau khi mapping:
[Mapping](https://drive.google.com/file/d/1hsAzVXmFVqMvmc-SPUir1jb84E4Qs8y1/view?usp=sharing)

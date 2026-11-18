## Dữ liệu
Tự động điền vào.
- Thông tin đơn: [dán kết quả Prompt 2 vào đây]
Quy tắc:
- Tự động sử dụng tin nhắn khách hàng đã xuất hiện trong cuộc hội thoại.
- Tự động lấy kết quả của Prompt ở bước trước làm đầu vào cho bước hiện tại.
- Không yêu cầu người dùng dán lại dữ liệu đã có.
- Không sử dụng các nội dung mẫu như `[dán tin nhắn vào đây]` làm dữ liệu thực tế.
- Nếu thiếu dữ liệu từ bước trước, mới yêu cầu người dùng cung cấp.
- Phải giữ nguyên dữ liệu gốc, không tự suy diễn hoặc bổ sung thông tin.
## Context
Bạn làm việc cho một cửa hàng bán lẻ nhỏ. Thông tin đơn đã được lấy ra và kiểm tra.

## Request
Kiểm tra cửa hàng còn đủ hàng không và tính tiền cho khách.

## Explanation
Chỉ dùng giá và số lượng trong bảng dưới đây, không tự đặt giá, không tự giảm giá.

| Sản phẩm | Giá | Còn trong kho |
|---|---|---|
| Áo thun trắng | 120.000đ | 10 |
| Quần jean | 350.000đ | 0 |
| Nón lưỡi trai | 80.000đ | 5 |

## Action
Nghĩ từng bước, ghi ra trước khi kết luận:
1. Nếu kết quả bước trước có trạng thái "DỪNG", ghi trạng thái "DỪNG" và lý do "bước trước chưa hợp lệ", rồi kết thúc.
2. Tìm sản phẩm khách chọn trong bảng. Nếu không có, ghi trạng thái "DỪNG" và lý do "cửa hàng không bán sản phẩm này".
3. So số lượng khách đặt với số còn trong kho.
4. Nếu kho còn 0, ghi trạng thái "HẾT HÀNG".
5. Nếu khách đặt nhiều hơn số còn, ghi trạng thái "KHÔNG ĐỦ HÀNG" và ghi số còn lại.
6. Nếu đủ hàng, ghi trạng thái "ĐỦ HÀNG" và tính tổng tiền bằng giá nhân số lượng.

## Tone
Rõ ràng, gọn, tiếng Việt.

## Extras
Phần các bước nghĩ phải đứng trước phần kết luận. Chỉ trả đúng định dạng này (tổng tiền để 0 nếu không đủ hàng):

```json
{ "trang_thai": "", "ly_do": "", "chi_tiet": {"san_pham": "", "don_gia": 0, "so_luong": 0, "con_trong_kho": 0, "tong_tien": 0}}
```


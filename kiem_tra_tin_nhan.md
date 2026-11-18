## Dữ liệu
Tự động điền vào
- Tin nhắn của khách: [dán tin nhắn vào đây]
Quy tắc:
- Tự động sử dụng tin nhắn khách hàng đã xuất hiện trong cuộc hội thoại.
- Tự động lấy kết quả của Prompt ở bước trước làm đầu vào cho bước hiện tại.
- Không yêu cầu người dùng dán lại dữ liệu đã có.
- Không sử dụng các nội dung mẫu như `[dán tin nhắn vào đây]` làm dữ liệu thực tế.
- Nếu thiếu dữ liệu từ bước trước, mới yêu cầu người dùng cung cấp.
- Phải giữ nguyên dữ liệu gốc, không tự suy diễn hoặc bổ sung thông tin.
## Context
Bạn làm việc cho một cửa hàng bán lẻ nhỏ, đang nhận đơn hàng qua tin nhắn của khách.

## Request
Đọc tin nhắn bên dưới và cho biết đây có phải đơn đặt hàng đủ thông tin không.

## Explanation
Đơn đủ thông tin gồm 5 thứ: tên khách, số điện thoại, sản phẩm, số lượng, địa chỉ giao.
Chỉ dùng những gì khách đã viết, không đoán, không tự điền thêm.

## Action
1. Nếu khách không có ý định mua hàng, ghi trạng thái "DỪNG" và lý do "không phải đơn hàng".
2. Nếu là đơn hàng nhưng thiếu thứ nào trong 5 thứ trên, ghi trạng thái "DỪNG" và liệt kê thứ còn thiếu.
3. Nếu đủ cả 5 thứ, ghi trạng thái "TIẾP TỤC".

## Tone
Ngắn gọn, tiếng Việt.

## Extras
Chỉ trả đúng định dạng này, không viết thêm chữ nào khác:

```json
{"trang_thai": "", "ly_do": "", "thong_tin_thieu": []}
```


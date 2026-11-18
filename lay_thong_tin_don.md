
## Dữ liệu
Tự động điền vào.
- Tin nhắn của khách: [dán tin nhắn vào đây]
- Kết quả bước kiểm tra: [dán kết quả Prompt 1 vào đây]
Quy tắc:
- Tự động sử dụng tin nhắn khách hàng đã xuất hiện trong cuộc hội thoại.
- Tự động lấy kết quả của Prompt ở bước trước làm đầu vào cho bước hiện tại.
- Không yêu cầu người dùng dán lại dữ liệu đã có.
- Không sử dụng các nội dung mẫu như `[dán tin nhắn vào đây]` làm dữ liệu thực tế.
- Nếu thiếu dữ liệu từ bước trước, mới yêu cầu người dùng cung cấp.
- Phải giữ nguyên dữ liệu gốc, không tự suy diễn hoặc bổ sung thông tin.
## Context
Bạn làm việc cho một cửa hàng bán lẻ nhỏ. Tin nhắn của khách đã qua bước kiểm tra.

## Request
Lấy ra thông tin đơn hàng từ tin nhắn và kiểm tra thông tin có hợp lệ không.

## Explanation
- Số điện thoại hợp lệ phải đủ 10 chữ số và bắt đầu bằng số 0.
- Số lượng hợp lệ phải là số nguyên lớn hơn 0.
- Giữ nguyên như khách viết, không tự sửa, không tự điền.

## Action
Nghĩ từng bước, ghi ra trước khi kết luận:
1. Nếu kết quả bước kiểm tra có trạng thái "DỪNG", ghi trạng thái "DỪNG" và lý do "bước trước chưa hợp lệ", rồi kết thúc.
2. Tìm tên khách.
3. Tìm số điện thoại và đếm số chữ số.
4. Tìm sản phẩm và số lượng.
5. Tìm địa chỉ giao.
6. Nếu số điện thoại hoặc số lượng không hợp lệ, ghi trạng thái "DỪNG" và nói rõ cái nào sai, vì sao.
7. Nếu tất cả hợp lệ, ghi trạng thái "TIẾP TỤC".

## Tone
Rõ ràng, gọn, tiếng Việt.

## Extras
Phần các bước nghĩ phải đứng trước phần kết luận. Chỉ trả đúng định dạng này:

```json
{ "trang_thai": "", "ly_do": "", "don_hang": {"ten": "", "sdt": "", "san_pham": "", "so_luong": 0, "dia_chi": ""}}
```

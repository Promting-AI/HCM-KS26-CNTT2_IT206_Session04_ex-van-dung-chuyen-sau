# Yêu cầu đầu ra: 
## Bước 1: 
- Các nghiệp vụ mà AI phải làm là:
  1. Kiểm tra tin nhắn có phải đơn hàng và đủ thông tin không	
  2. Trích xuất: tên khách, SĐT, sản phẩm, số lượng, địa chỉ	(CoT)
  3. Đối chiếu danh mục và tồn kho, tính tổng tiền (CoT) 
  4. Soạn tin phản hồi khách theo kết quả
- Input của cái 1 là tin nhắn của khách và output của nó đi ra sẽ là input của thằng số 2. Tương tự như vậy dữ liệu sẽ được đi là 1 -> 2 -> 3 -> 4
- Output của từng thằng sẽ là kết quả của các trường theo định dạng JSON.
## Bước 2: Promt
  [1. Kiểm tra tin nhắn có phải đơn hàng và đủ thông tin không](kiem_tra_tin_nhan.md)
  [2. Trích xuất: tên khách, SĐT, sản phẩm, số lượng, địa chỉ (CoT)](lay_thong_tin_don.md)
  [3. Đối chiếu danh mục và tồn kho, tính tổng tiền (CoT)](kiem_kho_va_tinh_tien.md)
  [4. Soạn tin phản hồi khách theo kết quả](soan_tin_tra_loi_khach.md)
## Link thử nghiệm
https://chatgpt.com/share/6afd041d-237c-83ec-9c5d-88d3d9cb3c13
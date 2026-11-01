# Xưởng Art

Bộ công cụ chuẩn bị art chạy hoàn toàn trong trình duyệt. Ảnh được xử lý ngay trên máy người dùng và không tải lên máy chủ nào.

## Tính năng

- **Tách nền**, có 3 cách:
  - AI tự động (U²-Net, có bản Nhanh và bản Chi tiết).
  - Theo màu nền, có khử viền màu.
  - Đũa thần: bấm vào vùng nào thì xóa vùng đó.
- **Cọ tẩy / khôi phục:** sửa những chỗ tách nền bị lẹm.
- **Tách element:** tự tìm từng vật thể rời nhau. Từ đó có thể lưu ZIP, mở thành tab, hoặc ghép thành sprite sheet.
- **Cắt lưới:** cắt sprite sheet hoặc tileset theo hàng/cột hay theo cỡ ô.
- **Kích thước:** đổi cỡ (mượt, hoặc giữ nét cho pixel art), khung vuông, lũy thừa 2, cắt sát phần trong suốt.
- **Cắt & xoay**, **chỉnh màu**, **viền sticker & bóng đổ**, **bảng màu & pixel art**.
- **Xuất file:** PNG, JPG hoặc WebP theo tỉ lệ tùy chọn, bộ icon nhiều cỡ, hoặc lưu mọi tab thành một file ZIP.

## Đưa lên GitHub Pages

### Cách 1: làm trên trang github.com, không cần cài gì

1. Vào github.com, bấm **New repository**. Đặt tên (ví dụ `xuong-art`) và chọn **Public**.
2. Trong repo vừa tạo, bấm **Add file → Upload files**.
3. Kéo **toàn bộ nội dung** của thư mục này vào, gồm `index.html`, `favicon.svg` và hai thư mục `vendor` và `models`.
   - Mỗi tệp đều dưới 25 MB nên tải qua trình duyệt được.
   - Tệp `.nojekyll` bị ẩn trên máy cũng không sao nếu không kéo theo.
4. Bấm **Commit changes**.
5. Vào **Settings → Pages**. Ở mục *Build and deployment*, chọn:
   - Source: **Deploy from a branch**
   - Branch: **main**, thư mục **/ (root)**

   Rồi bấm **Save**.
6. Đợi 1–2 phút. Trang sẽ chạy ở `https://<tên-github>.github.io/xuong-art/`.

### Cách 2: dùng git

```bash
cd xuong-art
git init
git add .
git commit -m "Xưởng Art"
git branch -M main
git remote add origin https://github.com/<tên-github>/xuong-art.git
git push -u origin main
```

Sau đó bật Pages như bước 5 ở trên.

## Chạy thử trên máy

Tách nền AI cần chạy qua máy chủ web. Mở thẳng tệp `index.html` thì các công cụ khác vẫn chạy, nhưng AI sẽ không tải được mô hình.

```bash
cd xuong-art
python3 -m http.server 8000
# mở http://localhost:8000
```

## Cấu trúc thư mục

```
index.html                 toàn bộ giao diện và mã xử lý
favicon.svg
vendor/jszip.min.js        đóng gói ZIP
vendor/ort/                ONNX Runtime Web 1.20.1 (chạy mô hình AI)
models/u2netp.onnx         mô hình Nhanh (4,4 MB)
models/silueta.part1.bin   mô hình Chi tiết, chia 2 phần
models/silueta.part2.bin   để mỗi phần dưới 25 MB
```

## Ghi công

Xem `THIRD_PARTY_NOTICES.md`.

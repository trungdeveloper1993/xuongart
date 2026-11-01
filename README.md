# Xưởng Art

Bộ công cụ chuẩn bị art chạy hoàn toàn trong trình duyệt. Ảnh được xử lý ngay trên máy người dùng và không tải lên máy chủ nào.

**Dùng ngay:** https://trungdeveloper1993.github.io/xuongart/

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

## Cập nhật trang GitHub Pages

Trang được GitHub Pages lấy thẳng từ nhánh `main` (thư mục gốc), không có bước build. Mỗi khi `main` có commit mới, GitHub tự đăng lại trang sau khoảng 1–2 phút.

### Cách 1: sửa trên github.com

1. Mở tệp cần sửa (thường là `index.html`), bấm biểu tượng bút chì, sửa xong bấm **Commit changes** vào nhánh `main`.
   Muốn thêm hoặc thay tệp thì dùng **Add file → Upload files** (mỗi tệp phải dưới 25 MB).
2. Mở tab **Actions** để xem lượt chạy *pages build and deployment*. Có dấu tích xanh là trang đã cập nhật.

### Cách 2: dùng git

```bash
git clone https://github.com/trungdeveloper1993/xuongart.git
cd xuongart
# sửa tệp…
git add .
git commit -m "Mô tả thay đổi"
git push origin main
```

Nếu làm trên nhánh khác thì mở pull request vào `main` rồi merge. Trang chỉ đổi khi thay đổi đã nằm trên `main`.

### Trang vẫn hiện bản cũ?

- Tải lại bỏ qua cache: Ctrl+Shift+R (macOS: Cmd+Shift+R).
- Kiểm tra **Settings → Pages**: Source là **Deploy from a branch**, Branch là **main**, thư mục **/ (root)**.
- Mô hình AI và bộ chạy ONNX được trình duyệt lưu lại theo đường dẫn (bộ nhớ đệm `xuong-art-ai-v1` trong `index.html`). Nếu thay tệp trong `models/` hoặc `vendor/ort/` mà giữ nguyên tên, hãy đổi tên bộ nhớ đệm đó (ví dụ `xuong-art-ai-v2`) và cập nhật số byte trong `MODELS` / `WASM_BYTES` của `index.html`, để người dùng cũ tải bản mới.

## Chạy thử trên máy

Tách nền AI cần chạy qua máy chủ web. Mở thẳng tệp `index.html` thì các công cụ khác vẫn chạy, nhưng AI sẽ không tải được mô hình.

```bash
cd xuongart
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

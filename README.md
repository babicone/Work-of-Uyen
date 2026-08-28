# Babi Time Tracker

Trang web đơn giản (không cần server, không cần code) để key thời gian + task theo đúng flow chị mô tả:

1. Vào trang → **STEP 01**: nhập Company, chọn Task group, nhập Task name → tool tự ráp thành `Company – Year – Week# – Task name`
2. **STEP 02**: hiện ảnh SOP nhắc lại quy trình cho nhóm task đó (ảnh trong thư mục `sop/`, hiện đang là ảnh placeholder — thay bằng ảnh SOP thật của chị)
3. **STEP 03**: bấm **Start**, xong việc bấm **Check out**
4. **STEP 04** (optional): dán link file kết quả đã upload
5. **STEP 05**: xem lại lịch sử toàn bộ task đã track + bấm **Export CSV report** để gửi khách/đối chiếu

Dữ liệu lưu trong **localStorage của trình duyệt** (không cần tài khoản, không cần database) — nghĩa là chỉ nằm trên máy/trình duyệt chị đang dùng để track. Nếu sau này cần nhiều người cùng team track chung 1 chỗ, sẽ cần thêm 1 lớp lưu trữ chung (Google Sheet, Airtable, hoặc database thật) — đây là bước nâng cấp sau, ngoài phạm vi bản này.

## Cách đưa lên GitHub Pages — KHÔNG CẦN CODE, KHÔNG CẦN TERMINAL

1. Vào repo GitHub của chị trên trình duyệt (repo chị đã tạo, ví dụ `babicone/time-tracker`)
2. Bấm nút **Add file → Upload files**
3. Kéo thả toàn bộ các file trong thư mục này vào (`index.html`, `style.css`, `script.js`, `CNAME`, và cả thư mục `sop/` với các ảnh bên trong)
4. Bấm **Commit changes**
5. Vào **Settings → Pages** (menu bên trái repo)
6. Ở mục **Source**, chọn nhánh `main` (hoặc `master`) và thư mục `/ (root)` → **Save**
7. Đợi 1–2 phút, GitHub sẽ cho link dạng `https://<username>.github.io/<repo>/` — vào thử để chắc trang chạy được

## Gắn domain riêng (babi.cone)

⚠️ **Lưu ý:** `.cone` không phải là đuôi tên miền phổ biến — chị double-check lại đúng chính tả tên miền đã mua nhé (mở file `CNAME` sửa lại nếu cần, chỉ có đúng 1 dòng là tên miền, không có `https://`, không có dấu `/`).

1. Trong **Settings → Pages** của repo, mục **Custom domain**, nhập tên miền của chị (vd `babi.cone`) → Save (GitHub tự tạo file `CNAME` — nếu chị đã upload sẵn file `CNAME` ở bước trên thì khỏi cần nhập lại)
2. Qua nơi chị mua domain (Namecheap, GoDaddy, Mắt Bão, v.v.), vào phần quản lý DNS, thêm:
   - 4 bản ghi **A** trỏ về các IP của GitHub Pages:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - (nếu dùng subdomain như `www`) 1 bản ghi **CNAME** trỏ về `<username>.github.io`
3. Đợi DNS cập nhật (có thể vài phút đến vài giờ), sau đó vào lại **Settings → Pages** bấm **Enforce HTTPS** để bật https

## Sửa nhóm task / thêm ảnh SOP thật

Mở file `script.js`, sửa mảng `TASK_GROUPS` ở đầu file — đổi tên nhóm, thêm/bớt nhóm, hoặc đổi đường dẫn ảnh SOP. Ảnh SOP thật thì up thẳng vào thư mục `sop/`, đặt tên trùng với tên trong `script.js`.

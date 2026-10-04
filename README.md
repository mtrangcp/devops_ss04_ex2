## 1. Các bước thực hiện và giải quyết xung đột thủ công

1. **Khởi tạo và chuyển sang nhánh mới (`feature-update`):**
   - Chạy lệnh tạo và chuyển nhánh: `git checkout -b feature-update`
   - Chỉnh sửa nội dung một dòng bất kỳ tại file `README.md`, sau đó lưu lại.
   - Thêm vào staging area và commit:
     ```bash
     git add README.md
     git commit -m "Update README on feature-update branch"
     ```

2. **Tạo xung đột từ nhánh chính (`main`):**
   - Chuyển về nhánh `main`: `git checkout main`
   - Mở lại file `README.md`, sửa **chính xác cùng một dòng code** như trên nhưng với nội dung khác, rồi lưu lại.
   - Thêm vào staging area và commit trên nhánh `main`:
     ```bash
     git add README.md
     git commit -m "Update README on main branch"
     ```

3. **Gộp nhánh và kích hoạt xung đột (Merge Conflict):**
   - Chạy lệnh gộp: `git merge feature-update`
   - Hệ thống trả về trạng thái xung đột (`CONFLICT (content): Merge conflict in README.md`).

4. **Giải quyết xung đột thủ công:**
   - Mở file `README.md`, tìm các ký hiệu phân tách do Git tạo ra (`<<<<<<<`, `=======`, `>>>>>>>`).
   - Xóa bỏ các ký hiệu đánh dấu và chỉnh sửa lại nội dung đoạn văn bản cho hoàn chỉnh theo ý muốn.
   - Đưa file đã chỉnh sửa trở lại staging area: `git add README.md`
   - Hoàn tất quá trình gộp nhánh (Merge Commit):
     ```bash
     git commit -m "Resolve merge conflict in README.md via 3-way merge"
     ```

## 2. Kiểm tra kết quả đồ thị nhánh

- Chạy lệnh kiểm tra lịch sử phân rẽ và hợp nhánh:
  ```bash
  git log --graph --oneline
  ```

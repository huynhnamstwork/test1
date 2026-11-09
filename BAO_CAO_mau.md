# Báo cáo Phần A

## 1. Thông tin
- Repo: https://github.com/<user>/git-lab-<mssv>
- A: ...   B: ...

## 2. Lịch sử commit
(Dán kết quả `git log --oneline --graph --all`)

## 3. Kiểm tra push trực tiếp vào develop
**Lệnh:** `git push origin develop`

**Thông báo lỗi GitHub trả về:**
```
(dán nguyên văn)
```

**Giải thích:** Nhánh `develop` đã bật branch protection (bắt buộc Pull Request, cần ít nhất 1 người duyệt),
nên GitHub từ chối push trực tiếp. Mọi thay đổi phải đi qua nhánh feature -> PR -> review -> merge,
giúp code luôn được kiểm tra trước khi vào nhánh chung.

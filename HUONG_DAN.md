# Hướng dẫn Phần A (GitHub Desktop)

Đặt tên repo: `git-lab-<mssv>` (A là chủ repo, B là collaborator).

## Bước 1 - Tạo repo + mời B
1. Vào github.com > New repository. Tên `git-lab-<mssv>`.
   Tick **Add a README file**, **Add .gitignore > Python**. Nhánh mặc định phải là `main`.
   (Hoặc dùng file trong `buoc1_khoi_tao/` để thay README/.gitignore, sửa `<MSSV>`.)
2. Settings > Collaborators > Add people > mời B, B bấm chấp nhận lời mời.
3. GitHub Desktop: File > Clone repository > chọn repo > Clone.

## Bước 2 - Tạo nhánh develop từ main
1. Desktop: Current Branch > New Branch, tên `develop`, "Create branch based on" = `main`.
2. Bấm **Publish branch** để push lên GitHub.

## Bước 3 - Bảo vệ nhánh main và develop
Settings > Branches > Add branch ruleset (hoặc Add classic branch protection rule), làm cho cả `main` và `develop`:
- Tick **Require a pull request before merging**
- **Required approvals = 1**
- Chặn push trực tiếp (đã bao gồm khi bắt buộc PR). Với classic rule, tick thêm **Do not allow bypassing / Include administrators** để chính A (admin) cũng bị chặn.
Lưu ý: repo **private** trên tài khoản free có thể không dùng được branch protection. Hãy để repo **public** hoặc dùng GitHub Education/Pro.

## Bước 4 - Thêm app/calc.py qua feature/1-calc
1. Desktop: chuyển sang `develop`, New Branch `feature/1-calc` (based on `develop`).
2. Copy thư mục `app/` từ `buoc4_feature_calc/` vào thư mục repo (mở bằng Repository > Show in Explorer/Finder).
3. Desktop: ghi Summary `feat: add add and sub functions in calc`, bấm Commit, rồi Publish branch.
4. Bấm **Create Pull Request** (base = `develop`, compare = `feature/1-calc`).
5. B vào PR > Files changed > Review changes > Approve.
6. A bấm **Squash and merge**. (Có thể xóa nhánh feature sau khi merge.)

## Bước 5 - Commit dùng Conventional Commits
Ví dụ:
- `feat: add add and sub functions in calc`
- `docs: update README with branch model`
- `fix: correct sub function`

## Kiểm tra - push trực tiếp vào develop (để ra lỗi)
1. Desktop: chuyển sang `develop`, Fetch/Pull origin cho mới nhất.
2. Sửa nhỏ README.md, commit `docs: test direct push`.
3. Mở terminal trong repo (Repository > Open in Command Prompt/Terminal) chạy:
   `git push origin develop`
4. GitHub sẽ từ chối, thường có dạng:
   `remote: error: GH006: Protected branch update failed for refs/heads/develop.`
   `remote: error: Changes must be made through a pull request.`
5. Chụp/ghi lại nguyên văn thông báo, dán vào báo cáo (xem BAO_CAO_mau.md).
6. Dọn lại: `git reset --hard origin/develop` để bỏ commit thử.

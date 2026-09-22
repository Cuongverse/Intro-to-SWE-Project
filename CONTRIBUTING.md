# QUY ĐỊNH ĐÓNG GÓP MÃ NGUỒN & QUẢN TRỊ DỰ ÁN (CONTRIBUTING GUIDELINES)
> Dành cho các thành viên phát triển dự án E-Commerce & Order Management System.

Để đảm bảo tiến độ, chất lượng mã nguồn và tránh xung đột (merge conflicts), toàn bộ 5 thành viên bắt buộc phải tuân thủ các quy tắc dưới đây.

---

## 1. QUY TẮC PHÂN NHÁNH (GIT BRANCHING STRATEGY)

* ⛔ **TUYỆT ĐỐI KHÔNG commit hoặc push trực tiếp lên nhánh `main` và `develop`.**
* **Cấu trúc nhánh chính:**
  * `main`: Nhánh chạy ổn định nhất (Production-ready). Chỉ merge từ `develop` khi chuẩn bị nộp bài hoặc báo cáo tiến độ với giảng viên.
  * `develop`: Nhánh tích hợp chung của toàn nhóm. Mọi tính năng sau khi test xong sẽ được merge về đây.
* **Cấu trúc nhánh làm việc (Feature branches):**
  * Tách nhánh mới từ `develop`:
    ```bash
    git checkout develop
    git pull origin develop
    git checkout -b <loại-nhánh>/<mô-tả-ngắn-gọn>
    ```
  * **Quy ước đặt tên nhánh:**
    * Quy ước duy nhất: đặt tên theo tên của mọi người:

---

## 2. QUY ƯỚC COMMIT MESSAGE (CONVENTIONAL COMMITS)

Tất cả commit message lên **BRANCH CỦA MÌNH** phải viết rõ ràng:

```text
<mô tả ngắn bằng tiếng Việt hoặc tiếng Anh>
VD: git commit -m "added user authentication"
```
Tránh các mô tả như "fix bug", "update code", "asdasd", "xong roi"

## 3. Quy Chuẩn Đặt Tên (Naming Conventions)

| Đối tượng | Quy tắc | Ví dụ chuẩn | Không nên dùng |
| :--- | :--- | :--- | :--- |
| **Biến (Variables)** | `snake_case` (chữ thường, nối gạch dưới) | `total_amount`, `store_id` | `totalAmount`, `Total_Amount` |
| **Hàm / Phương thức** | `snake_case` (thường bắt đầu bằng động từ) | `get_inventory()`, `calculate_total()` | `GetInventory()`, `calculateTotal()` |
| **Lớp (Classes / Models)**| `PascalCase` (viết hoa chữ đầu mỗi từ) | `StoreInventory`, `SalesOrder` | `store_inventory`, `salesOrder` |
| **Hằng số (Constants)** | `UPPER_SNAKE_CASE` (in hoa toàn bộ) | `MAX_STOCK_ALERT`, `JWT_SECRET_KEY` | `maxStockAlert`, `Max_Stock_Alert` |
| **File / Module** | `snake_case` (chữ thường toàn bộ) | `database.py`, `sales_router.py` | `Database.py`, `salesRouter.py` |
| **Package / Thư mục** | `lowercase` (chữ thường ngắn gọn) | `routers/`, `schemas/`, `models/` | `Routers/`, `my_schemas/` |
| **Biến riêng tư (Private)**| `_snake_case` (tiền tố 1 dấu gạch dưới) | `_verify_token()`, `_db_conn` | `verify_token_private()` |

## 4. Quy trình PULL REQUEST (PR)
1. Đồng bộ code mới nhất trước khi tạo PR:
```text
git checkout develop
git pull origin develop
git checkout <nhánh-của-bạn>
git merge develop
# Giải quyết conflict (nếu có) trên máy cá nhân rồi mới push
git push origin <nhánh-của-bạn>
```
2. Mở Pull Request trên Gihub (desktop/web)
* Tiêu đề PR: rõ ràng, tóm tắt công việc đã làm.
* Nội dung PR:
* ** Mô tả những gì đã làm/đã sửa.
* ** Đính kèm video/hình ảnh demo (nếu có). 


# Báo Cáo MLOps Pipeline

**Họ và tên:** Phạm Nguyễn Tiến Mạnh
**MSSV:** 2A202600418

---

## Bộ Siêu Tham Số Đã Chọn

| Tham số             | Giá trị |
| ------------------- | ------- |
| `n_estimators`      | 200     |
| `max_depth`         | 25      |
| `min_samples_split` | 10      |

**Lý do lựa chọn:**

- `n_estimators=200`: Số lượng cây đủ lớn để mô hình ổn định, tránh variance cao so với giá trị nhỏ (ví dụ 50–100), nhưng không quá lớn gây tốn tài nguyên.
- `max_depth=25`: Cho phép cây học được các pattern phức tạp trong dữ liệu Wine Quality mà không bị underfitting, đồng thời vẫn kiểm soát được overfitting nhờ `min_samples_split`.
- `min_samples_split=10`: Hạn chế việc tách nút quá sâu trên các nhóm dữ liệu nhỏ, giúp mô hình tổng quát hóa tốt hơn trên tập eval.

Bộ tham số này được chọn sau khi thực nghiệm trên MLflow với nhiều cấu hình khác nhau và đạt accuracy vượt ngưỡng `EVAL_THRESHOLD = 0.662`.

# Báo cáo Day 14 — Nguyễn Thái Dương — 2A202603207

- Mã học viên dùng với `--student`: `2A202603207`
- `seed_tag` trong `frames_A.txt`: `393590736f`

## 1. Dự đoán trước sweep (bước 5b)

Ghi **trước** khi chạy `scripts/pp_sweep.py`, rồi commit và push ngay (lịch sử commit là bằng chứng thời điểm viết). Không sửa phần này sau khi có kết quả.

- Tham số tôi nghĩ giảm công sửa nhiều nhất: min_points
- Vì sao (nhìn ảnh BEV tập A: box thừa nhiều hay box sót nhiều?): box thừa nhiềusss

## 2. Tập A: sửa tay và tune

| Cấu hình | Xóa | Thêm | Sửa | Chi phí |
|---|---:|---:|---:|---:|
| Gốc | 77 | 0 | 0 | 23.1 |
| `best_config.json` | 14 | 4 | 0 | 8.2 |

- Tham số đã đổi trong `best_config.json`: `score_thr` 0.1 → 0.5 (`min_points` giữ 0).
- Kết quả leave-one-out:
s02f46: cấu hình chọn {'score_thr': '0.5', 'min_points': '0'} → 2.5 (tốt nhất có thể 2.5)
s04f12: cấu hình chọn {'score_thr': '0.5', 'min_points': '0'} → 3.2 (tốt nhất có thể 2.8)
s05f36: cấu hình chọn {'score_thr': '0.5', 'min_points': '0'} → 2.5 (tốt nhất có thể 2.5)
- Cấu hình có chạy ổn trên từng frame

- Cấu hình có ổn định trên từng frame không? Vì sao tôi vẫn chọn nó: <bạn tự viết 1–2 câu>

## 3. Trước/sau (bước 8)

Ảnh so sánh: `<tên file>.jpg` (nộp riêng trên LMS, sinh bởi `scripts/pp_compare.py`).

- `scripts/pp_compare.py` báo giảm 65% công sửa trên tập A (chi phí 23.1 → 8.2; s02f46 10.5 → 2.5, s04f12 5.1 → 3.2, s05f36 7.5 → 2.5).
- Dự đoán ở mục 1 đúng hay sai? Giải thích bằng số box xóa/thêm/sửa: mục 1 đúng, số box bị xóa khá nhiều vì không có điểm Lidar và đối chiếu với ảnh từ camera thì không có vật thể tương ứng 

## 4. Tập B

Số đo từ `scripts/pp_prelabel.py --frames d14_<ID>/frames_B.txt --config d14_<ID>/best_config.json --gt d14_<ID>/ref_B.json`:

| Xóa | Thêm | Sửa | Chi phí |
|---:|---:|---:|---:|
| | | | |

- Loại box tốn công sửa nhất ở tập B: ...

## 5. Giới hạn

- Nêu ít nhất 2 giới hạn (ví dụ: chỉ 3 frame tune; model KITTI không có Truck/Bus; chi phí là công thức, chưa phải thời gian sửa thật): ...

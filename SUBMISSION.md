# Hướng dẫn nộp bài (SUBMISSION)

## 1. Hình thức nộp bài
- Bài tập được thực hiện theo hình thức **cá nhân**.
- **Mỗi cá nhân phải tự nộp link repo của mình lên hệ thống LMS / Codelab** theo thông báo của giảng viên hoặc coach (mỗi học viên một repository riêng, không nộp hộ, không dùng chung repo).
- Repository phải được để ở chế độ Public (hoặc cấp quyền truy cập cho giảng viên / coach nếu được yêu cầu).

## 2. Quy chuẩn đặt tên Repository

Cấu trúc tên repository nộp bài:

```text
K4-L3A-DAY14-<HoVaTen>-<MSSV>-AIEvaluation
```

- `<HoVaTen>`: Họ và tên viết liền không dấu (PascalCase).
- `<MSSV>`: Mã số sinh viên chính xác.

**Ví dụ:**
```text
K4-L3A-DAY14-NguyenVanAn-L3A202600280-AIEvaluation
```

> ⚠️ **Lưu ý:** Đặt sai tên repository sẽ bị trừ **5 điểm** theo quy định trong [RUBRIC.md](RUBRIC.md).

## 3. Thành phần bài nộp (Deliverables)

| File | Yêu cầu |
|---|---|
| `solution/solution.py` | Hoàn thiện tất cả TODO bắt buộc |
| `golden_dataset.json` | Đủ 20 QA, đúng schema |
| `exercises.md` | worksheet, benchmark 3.2, rubric 3.3 |
| `reflection.md` | report, 3 failures, 5 Whys, regression |

Các file sinh ra trong quá trình chạy (artifacts) là tùy chọn (optional):
- `artifacts/actual_answers.json`
- `artifacts/benchmark_results.json`

> ⚠️ **CẢNH BÁO BẢO MẬT:** Tuyệt đối **KHÔNG commit** file `.env`, OpenAI API key hoặc bất kỳ thông tin bí mật nào lên GitHub repository. Vi phạm sẽ bị trừ **10 điểm**.

## 4. Nơi nộp và Hạn nộp (Deadline)
- **Nơi nộp:** Nộp link GitHub repository cá nhân lên LMS / Codelab.
- **Hạn chót mặc định:** **23h59 ngày lab (GMT+7)**.
- Coach có thể gia hạn tối đa không quá **48 giờ (≤48h)** đối với các trường hợp đặc biệt có lý do chính đáng được phê duyệt trước.

## 5. Checklist kiểm tra trước khi nộp

Hãy chạy các kiểm tra sau và tích chọn đầy đủ trước khi nộp bài:

- [x] Repository đã được đặt đúng tên chuẩn: `K4-L3A-DAY14-<HoVaTen>-<MSSV>-AIEvaluation`.
- [x] Chạy `python validate_golden_dataset.py` báo `PASS`.
- [x] Toàn bộ required tests pass khi chạy `pytest tests/ -v` (41 passed, 1 skipped nếu không làm bonus; ở đây 42/42 tests pass bao gồm cả bonus reranking).
- [x] `golden_dataset.json` đủ 20 QA (5 Easy + 7 Medium + 5 Hard + 3 Adversarial).
- [x] Đã kiểm tra `artifacts/actual_answers.json` sau khi chạy RAG (`python domain_assistant.py`).
- [x] `exercises.md` đã hoàn thành đầy đủ: Exercise 3.2 có đủ năm metrics và ba cases thấp nhất; Exercise 3.3 có rubric 1–5 và edge cases (Exercise 3.4 & 3.5 nếu chọn làm bonus).
- [x] `reflection.md` có ba 5 Whys analyses, bảng failure taxonomy và improvement log / regression strategy.
- [x] `solution/solution.py` là bản hoàn thiện của `template.py` (học viên đã copy sau khi hoàn thành code).
- [x] Không commit `.env`, API key hoặc dữ liệu nhạy cảm lên GitHub.

---

## Tài liệu liên quan
- [README.md](README.md) — Tổng quan bài lab và hướng dẫn khởi động
- [RUBRIC.md](RUBRIC.md) — Tiêu chí chấm điểm chi tiết và các trường hợp trừ điểm
- [CHECKPOINTS.md](CHECKPOINTS.md) — Hướng dẫn từng checkpoint và tiêu chuẩn nghiệm thu
- [RULES.md](RULES.md) — Quy định làm bài, sử dụng AI và bảo mật

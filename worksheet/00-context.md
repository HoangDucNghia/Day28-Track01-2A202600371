---
title: 00 — Context (bối cảnh nhóm + track)
section: Day 28 — điền 1 lần đầu buổi, dùng lại cho mọi lần hỏi AI
format: Nhóm 3
time: Điền ~5 phút đầu buổi
---

# 00-context.md — Context nhóm + track

Điền file này một lần ở đầu buổi. Mỗi lần dùng AI ở các bước sau, paste nguyên nội dung file này vào đầu cuộc trò chuyện. AI không tự nhớ context giữa các lần — context khác nhau thì câu trả lời cũng lệch.

---

## 1. Bối cảnh AI20k (đọc, không sửa)

Khóa **AI Thực Chiến** có ~500 học viên (sinh viên năm cuối + người đi làm), đang chuẩn bị cho giai đoạn 6 tuần thực chiến sau Day 28. Lab này do track Product (~80 học viên, nhóm 3) làm. Hoạt động cả khóa nằm trên Discord, LMS, lớp live, lab, nộp bài, coaching — ở quy mô ~500 người.

Lãnh đạo chương trình muốn xây **AI20k Learning OS** — một hệ công cụ AI hỗ trợ học và vận hành khóa. Chính quy mô ~500 người là lý do **không build hết cùng lúc** được: mỗi nhóm nhận 1 track (1 công cụ lớn), tách nhỏ, chọn Quick Win, viết AI Pilot Plan để xin pilot.

Việc của nhóm hôm nay đúng là việc một PM/PO AI làm ngoài doanh nghiệp thật: stakeholder giao một "công cụ AI" quá lớn — bạn phải tách nhỏ, chọn đúng phần làm trước, và bảo vệ lựa chọn bằng lập luận chứ không bằng slide đẹp.

---

## 2. Track của nhóm (điền sau khi nhận track card)

- **Track số / tên**: Track 4 — Bộ nhớ học tập / Knowledge Graph
- **Big Ask — chép nguyên văn câu yêu cầu trong track card**:

```text
Xây bộ nhớ học tập xuyên suốt khóa — concept, framework, case, slide, lab, các ngày trước được liên kết để học viên tra cứu và thấy mối liên hệ.
```

- **Công cụ lớn này phục vụ ai** (học viên / coach / instructor / admin): Học viên, coach, instructor
- **2 Red Flag đáng lo nhất (chép từ track card)**: 1. Knowledge graph quá to, không ai bảo trì — liên kết nhiều nhưng không giúp hành động  2. Sai nguồn/citation — bộ nhớ cá nhân chạm quyền riêng tư

---

## 3. Ràng buộc mọi track phải tôn trọng (đọc, không sửa)

- **Privacy** — data học viên/submission/Discord nhạy cảm; trong lab dùng data mẫu/giả định, nói rõ dùng cái gì.
- **Human review** — output rủi ro cao phải có người review, AI không tự quyết việc quan trọng.
- **Citation** — trả lời dựa trên tài liệu khóa thì phải có nguồn; thiếu nguồn thì nói "không biết", không bịa.
- **Budget nhỏ** — ưu tiên tool/API có sẵn, prototype nhanh, không xây platform lớn.
- **Formative ≠ summative** — feedback/chấm bằng AI là formative, chưa phải điểm chính thức nếu chưa có người calibrate.
- **Adoption** — tool không ai dùng = $0 dù accuracy 99%.
- **Pilot đủ nhỏ** — chạy được trong bối cảnh khóa hiện tại.

---

## 4. Ghi chú thêm (tùy nhóm)

- **Hạn chót nộp bài**: 23:59 hôm nay (Day 28).
- **Quy mô data giả định**: Slide, instructor notes, framework, case bank, gói lab, FAQ từ ~28 ngày học (D1–D28). Dùng data mẫu/giả định trong lab, không dùng data thật của học viên.
- **Hiện trạng**: Kiến thức nằm rải rác: slide, Discord, LMS, instructor notes, lab, case bank. Học viên hay quên D2/D27 khi sang D28.
- **Module tầm nhìn lớn (chép từ track card)**: Bản đồ concept giữa các ngày · tìm theo câu hỏi ("D28 dùng lại gì từ D2?") · liên kết framework → case → template lab · bộ nhớ học tập cá nhân (đã gặp lỗi gì) · bộ nhớ cho coach (nhóm này đã được feedback gì) · truy hồi câu trả lời có nguồn.
- **Quick Win gợi ý (chép từ track card)**: Bot trả lời "concept X nằm ở đâu trong khóa?" có nguồn · map D2 Design Thinking → D27 Economics → D28 AI Pilot Plan · tạo knowledge card cho 10 concept quan trọng của D28.
- **Ví dụ câu hỏi thật học viên có thể hỏi**: "Double Diamond là gì và được dùng ở ngày nào?", "D28 dùng lại framework gì từ D26 và D27?", "Baseline là gì, được dạy ở bài nào?"

---

## Cách dùng

```text
1. Đầu buổi: điền mục 2 (+ mục 4 nếu cần). Mục 1 và 3 chỉ để đọc.
2. Mỗi lần mở AI ở một bước: paste nguyên file này vào đầu chat trước.
3. Chọn prompt trong ../prompts/ hợp bước đang làm, chỉnh lại theo track.
4. Đọc kỹ bản nháp AI ra → sửa cho đúng context nhóm → lưu vào đúng file worksheet/.
```

Chỗ `[...]` là chỗ cần điền; điền xong xóa ngoặc nếu muốn.

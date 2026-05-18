---
artifact: 1 — Track & Big Ask + 2 — Tool Breakdown
bai-tap: Frame — nghe đúng đề rồi tách nhỏ
phase: Double Diamond vòng 1 · ◇ giãn (nghe rộng, chưa chốt)
time: ~12 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 00-context.md · track card · prompts/01-breakdown.md
nop-cuoi: Không — file trung gian (bản chốt phase này ở 3-FINAL-problem-framing.md)
---

# 1 — Intake & Breakdown: nghe đúng đề, tách nhỏ

Mục tiêu: cả nhóm hiểu giống nhau "công cụ lớn stakeholder muốn", rồi tách nó thành 5–8 use case nhỏ làm được riêng. Đây là nửa "giãn ra" của [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) vòng 1 — nghe rộng, tách rộng, chưa chọn.

Lý do làm bước này: hai cái bẫy chết người ở đây. Một, nhận đề literal ("làm con chatbot") rồi nhảy vào build — trong khi yêu cầu mơ hồ thường chỉ là triệu chứng. Hai, ôm cả công cụ lớn đi pitch "build cả platform" → trượt Gate 1 ngay. Tách nhỏ là động tác bắt buộc để từ "một ý tưởng to" sang "danh sách phần làm được".

Quy tắc: **nghe trước, tách trước, chưa chọn.** Bước này không được chốt Quick Win (việc đó ở file `2`).

## Bước 0 — Đọc track card + 00-context (2 phút)

Đọc track card được giao và `00-context.md` (mục 2 đã điền). Đừng lướt.

## Quy trình 12 phút

```text
2 phút  — Bước 0: đọc track card + context
4 phút  — Phần A: phát biểu lại Big Ask bằng lời nhóm
6 phút  — Phần B: tách 5–8 use case + check độc lập
```

---

## Phần A — Phát biểu lại Big Ask bằng lời nhóm

Đừng chép lại đề. Cả nhóm nói lại "công cụ lớn stakeholder muốn" bằng lời mình. Nếu 3 người nói 3 kiểu khác nhau → chưa hiểu giống nhau, bàn thêm.

Câu hỏi phụ (tự trả lời):

- Stakeholder nói họ muốn gì, và họ thực sự *cần* gì — có khác nhau không?
- "Tại sao bây giờ?" — ở quy mô ~500 người, cái gì đang đau khiến phải làm công cụ này lúc này?
- Ai là người dùng đầu tiên thật sự, không phải "cả khóa"?

### Trả lời

- **Big Ask, viết lại bằng lời nhóm (2–3 câu)**:

Nhóm hiểu stakeholder không chỉ muốn “một chatbot trả lời câu hỏi”, mà muốn xây một bộ nhớ học tập dùng được xuyên suốt khóa AI20K. Hệ thống này cần giúp học viên, coach và instructor tìm lại kiến thức cũ, thấy mối liên hệ giữa các ngày học, framework, lab và case thay vì kiến thức bị nằm rải rác trên slide, Discord và LMS. Quan trọng hơn, tool phải giúp người dùng “học tiếp được” và hành động được nhanh hơn, chứ không chỉ lưu trữ thông tin như một thư viện tài liệu.

- **Tại sao bây giờ**:

Ở quy mô ~500 học viên và chuẩn bị bước vào 6 tuần thực chiến, lượng kiến thức giữa các ngày đã quá lớn và phân tán. Học viên thường quên framework cũ (ví dụ D2, D27) khi làm bài ở D28 hoặc giai đoạn pilot sau này. Coach và instructor cũng mất thời gian trả lời lại các câu hỏi lặp đi lặp lại hoặc tìm tài liệu cũ để feedback. Nếu không có hệ thống truy hồi kiến thức có nguồn rõ ràng, việc scale coaching và tự học sẽ ngày càng khó.

- **Người dùng đầu tiên cụ thể**:

Học viên đang bước vào giai đoạn làm AI Pilot Plan sau Day 28 — đặc biệt là những nhóm cần nối lại framework, lab và case từ các ngày trước để làm bài nhưng không nhớ nội dung nằm ở đâu.

---

## Phần B — Tách công cụ lớn thành 5–8 use case

| # | Use case (AI làm gì · cho ai · để họ làm được gì) | Người dùng | Làm được độc lập? |
|---|---|---|---|
| 1 | AI trả lời “concept/framework X nằm ở đâu trong khóa?” kèm source từ slide/lab để học viên tìm lại nhanh kiến thức cũ | Học viên | Có |
| 2 | AI liên kết concept giữa nhiều ngày học (ví dụ D2 → D27 → D28) để học viên hiểu kiến thức được dùng lại như thế nào | Học viên | Có |
| 3 | AI gợi ý framework/lab/case liên quan khi học viên hỏi một vấn đề cụ thể để hỗ trợ làm assignment hoặc pilot | Học viên | Có |
| 4 | AI tạo knowledge card tóm tắt cho mỗi concept quan trọng gồm định nghĩa, ví dụ, nguồn và ngày học | Học viên | Có |
| 5 | AI lưu lại các lỗi hoặc feedback học viên từng gặp để học viên tránh lặp lại lỗi trong các bài sau | Học viên | Không — phụ thuộc #1 và hệ thống memory |
| 6 | AI cho coach xem nhóm này đã từng nhận feedback gì trước đó để tránh feedback trùng lặp và coaching liên tục hơn | Coach | Không — phụ thuộc hệ thống memory |
| 7 | AI tìm và truy hồi câu trả lời có citation từ instructor notes, handbook và slide để instructor trả lời nhanh hơn | Instructor | Có |
| 8 | AI map framework → case → template lab để học viên biết khi nào nên dùng framework nào trong bài thực tế | Học viên | Có |

---

## Phát hiện ban đầu

- Những use case liên quan “personal memory” hoặc “coach memory” hấp dẫn nhưng phức tạp hơn nhiều vì liên quan privacy, tracking và đồng bộ dữ liệu người dùng.
- Các use case truy hồi kiến thức có citation từ slide/lab có vẻ nhỏ hơn, dễ pilot hơn và chứng minh giá trị nhanh hơn trong bối cảnh 1 khóa học.
- Một số ý tưởng ban đầu thực ra chỉ là tính năng vụn (ví dụ “search slide”) chứ chưa phải use case hoàn chỉnh gắn với hành động của người dùng.
- Nếu ôm toàn bộ “knowledge graph” ngay từ đầu thì scope sẽ quá lớn và khó bảo trì.

## Câu hỏi mở (mang sang bước chọn Quick Win)

- Quick Win đầu tiên nên tập trung vào “retrieval có source” hay “concept mapping giữa các ngày”?
- Dữ liệu nào sẽ được dùng thật trong pilot: slide PDF, instructor notes hay chỉ handbook/lab trước?
- Có cần human review cho citation trước khi trả lời học viên không?
- Làm sao để knowledge graph giúp hành động được, thay vì chỉ là “Wikipedia nội bộ”?

---

## Tổng kiểm tra trước khi sang `2-quick-win.md`

| Hạng mục | Xong? |
|---|---|
| Cả nhóm phát biểu lại Big Ask giống nhau, không cần nhìn card | ✅ |
| Có 5–8 use case dạng "AI làm X cho ai để Y" | ✅ (8 use case) |
| Có ≥4 use case thật sự độc lập | ✅ (6 độc lập: #1, #2, #3, #4, #7, #8) |
| Nhóm KHÔNG còn ý định pitch "build cả platform" | ✅ |

Sau bước này, mở `2-quick-win.md` — chấm điểm chọn 1 lát cắt làm trước.

*Liên quan: handbook §A1+§A2 · `prompts/01-breakdown.md` · `00-context.md`*
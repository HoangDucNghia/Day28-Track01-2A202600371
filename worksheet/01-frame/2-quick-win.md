---
artifact: 3 — Quick Win Selection
bai-tap: Frame — chọn lát cắt làm trước
phase: Double Diamond vòng 1 · ◆ siết (hội tụ về 1 lựa chọn)
time: ~10 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 1-intake-breakdown.md · prompts/02-quick-win-challenge.md
nop-cuoi: Không — file trung gian (bản chốt phase này ở 3-FINAL-problem-framing.md)
---

# 2 — Quick Win: chọn lát cắt làm trước

Mục tiêu: từ 5–8 use case ở file `1`, chấm điểm nhanh và chốt **1 Quick Win** để pilot đầu tiên — kèm lý do chọn và lý do *không* chọn các phần khác. Đây là nửa "siết lại" của [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) vòng 1.

Lý do làm bước này: đây là quyết định quan trọng nhất của phase Frame. Quick Win **không phải** phần dễ nhất hay nghe hay nhất — là phần *chứng minh được giá trị nhanh và có người ủng hộ*. Chọn sai → pilot fail → mất uy tín → khó xin pilot tiếp. Nhóm phải chọn được *và bảo vệ được bằng lý do*, không bằng cảm tính.

Quy tắc: **điểm số chỉ là gợi ý, không phải đáp án.** Đừng để con số quyết thay nhóm — nó chỉ giúp so sánh.

## Bước 0 — Lấy 4–6 use case mạnh nhất từ file `1` (1 phút)

## Quy trình 10 phút

```text
1 phút  — Bước 0: chọn 4–6 ứng viên
5 phút  — Phần A: chấm điểm 4 trục
3 phút  — Phần B: 1 lý do nên / 1 lý do không cho top 2
1 phút  — Phần C: chốt + ai ủng hộ + cái KHÔNG chọn
```

---

## Phần A — Chấm điểm 4 trục (1–5 mỗi trục)

Câu hỏi phụ (tự trả lời):

- "Risk" ở đây là *sai thì mất gì* — chọn đúng việc chính của user (task centrality) thì sai cũng đỡ đau; chọn việc lớn nhất thì sai rất đắt. Use case nào risk thấp thật?
- Use case nào có sẵn data + có người trong AI20k thật sự muốn dùng?

| Use case | Impact (×.30) | Feasibility (×.25) | Evidence (×.25) | Risk (×.20) | Tổng | Hạng |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| #1 — AI trả lời “concept/framework X nằm ở đâu?” kèm source | 5 | 5 | 5 | 5 | **5.00** | 1 |
| #4 — AI tạo knowledge card cho concept quan trọng | 3 | 5 | 4 | 5 | **4.15** | 2 |
| #8 — AI map framework → case → template lab | 4 | 4 | 4 | 4 | **4.00** | 3 |
| #2 — AI liên kết concept giữa nhiều ngày học (D2→D27→D28) | 4 | 3 | 3 | 4 | **3.75** | 4 |
| #5 — AI lưu lỗi và feedback cá nhân của học viên | 4 | 2 | 2 | 2 | **2.60** | 5 |
| #6 — AI cho coach xem feedback lịch sử của từng nhóm | 4 | 2 | 2 | 2 | **2.60** | 5 |

> **Công thức**: Tổng = Impact×0.30 + Feasibility×0.25 + Evidence×0.25 + Risk×0.20

(Thang điểm chi tiết: `templates/quick-win-scoring.md`.)

## Phần B — 1 lý do nên / 1 lý do không, cho top 2

**Ứng viên A — AI trả lời “concept/framework X nằm ở đâu trong khóa?” kèm source**

```text
Nên chọn vì:
Đây là pain xảy ra thường xuyên nhất ở AI20k: học viên không nhớ concept nằm ở đâu và coach/instructor phải trả lời lặp lại. Use case này có data sẵn (slide, handbook, lab), pilot nhỏ được bằng RAG/tool có sẵn và chứng minh hiệu quả rất nhanh qua số câu hỏi được trả lời đúng có citation.

Không nên vì:
Nếu citation sai hoặc retrieval sai nguồn, user sẽ mất trust rất nhanh. Dù scope nhỏ nhưng cần kiểm soát chất lượng nguồn khá kỹ.
```

**Ứng viên B — AI tạo knowledge card cho concept quan trọng**

```text
Nên chọn vì:
Làm khá nhanh, demo trực quan và giúp học viên ôn lại kiến thức dễ hơn. Có thể tạo từ tài liệu hiện có mà chưa cần knowledge graph phức tạp.

Không nên vì:
Nghe hay nhưng có nguy cơ trở thành “flashcard generator” ít dùng thật. Nó giúp đọc lại kiến thức nhưng chưa giải quyết pain lớn nhất là tìm và nối lại context giữa các ngày học.
```

## Phần C — Chốt Quick Win

- **Quick Win nhóm chọn**: AI trả lời “concept/framework X nằm ở đâu trong khóa?” kèm citation từ slide/lab/handbook
- **Vì sao chọn cái này trước** (2–4 câu, bám điểm + impact + evidence nhanh): Đây là use case có điểm tổng cao nhất vì vừa impact lớn, vừa khả thi trong pilot nhỏ. Dữ liệu đã có sẵn trong slide, lab và handbook nên nhóm có thể làm prototype bằng tool/API có sẵn thay vì build knowledge graph hoàn chỉnh. Ngoài ra, hiệu quả có thể đo rất nhanh trong 1–2 tuần qua số lượng câu hỏi được trả lời đúng, có source rõ ràng và giảm số câu hỏi lặp lại cho coach/instructor. Use case này cũng phù hợp triết lý “không build cả platform ngay”, mà chỉ chứng minh rằng retrieval có citation thực sự giúp học viên học tiếp được.
- **Ai trong AI20k sẽ ủng hộ pilot này** (và vì sao họ care — "có người ủng hộ" thường quan trọng hơn "impact cao"): 
- Coach — vì họ đang phải trả lời nhiều câu hỏi lặp (“framework này học ngày nào?”, “template nằm đâu?”). Tool giúp giảm tải coaching cơ bản.
- Học viên giai đoạn làm AI Pilot Plan — vì họ cần nối lại kiến thức cũ rất nhanh thay vì tự mò slide/Discord.
- Instructor — vì có thể đảm bảo câu trả lời bám đúng tài liệu khóa thay vì AI hallucinate.
- **Nhóm KHÔNG chọn gì + vì sao** (≥2 use case bị loại): 1. AI lưu lỗi và feedback cá nhân của học viên → Không chọn vì liên quan privacy, cần hệ thống memory/user tracking phức tạp và khó chứng minh nhanh trong 1 khóa.  2. AI cho coach xem feedback lịch sử của từng nhóm → Không chọn vì phụ thuộc dữ liệu coaching thực tế và có risk cao nếu AI truy hồi sai feedback hoặc lẫn giữa các nhóm. 3. AI liên kết concept giữa nhiều ngày học → Không chọn trước vì dù giá trị cao nhưng cần ontology/concept mapping phức tạp hơn retrieval cơ bản. Nên làm sau khi retrieval có source đã hoạt động ổn định.

---

## Phát hiện ban đầu

- Use case “retrieval có citation” thực ra là nền móng cho nhiều module khác của knowledge graph.
- Những use case có “memory cá nhân” hấp dẫn nhưng rủi ro cao hơn rất nhiều so với perception ban đầu.
- Demo đẹp chưa chắc impact thật; nhiều tính năng “visual hay” không giải quyết pain chính của học viên.

## Câu hỏi mở (mang sang Problem Framing)

- Citation sẽ hiển thị ở mức nào để user đủ trust? (slide/page/link?)
- Nếu AI không tìm được source rõ ràng thì nên trả lời thế nào?
- Pilot sẽ giới hạn trên loại data nào trước: slide D28 hay toàn bộ khóa?
- Success metric của pilot là giảm thời gian tìm tài liệu hay tăng accuracy câu trả lời?

---

## Tổng kiểm tra trước khi sang `3-FINAL-problem-framing.md`

| Hạng mục | Xong? |
|---|---|
| Có bảng chấm 4 trục cho ≥4 use case | ✅ (6 use case, có trọng số) |
| Chốt 1 Quick Win, lý do bám số/impact (không "nghe hay") | ✅ |
| Nêu rõ ai ủng hộ pilot này | ✅ (Coach, Học viên, Instructor) |
| Ghi rõ ≥2 phần KHÔNG chọn + lý do | ✅ (3 use case bị loại kèm lý do) |


⚑ Đây là phần coach kiểm tra ở Mốc 1: *"Vì sao không làm full tool? Vì sao chọn lát cắt này trước?"*

Sau bước này, mở `3-FINAL-problem-framing.md` — đóng khung vấn đề thật (bản nộp của phase Frame).

*Liên quan: handbook §A3 · `templates/quick-win-scoring.md` · `prompts/02-quick-win-challenge.md`*

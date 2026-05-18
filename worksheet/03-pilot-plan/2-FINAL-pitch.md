---
artifact: 8 — 5-slide Pitch + AI Support Log (bản nộp cuối lab)
bai-tap: Pilot Plan — dồn thành pitch, sẵn sàng phản biện
phase: Double Diamond vòng 2 · ◆ output (bản nộp cuối + present)
time: ~5 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 1-pilot-plan.md + toàn bộ 01-frame + 02-solution · templates/5-slide-pitch.md
nop-cuoi: Có — bản nộp cuối lab (Part E · 5-slide Pitch + AI Support Log)
---

# 2 — FINAL: 5-slide Pitch + AI Support Log

Mục tiêu: dồn cả A3 Working Canvas thành 5 slide pitch (5 phút), chuẩn bị trả lời 3 câu phản biện, và ghi AI Support Log. Đây là bản nộp cuối cùng của lab.

Lý do làm bước này: nguyên tắc *demo đơn giản + lập luận chặt > demo đẹp + lập luận yếu*. Slide đẹp mà không trả lời được "số này lấy ở đâu" thì hỏng. Pitch không phải kể chuyện — là đưa evidence để stakeholder ra được một quyết định.

Quy tắc: **slide cuối phải là một lời xin rõ ràng** (xin gì · đổi lại hứa gì). Không có lời xin = stakeholder không biết approve cái gì.

## Quy trình 5 phút

```text
3 phút  — Dồn 5 slide (mỗi slide 1 thông điệp)
1 phút  — Chuẩn bị 3 câu phản biện
1 phút  — AI Support Log
```

---

## Phần A — 5 slide (mỗi slide 1 thông điệp)

Kéo nguyên liệu từ các file đã làm, đừng viết mới. Khung đầy đủ: `templates/5-slide-pitch.md`.

| # | Slide | Lấy từ | Nội dung 1–2 gạch đầu dòng | Ai nói |
|---|---|---|---|---|
| 1 | Problem & user | 01-frame/3-FINAL | • Học viên AI20k mất ~15'/lần tìm lại concept cũ trong slide rời rạc; coach trả lời 30–50 câu lặp/tuần • Người đau nhất: 80 học viên track Product đang làm pilot plan, cần nối lại D2/D26/D27 | Hoàng Đức Nghĩa |
| 2 | Breakdown & Quick Win | 01-frame/1,2 | • Tách 8 use case, chọn 1: bot tra cứu "concept X ở đâu?" có citation • Không chọn: memory cá nhân (privacy), concept mapping (quá lớn), coach memory (phụ thuộc hệ thống) | Hoàng Đức Nghĩa |
| 3 | Solution + bản vẽ | 02-solution/2-FINAL | • Boost: RAG pipeline (GPT-4o-mini + Chroma + LangChain), ~$15–25/th • [Chiếu prompt flow: Input → Embed → Retrieve → Generate có citation → Instructor review] | Phạm Việt Anh |
| 4 | AI Pilot Plan | 03-pilot-plan/1 | • 4 tuần, 2 phase: P1 test 30 câu với instructor review → P2 mở 80 người • Budget: ~$15–25/th API + 60h nhóm + 12h instructor | Bùi Minh Ngọc |
| 5 | Metric · exit · **lời xin** | 03-pilot-plan/1 | • Đo: citation accuracy ≥85%, adoption ≥30%, giảm câu hỏi lặp ≥40% • Dừng nếu: hallucination ≥3 lần/tuần • **Xin**: truy cập tài liệu khóa + 12h instructor review + 1 Discord channel — **Hứa**: giao evidence accuracy + adoption sau 4 tuần, chấp nhận dừng nếu metric fail | Bùi Minh Ngọc |

## Phần B — Chuẩn bị 3 câu phản biện

Business owner/instructor sẽ hỏi mỗi nhóm 1–2 câu. Viết sẵn câu trả lời:

1. *"Số liệu / giả định này lấy ở đâu?"* → Số 30–50 câu hỏi lặp/tuần và ~15 phút/lần là **giả định** dựa trên quy mô ~500 học viên và hoạt động Discord hiện tại (đã đánh dấu 🧮). Phase 1 sẽ đo baseline thật trước khi mở rộng.
2. *"Nếu giả định quan trọng nhất của bạn sai thì sao?"* → Giả định chính: học viên thật sự cần tra cứu concept cũ. Nếu sai → adoption sẽ <15% → chạm exit criteria mức Cảnh báo → dừng mở rộng, pivot sang knowledge card hoặc concept mapping.
3. *"Tình huống nào sẽ khiến bạn dừng pilot?"* → (1) Hallucinated citation ≥3 lần/tuần → dừng ngay, ban vận hành quyết. (2) Lộ data ngoài kho công khai 1 lần → dừng ngay. (3) Citation accuracy <80% sau 2 tuần → dừng Phase 2, tối ưu lại.

## Phần C — AI Support Log

| Câu hỏi | Trả lời |
|---|---|
| AI giúp được gì trong lab này? | AI giúp dựng nhanh bảng use case, chấm điểm Quick Win, research 4 tầng (tìm Danswer/Notion AI/Perplexity làm tiền lệ), và dựng khung prompt flow cho bản vẽ trực quan. |
| AI đưa output nào nghe hợp lý nhưng nhóm phải sửa? | AI đưa điểm Quick Win scoring bằng số tròn (5/5/5/5 = 5.0) không dùng trọng số — nhóm phải tính lại theo công thức. AI cũng gợi ý pain evidence bằng số chung chung — nhóm phải đánh dấu rõ đâu là giả định (🧮). |
| Phần nào nhóm tự lập luận, KHÔNG copy AI? | Quyết định chọn Quick Win (retrieval có citation thay vì knowledge card hay concept mapping). Exit criteria 2 mức và việc gán quyền dừng cho Ban vận hành (không phải nhóm tự quyết). Adoption plan với fallback pivot sang Discord bot. |

---

## Tổng kiểm tra trước khi nộp

| Hạng mục | Xong? |
|---|---|
| 5 slide, mỗi slide 1 thông điệp, đã phân ai nói slide nào | ✅ (3 thành viên, phân rõ) |
| Slide 5 có lời xin rõ ràng (xin gì · hứa gì) | ✅ (xin tài liệu + 12h review + Discord channel; hứa evidence + chấp nhận dừng) |
| Có câu trả lời sẵn cho cả 3 câu phản biện | ✅ |
| AI Support Log điền đủ 3 dòng | ✅ |
| Tất cả file worksheet/ đã commit + push, link dán vào Discord | ⬜ Chưa (cần push sau khi xong) |

Đây là file cuối. Pitch 5 phút + nhận phản biện theo bảng 5 Gate (`templates/rubric-gate-sheet.md`).

*Liên quan: handbook §A9 · `templates/5-slide-pitch.md` · `templates/ai-support-log.md`*

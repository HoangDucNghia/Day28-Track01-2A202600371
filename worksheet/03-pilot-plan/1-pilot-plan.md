---
artifact: 7 — AI Pilot Plan core
bai-tap: Pilot Plan — cam kết hai chiều: xin – hứa – đo – dừng
phase: Double Diamond vòng 2 · ◇ giãn → ◆ siết (liệt kê hết rồi chốt gọn)
time: ~10 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 02-solution/2-FINAL-solution.md · 00-context.md · prompts/06-pilot-plan-challenge.md
nop-cuoi: Không — file trung gian (bản nộp ở 2-FINAL-pitch.md)
---

# 1 — AI Pilot Plan core

Mục tiêu: viết phần kế hoạch xin pilot — scope, người, data, budget, timeline, metric, exit criteria, adoption, lời hứa, lời xin. Bước này giãn ra (liệt kê hết những thứ cần) rồi siết lại (chốt bản gọn đủ để stakeholder quyết).

Lý do làm bước này: đây là thứ stakeholder dùng để **quyết approve hay dừng**. AI Pilot Plan **không phải proposal xin tiền** — là *cam kết hai chiều*: nhóm xin nguồn lực, đổi lại hứa giao evidence + chấp nhận dừng nếu metric fail. Demo đẹp mà không nói được "xin gì, hứa gì, đo gì, dừng khi nào" → trượt Gate 5.

Quy tắc: **budget tách từng hạng mục, không gộp 1 cục; không có mục "miscellaneous".** Exit criteria phải có người có quyền thực thi, không chỉ trên giấy.

## Quy trình 10 phút

```text
6 phút  — Điền 10 mục core (kéo nguyên liệu từ 00 + 01-frame + 02-solution)
3 phút  — Phần exit criteria + adoption (chỗ nhóm hay bỏ quên)
1 phút  — Tự phản biện
```

---

## 10 mục core

Câu hỏi phụ (tự trả lời):

- Nếu tóm vấn đề không gọn trong 1 câu → nhóm chưa hiểu vấn đề.
- Exit criteria của nhóm có ai DÁM thực thi khi sếp vẫn thích pilot không?
- Adoption: ai dùng đầu tiên — không phải "cả khóa ~500 người"?

### Trả lời

1. **Tóm vấn đề** (1 câu, từ Problem Framing): Học viên AI20k mất ~15 phút/lần để tìm lại concept/framework cũ trong hàng chục slide rời rạc, và coach phải trả lời 30–50 câu hỏi lặp/tuần kiểu "framework này học ngày nào?" — cần một bot tra cứu có citation.

2. **Cách làm + lý do** (từ 02-solution, 1 câu): **Boost** — dùng RAG pipeline (OpenAI/Gemini API + embedding + vector store + LangChain) trên tài liệu khóa học, không tự build vì bài này là productivity layer, không phải lợi thế cốt lõi.

3. **Scope pilot**: Phục vụ học viên track Product (~80 người) + coach/instructor hỗ trợ track này · Thời gian: 4 tuần (2 phase) · Phase 1 (tuần 1–2): index tài liệu D28 + test 30 câu mẫu với instructor review · Phase 2 (tuần 3–4): mở cho ~80 học viên dùng thật, đo adoption + accuracy.

4. **Người**:
   - Nhóm làm: Hoàng Đức Nghĩa (PM + setup pipeline), Phạm Việt Anh (chunking/indexing tài liệu), Bùi Minh Ngọc (test + đo metric)
   - Review output rủi ro cao: Instructor/TA (kiểm citation tuần đầu)
   - Quyền quyết approve/dừng: Ban vận hành AI20k / Product team Learning OS

5. **Data**: Tài liệu khóa học (slide, handbook, glossary, case bank, lab) — tất cả là tài liệu công khai của khóa, không dùng data cá nhân học viên. Cơ chế: mọi câu trả lời phải kèm citation; không có nguồn → nói "không biết".

6. **Budget** (tách hạng mục):

   | Hạng mục | Chi phí ước lượng / tháng | Ghi chú |
   |---|---|---|
   | API LLM (GPT-4o-mini hoặc Gemini) | $10–20 | Gemini free tier có thể dùng Phase 1 |
   | Embedding API | ~$1–2 | text-embedding-3-small, kho nhỏ |
   | Vector store (Chroma local / Pinecone free) | $0 | Free tier đủ 100K vectors |
   | Framework (LangChain/LlamaIndex) | $0 | Open-source |
   | Thời gian người: nhóm setup + test | ~20h/người × 3 = 60h | 4 tuần, mỗi người ~5h/tuần |
   | Thời gian người: Instructor/TA review | ~3h/tuần × 4 tuần = 12h | Review 30 câu tuần 1–2, spot-check tuần 3–4 |
   | Hạng mục ẩn: maintenance sau pilot | ~2h/tuần | Cập nhật tài liệu mới, fix chunk lỗi |
   | **Tổng chi phí API** | **~$15–25/tháng** | |

7. **Timeline + cổng giữa phase**:
   - **Phase 1 (tuần 1–2)**: Index tài liệu D28 (handbook, glossary, slide) → build RAG pipeline → test 30 câu mẫu → Instructor review
     - → **Cổng**: accuracy ≥80% trên 30 câu, không có hallucinated citation → qua Phase 2
   - **Phase 2 (tuần 3–4)**: Mở cho ~80 học viên dùng → đo adoption rate, accuracy thật, feedback
     - → **Cổng cuối**: quyết định tiếp tục (mở rộng) / dừng / pivot

8. **Metrics** (SMART + baseline + ngưỡng + ai đo):

| Metric | Đo bằng gì · ai đo | Baseline | Ngưỡng đạt |
|---|---|---|---|
| Citation accuracy | % câu trả lời có citation đúng nguồn · Instructor/TA chấm | 0% (chưa có tool) | ≥85% sau Phase 1 |
| Thời gian tìm tài liệu | Survey học viên: "bạn mất bao lâu tìm concept cũ?" · Nhóm khảo sát | 🧮 ~15 phút/lần (giả định) | Giảm xuống ≤5 phút/lần |
| Adoption rate | Số học viên dùng ít nhất 1 lần/tuần · Nhóm đo từ log | 0 (chưa có tool) | ≥30% của 80 người (≥24 người) sau Phase 2 |
| Số câu hỏi lặp cho coach | Đếm câu hỏi "framework/slide ở đâu?" trên Discord · Nhóm đếm thủ công | 🧮 ~30–50 câu/tuần (giả định) | Giảm ≥40% so với baseline |

   Leading indicator (biết kết quả sớm trong 1–2 tuần): Citation accuracy trên 30 câu mẫu Phase 1. Nếu <70% sau tuần 2 → cần tối ưu chunking/prompt trước khi mở rộng.

9. **Exit criteria** (định trước, ≥2 mức):

| Mức | Điều kiện | Hành động | Ai có quyền dừng |
|---|---|---|---|
| Cảnh báo | Citation accuracy <80% sau tuần 2 HOẶC adoption <15% sau tuần 4 | Dừng Phase 2, quay lại tối ưu chunking/prompt. Không mở rộng. | Nhóm pilot + Instructor |
| Nghiêm trọng | Hallucinated citation xảy ra ≥3 lần trong 1 tuần HOẶC lộ data không thuộc kho công khai 1 lần | Dừng pilot ngay lập tức. Báo cáo cho ban vận hành. | Ban vận hành AI20k (có quyền override dù nhóm muốn tiếp) |

   *Liên hệ 2 Red Flag ở `00-context.md`:*
   - Red Flag 1 (graph quá to, không ai bảo trì): → Chặn bằng scope nhỏ (chỉ retrieval, không build full graph) + có người bảo trì rõ ràng (nhóm pilot + TA).
   - Red Flag 2 (sai citation): → Chặn bằng exit criteria mức Nghiêm trọng (≥3 lần hallucination = dừng ngay).

10. **Adoption** (tool không ai dùng = $0):
    - **Ai dùng đầu tiên**: 80 học viên track Product đang làm lab/pilot plan sau D28.
    - **Workflow đổi ở đâu**: Thay vì search Discord/lục slide, học viên hỏi bot trước → nhận trả lời có citation → nếu đủ tin thì dùng luôn, nếu không thì lục slide như cũ.
    - **Ai train/support**: Nhóm pilot hướng dẫn nhanh 5 phút đầu tuần 3 + pin link bot trên Discord channel.
    - **Nếu không ai dùng**: Survey hỏi lý do (UX kém? không biết có tool? output không hữu ích?). Nếu adoption <15% sau 2 tuần dù output chính xác → vấn đề là adoption chứ không phải tech → pivot sang embedded trong workflow (ví dụ tích hợp vào Discord bot thay vì web riêng).

---

## Tự phản biện

- **Budget thiếu hạng mục ẩn nào không?** → Đã tính maintenance (2h/tuần cập nhật tài liệu). Có thể thiếu: chi phí nếu cần upgrade từ Gemini free sang paid khi rate limit không đủ.
- **Exit criteria đủ mạnh để THẬT SỰ dừng, hay chỉ trên giấy?** → Mức Nghiêm trọng do Ban vận hành quyết định (không phải nhóm pilot tự quyết), nên có người DÁM dừng.
- **Giả định quan trọng nhất sai → plan gì?** → Giả định chính: "học viên thật sự cần tra cứu concept cũ và hiện đang mất nhiều thời gian". Nếu sai → adoption sẽ thấp, có thể thấy ngay từ tuần 3–4 → pivot sang knowledge card hoặc concept mapping thay vì Q&A.

---

## Tổng kiểm tra trước khi sang `2-FINAL-pitch.md`

| Hạng mục | Xong? |
|---|---|
| Tóm vấn đề trong 1 câu | ✅ |
| Budget tách hạng mục, không "miscellaneous" | ✅ (7 hạng mục rõ ràng) |
| Metric có baseline + ngưỡng + ai đo | ✅ (4 metrics, có baseline + ngưỡng) |
| Exit criteria có người có quyền thực thi (≥2 mức) | ✅ (Ban vận hành có quyền override) |
| Adoption: chỉ rõ ai dùng đầu tiên (không "cả khóa") | ✅ (80 học viên track Product) |

⚑ Coach kiểm tra ở Mốc 4: *"Xin gì? Hứa gì? Đo gì? Dừng khi nào?"*

Sau bước này, mở `2-FINAL-pitch.md` — dồn tất cả thành 5-slide pitch + AI Support Log.

*Liên quan: handbook §A7+§A8 · `templates/ai-pilot-plan-core.md` · `prompts/06-pilot-plan-challenge.md`*

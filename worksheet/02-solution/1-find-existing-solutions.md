---
artifact: 5 — Solution Approach (phần khám phá)
bai-tap: Solution — tìm lời giải đã có sẵn trước khi tự xây
phase: Double Diamond vòng 2 · ◇ giãn (mở hết lựa chọn, chưa chốt)
time: ~8 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 01-frame/3-FINAL-problem-framing.md · 00-context.md · prompts/04-find-solutions.md
nop-cuoi: Không — file trung gian (bản chốt ở 2-FINAL-solution.md)
---

# 1 — Find existing solutions (đừng xây lại từ số 0)

Mục tiêu: trước khi quyết Build / Buy / Boost / Partner, nhóm phải biết bài này đã có ai giải ở chỗ khác chưa, và họ giải bằng cách nào. Đây là nửa "giãn ra" của [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) vòng 2 — mở hết các lời giải đang tồn tại, chưa chốt cái nào.

Lý do làm bước này: đây là chỗ nhiều nhóm hỏng mà không biết. Hỏng vì nhảy thẳng vào "tự build" cho oai, trong khi 80–90% nhu cầu nội bộ chỉ cần Boost hoặc Buy. Hỏng vì không hỏi "ai làm rồi" nên đi lại từ số 0. Gần như bài nào cũng đã có người giải ở một ngành khác — không thấy thì phí cả pilot.

Quy tắc: **không có nguồn = giả định.** Mỗi cái AI/web nói ra, hỏi lại "lấy ở đâu?". Không chỉ được nguồn thì đánh dấu 🧮 (giả định để giảng), đừng xài như fact.

## Bước 0 — Bài này thực ra là dạng bài gì? (2 phút)

Bỏ context AI20k sang một bên. Mô tả Quick Win của nhóm như một bài toán chung — không có chữ "học viên / coach / Discord". Vài ví dụ cho dễ hình dung:

- "câu hỏi của user → câu trả lời kèm nguồn" → đây là bài Q&A có citation
- "một đống văn bản lộn xộn → data có cấu trúc" → bài extraction
- "bài nộp → nhận xét theo rubric" → bài rubric grading

Dạng bài (the pattern) đó gần như chắc chắn đã có người làm ở ngành khác. Tìm ra dạng bài → tìm ra người đã giải nó.

- **Quick Win của nhóm, viết lại thành 1 dạng bài chung (không có chữ domain)**: Bài **Q&A có citation trên một kho tài liệu đóng** (closed-corpus retrieval-augmented QA)
- **Input → output thực chất là gì**: Câu hỏi bằng ngôn ngữ tự nhiên → Câu trả lời ngắn + dẫn nguồn cụ thể (tên tài liệu, slide/page). Nếu không tìm được nguồn → trả “không biết”.
- **Ràng buộc không bỏ được (lấy từ `00-context.md`)**: Citation bắt buộc · thiếu nguồn thì nói "không biết" · human review cho pilot đầu · budget nhỏ (dùng API/tool sẵn) · không dùng data cá nhân học viên

## Quy trình 8 phút

```text
2 phút  — Bước 0: gọi tên dạng bài
4 phút  — Phần A: deep research 4 tầng "ai giải dạng bài này rồi"
2 phút  — Phần B: rút về 2–3 hướng khả thi, đánh dấu nguồn
```

---

## Phần A — Deep research: ai giải dạng bài này rồi, giải sao?

Không phải gõ 1 câu vào AI rồi chép. Chạy 4 tầng, **tầng sau lấy kết quả tầng trước làm input**. Khung câu lệnh ở `prompts/04-find-solutions.md`.

Câu hỏi phụ (tự trả lời — viết ra cái nhóm *tìm thấy*, không phải cái nhóm *đoán*):

- Dạng bài này giống bài nào ở một ngành hoàn toàn khác?
- Hướng nào AI gợi ý mà nhóm **không kiểm được nguồn** — vậy có nên tin không?
- Một ca thất bại của người đi trước dạy nhóm tránh đúng điều gì?
- Nhóm "đi từ mức mấy" — kế thừa được gì để khỏi bắt đầu từ 0?

### Trả lời — điền theo 4 tầng

| Tầng | Hỏi AI/web câu gì | Tìm được gì | Nguồn / 🧮 nếu là giả định |
|---|---|---|---|
| 1 · Map | "Q&A có citation trên kho tài liệu đóng thường giải bằng hướng nào?" | (a) RAG pipeline (chunk + embed + retrieve + generate) · (b) Fine-tune model trên corpus · (c) Keyword search + re-rank · (d) SaaS sẵn có (Notion AI, Glean, Danswer) · (e) Hybrid: BM25 + semantic search. Hướng (a) và (e) phổ biến nhất cho kho tài liệu vừa và nhỏ. | LangChain docs · LlamaIndex docs · Pinecone blog |
| 2 · Tiền lệ | "Ai đã làm Q&A có citation trên tài liệu giáo dục/nội bộ?" | (1) **Notion AI Q&A** — search + answer từ workspace pages, có dẫn link nguồn. (2) **Danswer (open-source)** — enterprise Q&A với citation, dùng RAG + connector cho Slack/Confluence/Google Drive. (3) **Coursera/edX internal** — một số nền tảng học dùng Q&A bot trên course material với GPT + retrieval. (4) **Perplexity AI** — mô hình Q&A web có citation làm benchmark về UX trìdnh bày nguồn. | Danswer GitHub · Notion AI changelog · 🧮 Coursera internal (giả định từ báo cáo công nghệ, không có link trực tiếp) |
| 3 · Phản chứng | "Ca nào làm Q&A có citation thất bại?" | (1) Chatbot nội bộ bịa nguồn (hallucination) — nguyên nhân: chunk quá lớn, prompt không enforce citation, không có fallback "không biết". (2) Knowledge base quá to không ai bảo trì — tài liệu lỗi thời, retrieval ra kết quả sai. (3) User không tin vì citation dẫn tới file nhưng không chỉ được đoạn cụ thể. | 🧮 Tổng hợp từ nhiều bài viết về RAG failures (LangChain community, HN discussions) |
| 4 · Thu hẹp | "Với budget nhỏ, cần citation, có người review — hướng nào khả thi 6 tuần?" | **Boost** (model sẵn + data riêng) là hướng tối ưu: dùng OpenAI/Gemini API + embedding + vector store (Pinecone/Chroma) + LangChain/LlamaIndex. Không cần fine-tune. Chi phí: ~$20–50/tháng API. Build from scratch quá tốn. Buy (Danswer) khả thi nhưng cần self-host. | LangChain pricing · OpenAI API pricing · Pinecone free tier |

---

## Phần B — Rút về 2–3 hướng khả thi

Câu hỏi phụ:

- Hướng nào *kế thừa được nhiều nhất* từ người đã làm?
- Hướng nào nghe hay nhưng nhóm **không có nguồn** để tin?

### Trả lời

| Hướng giải khả thi | Ai làm rồi (gần bài mình nhất) | Nguồn / 🧮 | Hợp ràng buộc `00-context`? |
|---|---|---|---|
| **Boost**: RAG pipeline (OpenAI/Gemini + embedding + vector store + LangChain) | Danswer, Notion AI, Perplexity AI | Danswer GitHub, OpenAI docs | Có — budget nhỏ ($20–50/th), có citation built-in, dễ thêm human review |
| **Buy**: Danswer self-hosted (open-source enterprise Q&A) | Danswer (tự họ dùng cho nội bộ) | Danswer GitHub | Có điều kiện — cần server self-host, tốn setup ban đầu, nhưng free |
| **Build from scratch**: Tự xây model + indexing + UI | Không tìm thấy ai làm ở quy mô khóa học nhỏ | 🧮 | Không — quá tốn, quá chậm, không hợp budget nhỏ |

**"Đi từ 5 lên" — nhóm kế thừa cụ thể cái gì** (1–2 câu):

```text
Kế thừa kiến trúc RAG pipeline đã được chứng minh ở Danswer/Notion AI: chunk tài liệu → embed → vector store → retrieve top-k → generate có citation. Không cần nghiên cứu từ đầu — chỉ cần chọn đúng chunking strategy và prompt template cho bối cảnh tài liệu khóa học.
```

---

## Phát hiện ban đầu

Ghi nhanh 2–3 cái đáng chú ý nhất (chưa phải quyết định — quyết định ở file FINAL):

- **Boost là hướng rõ ràng nhất**: model sẵn (GPT-4o/Gemini) + data riêng (slide/handbook) + RAG pipeline. Không cần fine-tune, không cần build từ đầu.
- **Bài học từ ca thất bại**: hallucination và sai citation là rủi ro lớn nhất. Cần: (1) chunk nhỏ + metadata rõ, (2) prompt bắt buộc dẫn nguồn, (3) fallback "không biết" khi confidence thấp.
- **Danswer là plan B**: nếu Boost tự làm quá chậm, có thể dùng Danswer (open-source) để rút ngắn thời gian setup.

## Câu hỏi mở (mang sang bước chốt)

- Tài liệu khóa đang ở dạng gì? (Markdown / PDF / slides?) → quyết định chunking strategy.
- Nên dùng OpenAI API hay Gemini API? (giá, chất lượng tiếng Việt, rate limit)
- Citation nên ở mức nào: tên file + số trang, hay deep link tới đoạn cụ thể?

---

## Tổng kiểm tra trước khi sang `2-FINAL-solution.md`

| Hạng mục | Xong? |
|---|---|
| Gọi được dạng bài trong 1 câu, không còn chữ domain | ✅ (Q&A có citation trên kho tài liệu đóng) |
| Đủ 4 tầng deep research, tầng nào cũng có kết quả | ✅ |
| Mỗi kết quả có nguồn, hoặc đánh dấu 🧮 nếu là giả định | ✅ |
| Rút về 2–3 hướng + nói được "đi từ 5 lên" cái gì | ✅ (kế thừa RAG pipeline từ Danswer/Notion AI) |

Hàng nào chưa xong → quay lại Phần A, đừng sang bước chốt vội.

Sau bước này, mở `2-FINAL-solution.md` — chốt Build/Buy/Boost/Partner + data & ai review + bản vẽ trực quan (đây là bản nộp của phase này).

*Liên quan: handbook §A5 · `prompts/04-find-solutions.md` · `00-context.md`*

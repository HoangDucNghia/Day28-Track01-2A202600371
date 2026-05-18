---
artifact: 5 — Solution Approach + 6 — Demo/Mockup/Flow (bản nộp phase Solution)
bai-tap: Solution — chốt cách làm + cho stakeholder nhìn thấy
phase: Double Diamond vòng 2 · ◆ siết (chốt 1 cách làm + 1 artifact trực quan)
time: ~12 phút (xem deck để biết khung giờ chính xác trong buổi)
input: 1-find-existing-solutions.md · 00-context.md · templates/demo-examples.md · prompts/05-demo-challenge.md
nop-cuoi: Có — bản nộp của phase Solution (Part B + C · A3 mục Solution Approach + Demo/Mockup/Flow)
---

# 2 — FINAL: Solution Approach + Demo/Mockup/Flow

Mục tiêu: chốt cách làm cho Quick Win (Build / Buy / Boost / Partner), nói rõ data & ai review cần có, và tạo 1 bản vẽ trực quan để stakeholder *nhìn* được. Đây là nửa "siết lại" của [Double Diamond](https://www.thefountaininstitute.com/blog/what-is-the-double-diamond-design-process) vòng 2 và là bản nộp của phase Solution.

Lý do làm bước này: hai cái bẫy. Một, "tự build" cho oai — trong khi 80–90% nhu cầu nội bộ chỉ cần Boost/Buy; tự build là quyết định khó rút lại nhất. Hai, chỉ nói bằng chữ — stakeholder không duyệt một đoạn văn, họ duyệt khi *nhìn thấy* flow. Không có bản vẽ → trượt Gate 4 dù lập luận tốt.

Quy tắc: **bản vẽ trực quan là BẮT BUỘC; demo chạy được chỉ là điểm cộng.** *Demo đơn giản + lập luận chặt > demo đẹp + lập luận yếu.*

## Quy trình 12 phút

```text
4 phút  — Phần A: chốt Build/Buy/Boost/Partner (decision tree + ego check)
3 phút  — Phần B: data & ai review cần có
5 phút  — Phần C: vẽ 1 artifact trực quan + đánh dấu chỗ người review
```

---

## Phần A — Chốt cách làm

Đi decision tree, đừng chọn theo cảm giác:

```text
Bài này có phải LỢI THẾ CẠNH TRANH CỐT LÕI không?
 ├─ CÓ  → đội có AI engineer mạnh? CÓ → Build · KHÔNG → Boost
 └─ KHÔNG (chỉ là productivity layer) → có tool sẵn?
          CÓ → Buy · KHÔNG → Boost (model sẵn + data riêng)
```

Câu hỏi phụ:

- Nhóm chọn cách này vì *cần* hay vì *thích tự build*? Một câu thành thật.
- Hướng nào ở file `1` (đã tìm được người làm rồi) khớp với cách này — "đi từ 5 lên"?

### Trả lời

- **Cách làm chốt**: **Boost** (model sẵn + data riêng của khóa)
- **Lý do CẦN (không phải thích), 2–3 câu**: Bài này là Q&A có citation trên kho tài liệu đóng — dạng bài RAG đã có kiến trúc được chứng minh rộng rãi. Không cần tự train model vì model GPT-4o/Gemini đã hiểu tiếng Việt tốt. Chỉ cần ghép data riêng (slide, handbook, lab) vào pipeline retrieval là chạy được.
- **Vì sao KHÔNG "Build từ số 0"**: Budget nhỏ, không có AI engineer chuyên. Tự build model + indexing + UI sẽ mất nhiều tháng và không tạo lợi thế cạnh tranh cốt lõi — đây chỉ là productivity layer cho khóa học. Ego check: nhóm không cần tự build để chứng minh năng lực.
- **Tool / API / vendor cần + ước lượng chi phí thô**: OpenAI API (GPT-4o-mini, ~$10–20/th) hoặc Gemini API (free tier) · Embedding: text-embedding-3-small (~$0.02/1M tokens) · Vector store: Chroma (free, local) hoặc Pinecone (free tier 100K vectors) · Framework: LangChain/LlamaIndex (free) · Tổng: **~$20–50/tháng**

## Phần B — Data & ai review (cách làm này cần gì để chạy được)

| Cần gì | Có sẵn trong AI20k? | Trong lab dùng (mẫu/giả định) | Privacy? |
|---|---|---|---|
| Data: Slide skeleton + handbook D28 | Có — file .md trong repo | Dùng thật (tài liệu công khai của khóa) | Không nhạy cảm |
| Data: Instructor notes, case bank, framework | Có — trong LMS/Google Drive | Dùng mẫu 10–20 file đại diện | Không nhạy cảm (tài liệu khóa, không phải data học viên) |
| Data: Câu hỏi mẫu của học viên | Có — từ Discord/FAQ | Dùng 20–30 câu hỏi giả định dựa trên FAQ thật | Không dùng câu hỏi thật có tên học viên |

- **Output nào rủi ro cao** (sai gây hậu quả): Câu trả lời dẫn sai nguồn (hallucinated citation) → học viên học sai concept, mất trust ngay từ pilot đầu
- **Ai review + bao nhiêu mẫu + pass/fail theo gì**: Instructor/TA review 30 câu hỏi mẫu tuần đầu. Pass: citation đúng nguồn + trả lời đúng nội dung. Fail: bịa nguồn hoặc trả lời sai khái niệm. Ngưỡng: ≥85% câu trả lời đúng nguồn.
- **Có cần citation / nói "không biết" khi thiếu nguồn không**: **Có — bắt buộc**. Mọi câu trả lời phải kèm [Nguồn: tên file + đoạn]. Không tìm được nguồn → trả "Tôi không tìm thấy thông tin này trong tài liệu khóa."

## Phần C — Bản vẽ trực quan (BẮT BUỘC)

Chọn **2 dạng**: Prompt flow + Sample input/output.

### C1 — Prompt Flow (luồng xử lý)

```text
[INPUT: Học viên hỏi "Double Diamond được dạy ở ngày nào?"]
      │
      ▼
[B1: Embed câu hỏi → Tìm top-5 chunks trong vector store]
      │    ←←← (kho tài liệu: slide D2, D28 handbook, glossary...)
      ▼
[B2: Gửi top-5 chunks + câu hỏi vào GPT-4o-mini]
      │    Prompt: "Trả lời dựa TRÊN CÁC ĐOẠN sau. Dẫn nguồn.
      │             Nếu không tìm thấy → nói 'không biết'."
      ▼
[OUTPUT: "Double Diamond được giới thiệu ở Day 2 và nhắc lại ở Day 28.
          [Nguồn: glossary.md, mục Double Diamond]
          [Nguồn: d28-student-handbook.md, dòng 11]"]
      │
      ▼
[👤 INSTRUCTOR/TA REVIEW ← kiểm tra citation đúng không (tuần đầu pilot)]
      │
      ▼
[Nếu thiếu nguồn → "Tôi không tìm thấy trong tài liệu khóa."]
```

### C2 — Sample Input/Output (ví dụ thật)

```text
INPUT (câu hỏi mẫu từ học viên):
  "D28 dùng lại framework gì từ D26 và D27?"

OUTPUT mong muốn:
  "D28 dùng lại:
   - Từ D26: Phán đoán sản phẩm (Product Judgment) để chọn Quick Win đáng làm.
   - Từ D27: Kinh tế sản phẩm AI (cost, ROI, baseline) để dựng budget + metric
     trong AI Pilot Plan.
   [Nguồn: d28-student-handbook.md, mục 'Liên kết với Day 26 / Day 27']"

Vì sao ví dụ này thuyết phục: đây là câu hỏi thật mà học viên đang gặp khi làm
  lab D28. Output có nguồn cụ thể, không bịa.

Input sẽ làm tool LỘ ĐIỂM YẾu: "Cho tôi bài mẫu của nhóm khác" → tool phải
  trả "không tìm thấy" vì không có bài nộp trong kho tài liệu.
```

Chỗ con người review (output rủi ro cao) nằm ở: **Sau bước output, trước khi deploy rộng** — Instructor/TA kiểm tra 30 câu mẫu tuần đầu. Sau khi accuracy ≥85%, chuyển sang spot-check 10 câu/tuần.

Câu hỏi phụ — một người đóng vai stakeholder nhìn 20 giây: *hiểu user làm gì, nhận lại gì, không cần giải thích thêm không? Có chỗ nào "đẹp nhưng rỗng" không?*

---

## Tổng kiểm tra trước khi sang `../03-pilot-plan/`

| Hạng mục | Xong? |
|---|---|
| Cách làm có lý do CẦN, không phải "mặc định tự build" | ✅ (Boost — có decision tree + ego check) |
| Nói rõ data cần + ai review output rủi ro cao | ✅ (3 loại data + Instructor/TA review 30 câu) |
| Có ≥1 bản vẽ trực quan, người ngoài hiểu trong ~20 giây | ✅ (Prompt flow + Sample I/O) |
| Có đánh dấu chỗ con người review | ✅ (Instructor/TA review sau output) |

⚑ Coach kiểm tra ở Mốc 3: *"Stakeholder nhìn vào đâu để hiểu flow? Mockup/sketch/demo đâu?"* Chỉ nói bằng chữ = chưa qua.

Sau bước này, mở `../03-pilot-plan/1-pilot-plan.md`.

*Liên quan: handbook §A5+§A6 · `templates/demo-examples.md` · `prompts/05-demo-challenge.md`*

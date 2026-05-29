# 02 — Group Problem Statement

## Group convergence

Nhóm 3-4 người, mỗi người share top 3. Tổng cộng khoảng 9-12 candidates.

| # | Người đưa ra | Candidate problem | Người gặp vấn đề | Điểm nghẽn |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Tiến | Sinh viên học nhiều nhưng không biết học gì để đáp ứng nhu cầu JD | Sinh viên | Không có cơ chế nào giúp sinh viên đối chiếu bản thân với JD thật |
| 2 | Minh Anh | Họp daily tốn thời gian | Nhân viên, PM | Trùng lặp thông tin hàng ngày, cuộc họp hỗn loạn, không theo cấu trúc, dễ bị miss các chi tiết trong buổi họp |
| 3 | Đăng | Giáo viên IELTS chấm bài mất thời gian | Giáo viên | Chấm bài và feedback riêng tốn thời gian |
| 4 | Minh Anh | Tổng hợp tài liệu từ các công ty | Nhân viên, PM | Các công ty lưu trữ các tài liệu không theo tổ chức, khó tiếp cận với nhân viên mới |
| 5 | Đăng | Tìm kiếm & so sánh sản phẩm TMĐT | Người tiêu dùng | Lựa chọn sản phẩm, tìm kiếm deal hời từ các sàn mất thời gian |
| 6 | Minh Anh | Điểm nghẽn trong quy trình vận hành và bàn giao | Nhân viên dev | Reviewer quá bận + hoặc trì hoãn + nhiều lỗi convention, thiếu test case, hoặc sai logic cơ bản mà đáng lẽ phải phát hiện từ sớm. |
| 7 | Đăng | TA túc trực ngoài giờ | Học viên làm dự án | TA không thể đồng hành cùng HV 24/7 |
| 8 | Tiến | Sinh viên làm nhiều project nhưng không ghi lại quá trình ra quyết định -> không kể được trong phòng vấn kỹ thuật, bị loại dù đã làm thật. | Sinh viên chuẩn bị phỏng vấn | Không có evidence để kể (mỗi lần phỏng vấn mất 2-4 giờ ôn lại từ đầu) |
| 9 | Tiến | Mentor, TA mất 1-2 tiếng/tuần trả lời cùng bộ câu hỏi từ nhiều sinh viên: "em nên học gì tiếp?", "project này có đủ không?" | Mentor, TA, Senior | Mentor trả lời từng người thủ công (1-2 tiếng/tuần) |

## Shortlist và score

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Sinh viên học nhiều nhưng không biết học gì để đáp ứng nhu cầu JD | 5 | 4 | 5 | 4 | 4 | 5 | 3 | 30 |
| Tổng hợp nội dung họp daily/standup + action items + sync tiến độ sprint | 5 | 3 | 5 | 4 | 4 | 3 | 5 | 29 |
| Giáo viên IELTS chấm bài mất thời gian | 5 | 4 | 5 | 4 | 4 | 4 | 5 | 31 |


Nhóm chọn: **IELTS Writing Scoring**.

Vì sao chọn:

- Workflow rõ ràng và không phức tạp
- Impact to
- Có nhiều benchmark/ mẫu criteria đánh giá chính thức (Các đầu điểm đánh giá bài Writing )


## Research giải pháp

| Nguồn tool/ case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống/ rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Grammarly for Education | https://www.grammarly.com/edu | Phát hiện lỗi ngữ pháp, style, clarity | Tốt cho GRA criterion; auto-highlight lỗi | Không chấm theo IELTS band descriptor; không đánh giá CC hay TA | Tốt để làm pre-check trước khi giáo viên chấm; giảm tải bước phân loại lỗi GRA |
| Turnitin / Feedback Studio | https://www.turnitin.com/products/feedback-studio | Comment inline trên bài, reusable comment bank | Giáo viên tạo comment bank $\rightarrow$ tái sử dụng câu nhận xét thường gặp | Không AI-generated; giáo viên vẫn phải chọn và điền; không specific cho IELTS | Pattern tốt: comment bank là Rule đúng hướng — AI có thể làm tốt hơn bằng cách auto-suggest comment |
| Khanmigo (Khan Academy AI) | https://www.khanacademy.org/khan-labs | AI tutor phản hồi bài viết học sinh realtime | Fast feedback loop; học sinh nhận gợi ý ngay | Không theo IELTS rubric; không thay giáo viên; designed for K-12 | Pattern quan trọng: AI pre-feedback tức thì $\rightarrow$ học sinh review $\rightarrow$ giáo viên final. |
| IELTS.org AI Writing Feedback | https://ielts.org/take-a-test/ielts-ai-writing-feedback | Chấm writing tự động theo band descriptor chính thức | Official source, aligned với band descriptor thật \| Không có giáo viên review; học viên dùng trực tiếp $\rightarrow$ trust thấp hơn; không | Không có giáo viên review; học viên dùng trực tiếp $\rightarrow$ trust thấp hơn; không personalised | AI chấm có thể làm được — nhưng pattern đúng là AI draft + human review, không phải AI only |

Research takeaway:

```text
Thay vì thay thế con người, Pattern thành công của Khanmigo là "AI Draft + Human Review". Việc đưa AI vào làm Pre-feedback tức thì giúp tạo vòng lặp học tập nhanh (Fast feedback loop) cho học sinh mà không làm tăng tải cho giáo viên. Đây là lõi workflow mà nhóm cần áp dụng để cân bằng giữa Tốc độ (AI) và Chất lượng (Human)
```

## Workflow before/after

Nội dung workflow:

```text
CURRENT STATE — 4 bước, 30 phút

┌───────────────────────────────────┐
│ 1. Đọc toàn bộ bài                		      │  ~5–10 phút
│    Nắm ý tưởng, cấu trúc                          │  ← BOTTLENECK
└──────────────────┬────────────────┘
                                    │
                                    ▼
┌───────────────────────────────────┐
│ 2. Chấm 4 tiêu chí                                    │  ~10–15 phút
│    TA / CC / LR / GRA                                │  ← BOTTLENECK
└──────────────────┬────────────────┘
                                    │
                                   ▼
┌───────────────────────────────────┐
│ 3. Viết nhận xét thủ công                         │  ~10–15 phút
│    Từng lỗi, từng tiêu chí                           │  ← BOTTLENECK
└──────────────────┬────────────────┘
                                    │
                                   ▼
┌───────────────────────────────────┐
│ 4. Soát lỗi & kiểm tra nhất quán              │  ~5 phút
└──────────────────┬────────────────┘
                                    │
                                   ▼
                          Gửi feedback

────────────────────────────────────────
  Tổng: ~30 phút/bài
  50 bài = ~25 giờ công
────────────────────────────────────────

FUTURE STATE — 5 bước, 5 phút

Input prompt và essay
        │
        ▼
┌───────────────────────────────────┐
│ 0. AI phân tích đề bài            │  ~5 giây
│    Loại đề, yêu cầu, từ khóa     │  ✦ Tự động
└──────────────────┬────────────────┘
                   │
                   ▼
┌───────────────────────────────────┐
│ 1. AI phân tích bài viết          │  ~5 giây
│    Cấu trúc, ý tưởng, lập luận   │  ✦ Tự động
└──────────────────┬────────────────┘
                   │
                   ▼
┌───────────────────────────────────┐
│ 2. AI đối chiếu bài với đề        │  ~5 giây
│    Bài có trả lời đúng câu hỏi?  │  ✦ Tự động
└──────────────────┬────────────────┘
                   │
                   ▼
┌───────────────────────────────────┐
│ 3. AI chấm 4 tiêu chí            │  ~5 giây
│    TA / CC / LR / GRA             │  ✦ Tự động
└──────────────────┬────────────────┘
                   │
                   ▼
┌───────────────────────────────────┐
│ 4. AI draft nhận xét              │  ~5 giây
│    Từng lỗi, từng tiêu chí       │  ✦ Tự động
└──────────────────┬────────────────┘
                   │
                   ▼
┌───────────────────────────────────┐
│ 5. Giáo viên review & chỉnh sửa  │  ~3–5 phút
│    Đảm bảo chất lượng & gửi      │  ← Vẫn cần người
└──────────────────┬────────────────┘
                   │
                   ▼
            Gửi feedback
────────────────────────────────────────
  Tổng: ~5 phút/bài
  50 bài = ~4 giờ công
  Tiết kiệm: ~84%
────────────────────────────────────────
```

Before/after impact:

## Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** | Giáo viên IELTS chịu trách nhiệm chấm bài writing và trả feedback cho học viên sau mỗi buổi học. Học viên cần tự đánh giá bài viết dựa trên feedback này. |
| **Workflow** | Đọc toàn bài $\rightarrow$ nắm cấu trúc (~5-10 phút) $\rightarrow$ chấm 4 tiêu chí TA/CC/LR/GRA (~10-15 phút) $\rightarrow$ viết nhận xét thủ công từng lỗi (~10-15 phút) $\rightarrow$ soát lại lỗi chính tả, ngữ pháp (~5 phút) $\rightarrow$ gửi feedback. |
| **Bottleneck** | Bước chấm điểm và viết feedback chi tiết cho từng tiêu chí (narrative feedback) từ đầu tốn khoảng 20-25 phút/bài. |
| **Impact** | Mất 30 phút/bài $\times$ 5–10 học viên = 150–300 phút chấm thủ công mỗi tuần. Gây overload cho giáo viên và làm chậm tiến độ feedback, khiến học viên mất "thời điểm vàng" để tiếp thu lỗi sai ngay sau khi viết. |
| **Success Metric** | Giảm tổng thời gian chấm từ 30 phút xuống dưới 10 phút/bài (mục tiêu kỳ vọng ~5 phút/bài). Đảm bảo tỷ lệ chính xác cao; giáo viên chỉ cần review và chỉnh sửa nhỏ thay vì viết từ đầu; không tăng tỷ lệ feedback sai hoặc bị hỏi lại. |
| **Non-AI alternative** | Sử dụng Rubric chấm chuẩn hóa + Google Form tự động tổng hợp điểm. Cách này giảm được thời gian chấm (bước 2) nhưng thất bại ở bước viết nhận xét narrative (bước 3) vì vẫn đòi hỏi giáo viên phải đọc hiểu và tự diễn đạt bằng lời. |
| **AI Hypothesis** | AI chấm điểm tự động theo 4 tiêu chí TA/CC/LR/GRA và tự động draft sẵn phần nhận xét chi tiết cho từng lỗi. Giáo viên đóng vai trò kiểm duyệt, chỉnh sửa bản nháp này trước khi gửi. |
| **Boundary** | AI không tự gửi feedback, không tự quyết định điểm cuối cùng, và không thay thế hoàn toàn giáo viên trong bước approve (phê duyệt) kết quả trước khi trả bài cho học viên. |
| **AI intervention point** | Sau khi giáo viên đọc xong bài viết của học sinh và có ý định chấm $\rightarrow$ AI lập tức can thiệp để nhảy vào draft sẵn điểm số theo 4 tiêu chí cùng toàn bộ phần nhận xét chi tiết. Giáo viên chỉ cần đọc lại và tinh chỉnh. |
| **Mức chọn (Quick Gut)** | **Workflow**: Lựa chọn giải pháp tối ưu là xây dựng một quy trình Workflow tự động (AI draft scoring + narrative feedback) kết hợp với con người kiểm duyệt (Human-in-the-loop: giáo viên review và edit trước khi gửi), thay vì dùng Agent tự trị hoàn toàn để tránh rủi ro mất an toàn thông tin hoặc sai lệch kiến thức. |
| **Rủi ro & người thật kiểm** | • **Rủi ro:** AI chấm lệch band ở các bài viết có cấu trúc lập luận phức tạp, văn phong không chuẩn mực; feedback bị rập khuôn, thiếu cá nhân hóa theo trình độ thực tế của từng học viên; giáo viên bị lười hoặc quá phụ thuộc vào AI dẫn đến bỏ qua bước đọc bài.<br>• **Người thật kiểm tra:** Giáo viên bắt buộc phải đọc lại toàn bộ bài viết, đối chiếu với feedback do AI draft, xác nhận lại điểm số cuối cùng trước khi gửi bài. Tuyệt đối không gửi thẳng output của AI cho học viên. |

## Rule / Workflow / Agent

| Mức | Phương án | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| Rule | Rule-base để chia đoạn, tìm lỗi sai ngữ pháp, đếm từ | Đủ nếu teacher chỉ cần soát lỗi nhỏ, còn lại tự chấm | Chưa giải quyết được vấn đề thời gian | Không chọn |
| Workflow | Phân tích đề bài -> phân tích essay -> chấm theo từng tiêu chí -> viết lỗi, feedback -> teacher review | Hợp lý vì cấu trúc chấm bài IELTS đã theo một nguyên tắc các rubric rõ ràng | Chấm bài sai, feedback cứng nhắc | Chọn |
| Agent | Agent tự phân tích, chấm bài, hỏi ý teacher | Nếu cần thêm nhiều tool để feedback hay tạo bài tập cho học viên | Rộng so với một bài lab | Chưa |

**Mức chọn:**

```text
Workflow.
```

## Problem Statement v1

| Field | Nội dung |
|---|---|
| **Actor** | Giáo viên IELTS chịu trách nhiệm chấm bài writing và trả feedback cho học viên sau mỗi buổi học. |
| **Workflow** | Đọc toàn bài $\rightarrow$ nắm cấu trúc $\rightarrow$ chấm 4 tiêu chí TA/CC/LR/GRA $\rightarrow$ viết nhận xét thủ công từng lỗi $\rightarrow$ soát lại $\rightarrow$ gửi feedback. |
| **Bottleneck** | Viết nhận xét narrative từng tiêu chí từ đầu mất 20–25 phút |
| **Impact** | 30 phút/bài $\times$ 5–10 học viên = 150–300 phút chấm thủ công mỗi tuần; feedback trễ khiến học viên mất thời điểm vàng để tiếp thu lỗi sai ngay sau khi viết. |
| **Success Metric** | Giảm tổng thời gian từ 30 phút xuống dưới 10 phút/bài; không tăng tỷ lệ feedback sai hoặc bị học viên hỏi lại; giáo viên chỉ cần review và chỉnh sửa nhỏ thay vì viết từ đầu. |
| **Boundary** | AI không tự gửi feedback, không tự quyết định điểm cuối, không thay giáo viên trong việc approve kết quả trước khi trả cho học viên. |
| **AI intervention point** | Sau khi giáo viên đọc xong bài và có ý định chấm -> AI nhảy vào draft sẵn điểm 4 tiêu chí và toàn bộ phần nhận xét, giáo viên chỉ còn việc đọc lại và chỉnh. |
| **Mức chọn** | Workflow: AI draft scoring + narrative feedback, giáo viên review và edit trước khi gửi. |
| **Rủi ro & người thật kiểm** | AI chấm lệch band ở bài có lập luận phức tạp hoặc văn phong không chuẩn mực; feedback thiếu cá nhân hóa theo trình độ học viên; giáo viên quen dựa vào AI mà bỏ qua bước đọc bài. Người thật kiểm tra: giáo viên phải đọc lại toàn bộ feedback và xác nhận điểm trước khi gửi - không được gửi thẳng output của AI. |

## Final decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú |
|---|---|---|
| Actor và workflow đã rõ chưa? | Yes | Giáo viên IELTS là actor chính, workflow 5 bước đã được map rõ, AI intervention point xác định cụ thể |
| Baseline và success metric đã đo được chưa? | Yes | Baseline: 30 phút/bài. Target: dưới 10 phút/bài. Metric đo được bằng thời gian thực tế |
| Có data/input đủ dùng chưa? | Yes | Có sẵn dataset trên Huggingface |
| Nếu AI sai, hậu quả có chấp nhận được không? | Yes | Giáo viên vẫn review trước khi gửi - AI sai thì giáo viên sửa, không ảnh hưởng trực tiếp đến học viên |
| Có người review/owner vận hành không? | Yes | Giáo viên là người review bắt buộc trong workflow, không có bước nào AI tự gửi |
| Có cách non-AI đơn giản hơn không? | No | |

Decision:

```text
Go với scope nhỏ.
```

- Lý do: Hầu hết điều kiện đã đủ. Actor rõ, workflow rõ, metric đo được, rủi ro được kiểm soát bởi human-in-the-loop
- Nếu Go, pilot nhỏ nhất là: Lấy 10 bài IELTS Writing Task 2 đã có điểm thật từ giáo viên → chạy AI chấm và draft feedback → giáo viên so sánh output AI với feedback tự viết → đo thời gian tiết kiệm và tỷ lệ chỉnh sửa. 
- Nếu giáo viên chỉnh sửa dưới 30% nội dung AI tạo ra → xác nhận hypothesis, tiến sang build MVP.
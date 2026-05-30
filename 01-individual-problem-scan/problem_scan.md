# 01 — Individual Problem Scan

## Scan rộng

Minh scan 8 problems, vượt mức tối thiểu 5.

| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Lặp lại, tốn thời gian | Họp daily report và cập nhật đầu việc dài dòng | PM, Dev và các team liên quan | Mất khoảng 30 phút – 1 giờ mỗi ngày chỉ để sync tiến độ |
| 2 | Tốn thời gian | Viết meeting note, planning và chỉnh timetable sau mỗi buổi họp | PM | Sau mỗi buổi họp cần thêm 10–20 phút tổng hợp thủ công |
| 3 | Tốn thời gian | Tài liệu nghiệp vụ / dự án phân tán, khó tìm kiếm | Dev và các team liên quan | Có khi mất cả buổi chỉ để tìm đúng tài liệu hoặc version mới nhất |
| 4 | Pain | Trao đổi thông tin giữa các phòng ban chưa đồng bộ | Dev, PM và các team liên quan | Chỉ cần lệch giờ họp hoặc nghỉ phép là dễ mất context → delay sprint hoặc phải OT |
| 5 | Quá tải thông tin | Notification và nội dung chat quá dài | Dev và các team liên quan | Thông tin quan trọng dễ bị trôi giữa hàng trăm tin nhắn và nhiều group chat |
| 6 | Chất lượng thông tin | Tài liệu bị outdated hoặc thiếu cập nhật | Dev và các team liên quan | Dễ hiểu sai requirement → gây rework, tốn resource và bị complain từ Tech Lead / khách hàng |
| 7 | Điểm nghẽn quy trình | Review và bàn giao phụ thuộc quá nhiều vào reviewer | Reviewer, Dev | Reviewer quá bận hoặc review chậm; nhiều lỗi convention, thiếu test case, sai logic cơ bản không được phát hiện sớm |
| 8 | AI làm tốt hơn | Tổng hợp nội dung họp và tạo action items | PM, Dev | Sau họp vẫn phải tự note lại task, owner và deadline bằng tay |
| 9 | AI làm tốt hơn | Tóm tắt tài liệu kỹ thuật hoặc requirement dài | Dev, QA, BA | Mất nhiều thời gian đọc hàng chục trang tài liệu để nắm ý chính |
| 10 | AI làm tốt hơn | Theo dõi tiến độ sprint và cảnh báo risk | PM | Deadline hoặc blocker thường chỉ được phát hiện khi đã gần trễ |

## Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
| :---: | :--- | :--- | :--- |
| 1 | Tổng hợp nội dung họp daily/standup + action items + sync tiến độ sprint | Frequency rất cao, xảy ra hằng ngày; PM/Dev mất nhiều thời gian manual note và update. | AI có extract đúng owner/deadline/context không? Có đủ tin tưởng để dùng trong workflow thật không? |
| 2 | Tìm kiếm & tóm tắt tài liệu nội bộ phân tán | Pain phổ biến ở mọi team kỹ thuật nhưng chưa được giải quyết triệt để. | Retrieval có chính xác không? Tài liệu outdated/version conflict xử lý thế nào? |
| 3 | Review và bàn giao phụ thuộc quá nhiều vào reviewer | Reviewer thường quá tải hoặc review chậm; nhiều lỗi convention, thiếu test case, sai logic cơ bản lọt qua. | AI có hiểu đủ context/codebase để review hữu ích không? Dev có tin tưởng đề xuất từ AI không? |

## Problem Card #1 — Daily standup synthesis & action item tracking

**Problem 1 câu:**
Mỗi ngày PM và Dev mất 30–60 phút chỉ để tranh luận và đồng bộ tiến độ sprint, manual note action items, và update lại vào Jira/Notion, xem xét nếu tiến độ hiện tại kịp golive đợt tới -> những process lặp đi lặp lại mà không có giá trị thêm.

**Actor:**
PM, Dev (toàn bộ team sprint)

**Thời điểm / bối cảnh:**
Hằng ngày, đầu giờ sáng, chiều hoặc cuối ngày + bối cảnh standup/sync định kỳ trong sprint Agile.

**Current workflow:**

```text
1. Mở meeting (Zoom/Meet/huddle)
2. Từng người đọc update: hôm qua làm gì, hôm nay làm gì, blocker
3. PM mental-note hoặc ghi tay action items
4. Sau meeting: PM manually type lại vào Jira comment / Notion / Slack
5. Gửi recap lên channel
6. Check lại cuối ngày xem ai done chưa
```

**Bottleneck:**
Không có structured capture trong lúc meeting → PM phải dành 10–20 phút sau meeting để viết lại recap + update ticket. Thông tin dễ bị miss hoặc sai owner/deadline. Việc sync tiến độ tốn nhiều cognitive load không cần thiết + Vị trí sắp xếp tài liệu hỗn loạn.

**Impact:**
30–60 phút/ngày × số ngày sprint = 300–600 phút/sprint bị dùng cho coordination thuần túy. Action items bị miss hoặc trễ vì thiếu structured tracking.

**Success metric:**
Rút thời gian standup + post-meeting update xuống dưới 15 phút/ngày. Action items được capture đầy đủ, đúng owner, visible ngay sau meeting mà không cần PM manual type.

**Non-AI alternative:**
Standup template cố định (what I did / doing / blocked) + bot tự động remind. Giảm được phần format, nhưng vẫn không giải quyết capture & sync tự động.

**AI hypothesis:**
AI transcribe + extract structured output từ meeting audio/transcript: ai nói gì, blocker là gì, action item là gì, owner là ai, deadline là bao giờ. Sau đó auto-push vào Jira/Notion/Slack recap. PM chỉ cần review 2 phút.

**Quick gut:**
Workflow —> nhưng cần validate xem AI extract đúng owner/deadline/context không, và team có trust output đủ để không re-check manually không.

### Draft current

```text
CURRENT STATE — 30–60 phút/ngày

[1 Mở meeting: 5']
→ [2 Từng người đọc update: 15–25']
→ [3 PM mental-note / ghi tay action items: 5–10']  <-- dễ miss, sai owner
→ [4 Sau meeting: PM manually type recap + update Jira/Notion: 10–20']  <-- bottleneck
→ [5 Gửi recap lên Slack channel: 5']
→ [6 Check lại cuối ngày xem ai done chưa: 5–10']
```

### Draft future workflow

```text
FUTURE STATE — 10–20 phút/ngày

[1 Meeting diễn ra bình thường: 15–20']
→ [2 AI transcribe + extract structured output: 1']  <-- owner, deadline, blocker, action item
→ [3 AI auto-generate recap + push lên Slack: 1']
→ [4 PM review + sửa nếu cần: 3–5']  <-- human boundary
→ [5 AI (hoặc PM) update ticket Jira/Notion: 2']

Fallback: AI có khả năng sẽ extract sai owner/context → PM vẫn phải mất thời gian tự điền lại trước khi gửi.
-> Workflow Hiện tại chưa được tối ưu nhưng thời gian đã giảm được khoảng ~30%
```

## Problem Card #2 — Tìm kiếm & tóm tắt tài liệu nội bộ phân tán

**Problem 1 câu:**
Dev và PM mất nhiều thời gian tìm kiếm tài liệu nội bộ nằm rải rác trên Notion, Confluence, Google Drive, Slack, đặc biệt là những nhân viên mới onboard không biết tài liệu nào đúng, mới nhất, hay còn được dùng.

**Actor:**
Dev (onboarding, debug, implementation reference), PM (spec lookup, decision history), toàn bộ team kỹ thuật

**Thời điểm / bối cảnh:**
Xảy ra liên tục trong ngày. Mỗi khi cần tra cứu spec, API doc, quyết định thiết kế cũ, hoặc onboard thành viên mới vào codebase/product context.

**Current workflow:**

```text
1. Nhớ tài liệu cần tìm nằm ở đâu (Notion? Drive? Confluence?)
2. Search thủ công từng platform với keyword
3. Mở 3–5 kết quả, đọc lướt để tìm đúng cái cần
4. Không chắc bản đang đọc có phải bản mới nhất không
5. Hỏi teammate "cái này còn dùng không?" hoặc "link đúng ở đâu?"
6. Teammate mất thêm thời gian trả lời hoặc tìm lại hộ
```

**Bottleneck:**
Tài liệu phân tán nhiều nơi, không có single source of truth → tìm đúng tài liệu mất 10–20 phút/lần. Không có signal nào cho biết tài liệu đã outdated hay deprecated. Chi phí ẩn lớn nhất là interrupt teammate để hỏi lại.

**Impact:**
Ước tính 2–4 lần tra cứu/ngày × 10–20 phút = 20–80 phút/người/ngày. Với team 5–10 người, đây là 100–800 phút/ngày bị mất vào coordination và context-switching. Onboarding kéo dài thêm 1–2 tuần vì tài liệu khó tìm.

**Success metric:**
Thời gian tìm đúng tài liệu cần giảm xuống dưới 2 phút. Giảm số lần interrupt teammate để hỏi "tài liệu này còn dùng không". Độ chính xác retrieval đạt trên 80% (đúng tài liệu, đúng version).

**Non-AI alternative:**
Quy ước đặt tên + tag tài liệu chặt chẽ hơn, định kỳ audit và archive tài liệu cũ, dùng một platform duy nhất. Giảm được entropy nhưng tốn effort duy trì cao và thường bị bỏ qua sau vài tuần.

**AI hypothesis:**
AI index toàn bộ tài liệu nội bộ (Notion, Drive, Confluence, Slack) và cung cấp semantic search + summarization. User hỏi bằng ngôn ngữ tự nhiên, AI trả về đoạn trích liên quan kèm link gốc và metadata (last updated, author). Có thể flag tài liệu có dấu hiệu outdated dựa trên ngày chỉnh sửa hoặc conflict với tài liệu khác.

**Quick gut:**
Workflow —> nhưng độ khó implementation cao hơn Problem #1 do phụ thuộc vào chất lượng tài liệu đầu vào và cần giải quyết version conflict trước khi retrieval mới thực sự hữu ích.

## Problem Card #3 — Review & bàn giao phụ thuộc quá nhiều vào reviewer
 
**Problem 1 câu:**
Code review bị bottleneck bởi reviewer quá tải hoặc tự delay do các vấn đề phát sinh khiến PR nằm chờ 1–2 ngày, lỗi convention và thiếu test case vẫn lọt qua, và bàn giao giữa các Dev mất nhiều thời gian giải thích context.
 
**Actor:**
Dev (author PR), Senior Dev / Tech Lead (reviewer), PM (theo dõi tiến độ bị block)
 
**Thời điểm / bối cảnh:**
Cuối mỗi task hoặc feature, thời điểm khi Dev mở PR và chờ review trước khi merge. Cũng xảy ra khi bàn giao task giữa các thành viên trong sprint.
 
**Current workflow:**
 
```text
1. Dev hoàn thành code, mở PR trên GitHub/GitLab
2. Tag reviewer (thường 1–2 Senior Dev hoặc Tech Lead)
3. Reviewer nhận notification nhưng đang bận → PR nằm chờ
4. Dev ping lại trên Slack sau 1–2 ngày
5. Reviewer review nhanh vì áp lực → miss lỗi logic hoặc convention
6. Comment qua lại nhiều round → kéo dài merge
7. Khi bàn giao: Dev author giải thích miệng hoặc viết thêm doc ad-hoc
```
 
**Bottleneck:**
Review tập trung vào 1–2 người → single point of failure. Reviewer không đủ thời gian đọc kỹ từng PR → review chất lượng thấp hoặc trễ. Không có pre-check tự động trước khi PR đến tay reviewer → reviewer phải xử lý cả lỗi cơ bản lẫn lỗi logic.
 
**Impact:**
PR chờ review trung bình 1–2 ngày/round × 2–3 round = 2–6 ngày/feature bị delay chỉ vì bottleneck review. Lỗi lọt qua review dẫn đến bug production hoặc technical debt. Bàn giao kém làm thành viên mới mất 2–4 giờ để hiểu context một task.
 
**Success metric:**
Giảm thời gian chờ review xuống dưới 4 giờ cho lỗi cơ bản (convention, missing test, obvious logic error). Giảm số round comment qua lại từ trung bình 3 xuống còn 1–2. Reviewer chỉ cần focus vào logic và architecture, không phải style hay boilerplate.
 
**Non-AI alternative:**
Linter + CI pipeline tự động (ESLint, Prettier, pre-commit hooks) bắt được convention. Checklist PR template bắt buộc author tự review trước. Rotation reviewer để giảm tải. Giải quyết được phần format nhưng không giải quyết được logic review và context bàn giao.
 
**AI hypothesis:**
AI đọc diff của PR, đối chiếu với codebase hiện tại, và tự động comment: lỗi convention còn sót, thiếu test case nào, đoạn logic nào có risk, pattern nào không nhất quán với phần còn lại của codebase. Reviewer nhận được PR đã được pre-filter → chỉ cần focus vào judgment call. AI cũng tự động generate handoff summary từ PR description + diff cho bàn giao.
 
**Quick gut:**
Workflow —> nhưng giá trị thực phụ thuộc vào khả năng AI hiểu đủ codebase context, và dev có chấp nhận comment từ AI như comment từ teammate không.

## Problem Cards #2 và #3 — tóm tắt

| Card | Actor | Bottleneck | Metric | Quick gut | Vì sao chưa chọn làm #1 |
|---|---|---|---|---|---|
| Tìm kiếm tài liệu nội bộ | Dev, PM, toàn team kỹ thuật | Tài liệu phân tán nhiều platform, không biết bản nào mới nhất, phải hỏi teammate | 20–80 phút/người/ngày → dưới 2 phút/lần tra cứu | Workflow | Retrieval chỉ tốt khi tài liệu đầu vào có hygiene — cần điều kiện tiên quyết về doc convention trước khi AI phát huy được |
| Review & bàn giao | Dev (author), Senior Dev / Tech Lead (reviewer) | PR nằm chờ 1–2 ngày, reviewer quá tải, lỗi cơ bản lọt qua, bàn giao thiếu context | PR chờ 2–6 ngày/feature → dưới 4 giờ cho lỗi cơ bản | Workflow | Trust của Dev với AI comment chưa được validate; "review" và "bàn giao" là hai sub-problem cần tách — scope còn rộng để ship an toàn |

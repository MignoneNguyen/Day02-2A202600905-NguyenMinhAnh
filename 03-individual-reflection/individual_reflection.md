# 03 — Individual Reflection Example

## Đóng góp trong nhóm

| Hoạt động | Bạn đã làm gì? | Kết quả |
|---|---|---|
| Scan | Đưa ra được 8 vấn đề khác nhau trong internal workflow | Nhóm có đa dạng các loại vấn đề khác nhau với nhiều nhóm chủ đề khác nhau |
| Pitch | Lựa chọn **Daily standup synthesis & action item tracking** và lắng nghe các pitch của các thành viên còn lại | Không được chọn nhưng đã nhận xét, phản biện chỉ ra những vấn đề từ pitch của các thành viên |
| Challenge | Được nhóm hỏi scope của vấn đề đủ để giải quyết được bằng workflow? | Nhóm loại bỏ do scale quá rộng |
| Workflow | Đề xuất thêm tính năng cho cho workflow v1. | Nhóm cải thiện được workflow cũ của vấn đề đã được chọn |
| Research | Tham gia nghiên cứu các tool | Lựa chọn được một model đã có sẵn phù hợp với bài toán của nhóm |
| Rule / Workflow / Agent | Lựa chọn workflow vì đó là phương án phù hợp nhất | Cả nhóm đồng tình ý kiến này |

## Bảng dùng AI trong reflection — Daily standup synthesis & action item tracking

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai/hời hợt ở đâu? | Tôi sửa gì |
|---|---|---|---|---|
| Scan | Gợi ý các pain point liên quan đến standup theo role PM/Dev | Nhớ ra thêm các friction ẩn: recap Slack, update Jira sau meeting, interrupt cost | Gợi ý pain quá chung chung (VD: "meeting không hiệu quả") mà không gắn với workflow cụ thể | Bỏ các ý không có bước thực tế nào trong workflow hiện tại |
| Workflow | Nhờ AI mô tả lại current workflow từ mô tả ngắn | Dựng được flow 6 bước khá sát thực tế | AI gộp "sync tiến độ" và "capture action items" thành một bước duy nhất, bỏ qua bước post-meeting update riêng biệt | Tách bước 4 (manually type lại) thành bước độc lập vì đây chính là bottleneck chính |
| Research | Tìm tool transcribe + action item hiện có trên thị trường | Gợi ý được Fireflies, Otter, Granola, Fellow là các tool đang làm đúng use case này | Có claim "tiết kiệm X phút/ngày" không có nguồn cụ thể; không phân biệt tool nào phù hợp team nhỏ vs enterprise | Chỉ giữ tên tool, bỏ số liệu không verify, ghi chú thêm cần test thực tế |
| Problem Statement | Nhờ AI phản biện các field còn mơ hồ | Chỉ ra impact đang đo thời gian họp nhưng bỏ qua interrupt cost và action item miss rate | AI đề xuất "agent tự động push Jira" quá sớm khi chưa validate chất lượng transcript | Hạ AI hypothesis về mức: transcribe + recap Slack trước, Jira integration là bước sau |

---

## Bài học của mình

- Problem tốt cần có **actor rõ, workflow thật, và metric đo được** chứ không phải chỉ là pain nghe có vẻ phổ biến. Ba problem bạn chọn đều pass được tiêu chí này.
- **Tách sub-problem trước khi nghĩ đến solution.** "Review & bàn giao" hay "sync tiến độ & capture action items" là hai việc khác nhau — gộp lại thì dễ đề xuất AI, nhưng khó ship và khó đo.
- **Non-AI alternative không phải phần phụ**. Nó giúp xác định AI thực sự giải quyết phần nào mà process và tool thông thường không làm được. Nếu linter đã bắt được convention, AI không cần làm lại việc đó.
- **Impact ẩn thường quan trọng hơn impact đo được.** Interrupt cost, context-switching, onboarding kéo dài —> những thứ này không xuất hiện trong số liệu nhưng mới là lý do thực sự team bị chậm.
- **Sự tin tưởng là điều kiện để AI được dùng, không phải kết quả tự nhiên.** Với cả ba pain points, câu hỏi không phải "AI có làm được không" mà là "team có tin đủ để thay đổi workflow không." Đây là rủi ro cần validate sớm nhất.
- **Ship nhỏ nhất có thể trước.** Recap Slack trước Jira integration. Handoff summary trước review automation. Onboarding assistant trước toàn bộ search platform. Scope nhỏ giúp validate trust và accuracy trước khi mở rộng.

---

## Tóm lại 3 điểm cần sửa nếu dùng AI cho problem này:**

- Workflow bị gộp sai chỗ: Bước post-meeting update là bottleneck thực sự nhưng dễ bị AI merge vào bước "gửi recap." —> Cần tách ra rõ ràng để đúng chỗ can thiệp.

- Impact thiếu chiều: Số liệu thời gian dễ tính nhưng interrupt cost và action item miss rate mới là pain sâu hơn. AI thường bỏ qua vì khó định lượng —> Cần bổ sung thủ công.

- Hypothesis bị escalate quá nhanh: AI có xu hướng đề xuất solution phức tạp (agent, integration) trước khi validate bước đơn giản hơn (recap text) —> Cần kéo lại về scope nhỏ nhất có thể ship và đo được.

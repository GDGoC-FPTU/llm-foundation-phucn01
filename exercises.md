# Ngày 1 — Bài Tập & Phản Ánh
## Nền Tảng LLM API | Phiếu Thực Hành

**Thời lượng:** 1:30 giờ  
**Cấu trúc:** Lập trình cốt lõi (60 phút) → Bài tập mở rộng (30 phút)

---

## Phần 1 — Lập Trình Cốt Lõi (0:00–1:00)

Chạy các ví dụ trong Google Colab tại: https://colab.research.google.com/drive/172zCiXpLr1FEXMRCAbmZoqTrKiSkUERm?usp=sharing

Triển khai tất cả TODO trong `template.py`. Chạy `pytest tests/` để kiểm tra tiến độ.

**Điểm kiểm tra:** Sau khi hoàn thành 4 nhiệm vụ, chạy:
```bash
python template.py
```
Bạn sẽ thấy output so sánh phản hồi của GPT-4o và GPT-4o-mini.

---

## Phần 2 — Bài Tập Mở Rộng (1:00–1:30)

### Bài tập 2.1 — Độ Nhạy Của Temperature
Gọi `call_openai` với các giá trị temperature 0.0, 0.5, 1.0 và 1.5 sử dụng prompt **"Hãy kể cho tôi một sự thật thú vị về Việt Nam."**

**Bạn nhận thấy quy luật gì qua bốn phản hồi?** (2–3 câu)
> *Câu trả lời của bạn*

**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**
> *Câu trả lời của bạn*

---

### Bài tập 2.2 — Đánh Đổi Chi Phí
Xem xét kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người thực hiện 3 lần gọi API, mỗi lần trung bình ~350 token.

**Ước tính xem GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này:**
> *Câu trả lời của bạn*
- Tổng số token mỗi ngày là: 10.000 x 3 x ~350 = ~10.500.000 token/ngày (~10.5 triệu token)
- So sánh giá:
+ GPT-4o: input $5 / 1M tokens, output $20 / 1M tokens
+ GPT-4o-mini: input $0.15 / 1M tokens, output $0.60 / 1M tokens
=> Như vậy GPT-4o đắt hơn so với GPT-4o-mini: khoảng 33 lần (input: $5/$0.15 = ~33.33, output: $20/$0.60 = ~33.33) 

**Mô tả một trường hợp mà chi phí cao hơn của GPT-4o là xứng đáng, và một trường hợp GPT-4o-mini là lựa chọn tốt hơn:**
> *Câu trả lời của bạn*
- GPT-4o phù hợp khi cần chất lượng suy luận cao, ví dụ trợ lý AI cho bác sĩ hoặc luật sư, phân tích tài liệu phức tạp, xử lý đa ngôn ngữ chất lượng cao, hoặc các tác vụ yêu cầu độ chính xác và khả năng suy luận mạnh.
- Trong khi đó, GPT-4o-mini phù hợp hơn cho: chatbot hỗ trợ khách hàng, FAQ tự động, tóm tắt văn bản ngắn, hoặc các ứng dụng có lượng request lớn và cần tối ưu chi phí.

---

### Bài tập 2.3 — Trải Nghiệm Người Dùng với Streaming
**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì non-streaming lại phù hợp hơn?** (1 đoạn văn)
> *Câu trả lời của bạn*
Streaming quan trọng nhất trong chatbot hoặc trợ lý AI thời gian thực vì người dùng thấy phản hồi xuất hiện ngay lập tức, giúp trải nghiệm tự nhiên và giảm cảm giác chờ đợi. Ngược lại, non-streaming phù hợp hơn khi cần nhận toàn bộ kết quả hoàn chỉnh trước khi xử lý hoặc lưu trữ, như tạo báo cáo hoặc phân tích dữ liệu.


## Danh Sách Kiểm Tra Nộp Bài
- [ ] Tất cả tests pass: `pytest tests/ -v`
- [ ] `call_openai` đã triển khai và kiểm thử
- [ ] `call_openai_mini` đã triển khai và kiểm thử
- [ ] `compare_models` đã triển khai và kiểm thử
- [ ] `streaming_chatbot` đã triển khai và kiểm thử
- [ ] `retry_with_backoff` đã triển khai và kiểm thử
- [ ] `batch_compare` đã triển khai và kiểm thử
- [ ] `format_comparison_table` đã triển khai và kiểm thử
- [ ] `exercises.md` đã điền đầy đủ
- [ ] Sao chép bài làm vào folder `solution` và đặt tên theo quy định 

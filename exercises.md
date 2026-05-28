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

> _Câu trả lời của bạn_
> Khi temperature tăng từ 0.0 lên 1.5, câu trả lời trở nên sáng tạo và đa dạng hơn. Với temperature thấp, mô hình thường trả lời an toàn, nhất quán và giống nhau giữa nhiều lần gọi. Với temperature cao, nội dung phong phú hơn nhưng đôi khi lan man hoặc kém chính xác hơn.

**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**

> _Câu trả lời của bạn_

## Đối với chatbot hỗ trợ khách hàng, tôi sẽ chọn temperature khoảng 0.2–0.5 vì cần câu trả lời ổn định, chính xác và chuyên nghiệp. Temperature quá cao có thể khiến chatbot trả lời không nhất quán hoặc tạo thông tin không cần thiết.

### Bài tập 2.2 — Đánh Đổi Chi Phí

Xem xét kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người thực hiện 3 lần gọi API, mỗi lần trung bình ~350 token.

**Ước tính xem GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này:**

> _Câu trả lời của bạn_
> Tỷ lệ chi phí:
> 0.010 / 0.0006 ≈ 16.7
> GPT-4o đắt hơn GPT-4o-mini khoảng 16–17 lần cho workload này.

**Mô tả một trường hợp mà chi phí cao hơn của GPT-4o là xứng đáng, và một trường hợp GPT-4o-mini là lựa chọn tốt hơn:**

> _Câu trả lời của bạn_
> GPT-4o là lựa chọn xứng đáng trong các trường hợp yêu cầu độ chính xác và khả năng suy luận cao, ví dụ như trợ lý AI chuyên nghiệp, phân tích dữ liệu phức tạp, viết code hoặc xử lý các tình huống cần hiểu ngữ cảnh sâu. Trong những trường hợp này, chất lượng đầu ra quan trọng hơn chi phí.

Ngược lại, GPT-4o-mini phù hợp hơn cho các hệ thống có lưu lượng lớn và yêu cầu đơn giản như chatbot FAQ, hỗ trợ khách hàng cơ bản hoặc các tác vụ lặp lại. Trong các trường hợp này, tối ưu chi phí và tốc độ phản hồi là ưu tiên hàng đầu.

---

### Bài tập 2.3 — Trải Nghiệm Người Dùng với Streaming

**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì non-streaming lại phù hợp hơn?** (1 đoạn văn)

> _Câu trả lời của bạn_
> Streaming quan trọng nhất trong các ứng dụng tương tác thời gian thực như chatbot, trợ lý ảo hoặc hệ thống hỗ trợ khách hàng, nơi người dùng cần phản hồi nhanh và cảm giác “đang được trả lời ngay” để cải thiện trải nghiệm. Ngược lại, non-streaming phù hợp hơn trong các tình huống cần kết quả hoàn chỉnh và có cấu trúc rõ ràng trước khi xử lý tiếp, chẳng hạn như tạo báo cáo, sinh dữ liệu JSON cho hệ thống khác, hoặc các tác vụ backend yêu cầu độ chính xác và tính toàn vẹn của toàn bộ output.

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

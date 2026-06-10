# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600631
**Name:** Pham Hoang Anh
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 10 | Dữ liệu sạch sẽ, chuẩn hoá tốt, Agent hoạt động chính xác. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | Dữ liệu bị nhiễu do chứa outlier cực đoan và các lỗi khác. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi sử dụng Garbage Data, Agent đã đưa ra câu trả lời sai do dữ liệu đầu vào chứa nhiều lỗi chất lượng nghiêm trọng. Cụ thể, bộ dữ liệu rác có bản ghi ngoại lệ cực đoan (outlier) như 'Nuclear Reactor' với giá $999999, khiến logic tìm sản phẩm điện tử đắt nhất trả về một kết quả không thực tế. Đồng thời, các lỗi khác như trùng lặp ID (Duplicate IDs), sai kiểu dữ liệu (như chuỗi 'ten dollars' cho cột price) và các giá trị bị khuyết thiếu (null values) phá vỡ tính nhất quán của bảng dữ liệu, làm cho Agent không thể tính toán hoặc so sánh chính xác các thuộc tính khác. Những lỗi này chứng minh rằng AI Agent hoàn toàn phụ thuộc vào chất lượng dữ liệu nguồn đầu vào.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** 

Tôi hoàn toàn đồng ý với nhận định này. Cho dù bạn viết prompt thông minh hay chi tiết đến đâu, nếu dữ liệu cung cấp cho mô hình (knowledge base) bị bẩn, thiếu sót hoặc chứa outlier nhiễu, AI Agent vẫn sẽ thực hiện tính toán trên dữ liệu lỗi và đưa ra câu trả lời sai lệch (hallucination). Dữ liệu sạch và chất lượng chính là nền móng cốt lõi cho mọi ứng dụng AI đáng tin cậy.

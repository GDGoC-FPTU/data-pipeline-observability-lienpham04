# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600260
**Name:** Pham Hoang Kim Lien
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 10 | Correct! Agent found the highest-priced electronics item from validated data. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Highly inaccurate! Agent picked an extreme outlier instead of a legitimate product. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Bộ dữ liệu rác chứa nhiều lỗi về chất lượng dữ liệu:

1. **Duplicate IDs**: ID "1" xuất hiện 2 lần (Laptop và Banana), gây nhầm lẫn trong việc định danh sản phẩm.
2. **Wrong Data Types**: Giá của "Broken Chair" là "ten dollars" (chuỗi văn bản) thay vì số, không thể so sánh.
3. **Extreme Outliers**: "Nuclear Reactor" với giá $999,999 là một giá trị bất thường và không thực tế.
4. **Null Values**: "Ghost Item" có ID và category rỗng, không hợp lệ.

Agent chỉ tìm kiếm khối lượng electronics và chọn sản phẩm có giá cao nhất, nên nó rơi vào bẫy của outlier. Dữ liệu rác không được xác thực, nên các giá trị lỗi lẫn với dữ liệu hợp lệ, dẫn đến quyết định sai lầm.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** **Hoàn toàn đồng ý!**

Bài tập này chứng minh rằng chất lượng dữ liệu quan trọng hơn chất lượng của prompt/agent logic. Ngay cả khi agent hoạt động hoàn hảo, dữ liệu xấu sẽ dẫn đến kết quả xấu. Bước Validate & Transform trong ETL pipeline không chỉ "tốt" mà là **cần thiết**. Không có giai đoạn làm sạch dữ liệu, AI agent sẽ luôn đứa ra quyết định sai lệch dựa trên dữ liệu lỗi. Do đó, đầu tư vào dữ liệu sạch là nền tảng để xây dựng hệ thống AI đáng tin cậy.

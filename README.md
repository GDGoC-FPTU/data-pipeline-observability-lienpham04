[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574024&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** phamlienhg1006@gmail.com
**Name:** Phạm Hoàng Kim Liên
**Student ID**: AI20K-2A202600260
---

## Mo ta

Bài lab này xây dựng một pipeline ETL tự động để xử lý dữ liệu sản phẩm từ file JSON. Pipeline bao gồm các bước: Extract (đọc dữ liệu), Validate (loại bỏ dữ liệu không hợp lệ), Transform (chuẩn hóa và tính giá giảm 10%), và Load (lưu ra CSV). Ngoài ra, lab còn thực hiện thí nghiệm so sánh hiệu suất của AI agent khi sử dụng dữ liệu sạch vs dữ liệu rác để chứng minh tầm quan trọng của chất lượng dữ liệu trong hệ thống AI.

## Ket qua

Pipeline đã xử lý thành công 5 records từ raw_data.json, trong đó:
- 3 records hợp lệ được lưu vào processed_data.csv
- 2 records bị loại bỏ (1 record có giá âm, 1 record có category rỗng)

Thí nghiệm agent simulation cho thấy:
- Với dữ liệu sạch: Agent đưa ra quyết định chính xác (điểm 10/10)
- Với dữ liệu rác: Agent bị ảnh hưởng bởi outliers và đưa ra quyết định sai lệch (điểm 2/10)

[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112844&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** hoanganhnth2k3@gmail.com
**Name:** Pham Hoang Anh
**Student ID:** 2A202600631

---

## Mo ta

Bài Lab này thực hiện xây dựng một đường ống dẫn dữ liệu tự động (ETL Pipeline) bằng Python và Pandas. Dự án trích xuất dữ liệu sản phẩm từ file JSON, thực hiện xác thực và lọc bỏ các bản ghi không hợp lệ (giá trị âm hoặc trống danh mục), biến đổi chuẩn hóa dữ liệu, lưu trữ kết quả và tiến hành thử nghiệm giả lập Stress Test đối với AI Agent để so sánh tác động của chất lượng dữ liệu.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
python3 solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python3 generate_garbage.py
python3 agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

- **Tổng số records trong file thô:** 5 bản ghi.
- **Số records hợp lệ và được lưu trữ:** 3 bản ghi (Laptop, Chair, Monitor).
- **Số records bị loại bỏ do không hợp lệ:** 2 bản ghi (Mystery Box vì giá < 0, Phone vì trống category).
- **Stress Test:** AI Agent đưa ra kết quả chính xác trên Clean Data và đưa ra kết quả sai lệch nghiêm trọng trên Garbage Data.

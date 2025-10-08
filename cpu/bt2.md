# Bài 2 — SJF có độc quyền (SRTF)

**Dữ liệu:**
| Process | Arrival Time (AT) | Burst Time (BT) |
|---------|-------------------:|-----------------:|
| P1      | 0                  | 7                |
| P2      | 2                  | 4                |
| P3      | 4                  | 1                |
| P4      | 5                  | 4                |

**Sắp xếp & mô tả:** SRTF: luôn chọn tiến trình còn thời gian chạy **nhỏ nhất** trong ready queue (có thể preempt).

---

## Kết quả (SRTF scheduling)

| Process | AT | BT | CT (Completion) | Turnaround (CT-AT) | Waiting (TAT-BT) |
|---------|----:|----:|----------------:|-------------------:|-----------------:|
| P1      | 0  | 7  | 16              | 16                 | 9                |
| P2      | 2  | 4  | 7               | 5                  | 1                |
| P3      | 4  | 1  | 5               | 1                  | 0                |
| P4      | 5  | 4  | 11              | 6                  | 2                |



**Trung bình:**
- Average Waiting Time = (9 + 1 + 0 + 2) / 4 = 12 / 4 = **3.0**
- Average Turnaround Time = (16 + 5 + 1 + 6) / 4 = 28 / 4 = **7.0**
- Throughput = 4 processes / makespan(=16) = **0.25 process / unit time**

---

## Biểu đồ Gantt (ASCII)

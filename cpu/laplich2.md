# Bài 2 — SJF có độc quyền (SRTF)

**Đề bài:**  
Cho các tiến trình `(p1,p2,p3,p4)` với  
`AT = (0,2,4,5)` và `BT = (7,4,1,4)`  
(Yêu cầu: lập lịch bằng SRTF — Shortest Remaining Time First, tức SJF có preemption)

**Ghi nhớ:**  
- Completion Time (CT) = thời điểm tiến trình hoàn thành  
- Turnaround Time (TAT) = CT − AT  
- Waiting Time (WT) = TAT − BT

---

## Kết quả (SRTF scheduling)

| Process | AT | BT | Start (first) | CT (Completion) | Turnaround (CT − AT) | Waiting (TAT − BT) |
|---------|---:|---:|---------------:|-----------------:|---------------------:|-------------------:|
| P1      | 0  | 7  | 0 (chạy lúc 0) | 16               | 16                   | 9                  |
| P2      | 2  | 4  | 2 (được preempt) | 7               | 5                    | 1                  |
| P3      | 4  | 1  | 4               | 5                | 1                    | 0                  |
| P4      | 5  | 4  | 7               | 11               | 6                    | 2                  |

**Trung bình:**
- **Average Waiting Time** = (9 + 1 + 0 + 2) / 4 = 12 / 4 = **3.0**  
- **Average Turnaround Time** = (16 + 5 + 1 + 6) / 4 = 28 / 4 = **7.0**  
- **Makespan (thời điểm hoàn thành cuối)** = CT_max = **16**

---

## Biểu đồ Gantt (ASCII)
![alt text]({F776810B-53C6-4011-8F77-D80B747DD200}.png)

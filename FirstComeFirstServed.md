# 🧩 FCFS (First Come – First Serve) Scheduling

## 📘 Khái niệm
- FCFS là **thuật toán lập lịch CPU đơn giản nhất**.  
- **Tiến trình nào đến trước sẽ được phục vụ trước**.  
- Hoạt động giống như **hàng đợi FIFO (First In – First Out)**.  
- **Không có ngắt (Non-preemptive)**: tiến trình đang chạy sẽ giữ CPU cho đến khi hoàn thành.  

---

## ⚙️ Cách hoạt động
1. Các tiến trình được sắp xếp theo **thứ tự thời gian đến (Arrival Time)**.  
2. CPU **chọn tiến trình đến sớm nhất** để thực thi.  
3. Khi tiến trình đó kết thúc, CPU **chuyển sang tiến trình kế tiếp**.  
4. Không có việc tạm dừng hoặc chuyển CPU giữa chừng.  

---

## 📊 Ví dụ minh họa

| Process | Arrival | Burst | Start | Finish | Waiting Time | Turnaround Time |
|----------|----------|--------|--------|----------|----------------|-----------------|
| P1 | 0 | 4 | 0 | 4 | 0 | 4 |
| P2 | 1 | 3 | 4 | 7 | 3 | 6 |
| P3 | 2 | 1 | 7 | 8 | 5 | 6 |

**Công thức:**
- `Waiting Time = Start - Arrival`
- `Turnaround Time = Finish - Arrival`

**Kết quả trung bình:**
- Average Waiting Time = (0 + 3 + 5) / 3 = **2.67**
- Average Turnaround Time = (4 + 6 + 6) / 3 = **5.33**

---

## 🧮 Biểu đồ Gantt


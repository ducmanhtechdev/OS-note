🧠 Sắp xếp theo **Arrival Time tăng dần** → Thứ tự chạy:  
`P1 → P3 → P2`

---

## 🔹 Lưu ý
| Trường hợp | Tiêu chí FCFS |
|-------------|----------------|
| Arrival khác nhau | Arrival nhỏ hơn chạy trước |
| Arrival bằng nhau | Theo thứ tự khai báo / ID nhỏ hơn |
| Burst nhỏ hơn | ❌ Không quan tâm |

---

## 🔹 So sánh nhanh
| Thuật toán | Tiêu chí chọn tiến trình |
|-------------|---------------------------|
| **FCFS** | Arrival Time nhỏ hơn |
| **SJF** | Burst Time nhỏ hơn |
| **RR (Round Robin)** | Chia đều theo Quantum Time |

Chắc chắn rồi! Dưới đây là nội dung bạn cung cấp, đã được định dạng lại bằng Markdown với tiêu đề rõ ràng để bạn dễ dàng ôn tập hơn.

---

## **Tổng quan về Lập lịch CPU (CPU Scheduling)**
[cite_start]Lập lịch CPU là quá trình chọn một tiến trình từ hàng đợi sẵn sàng (ready queue) để cấp phát CPU cho nó thực thi[cite: 543]. [cite_start]Mục tiêu chính là để tối đa hóa hiệu suất sử dụng CPU trong môi trường đa chương trình (multiprogramming)[cite: 508].

### **▶️ Khi nào cần Lập lịch?**
[cite_start]Các quyết định lập lịch xảy ra khi một tiến trình[cite: 544]:
* [cite_start]Chuyển từ trạng thái **Running** (đang chạy) sang **Waiting** (đang chờ)[cite: 545].
* [cite_start]Chuyển từ trạng thái **Running** sang **Ready** (sẵn sàng)[cite: 546].
* [cite_start]Chuyển từ trạng thái **Waiting** sang **Ready**[cite: 547].
* [cite_start]Kết thúc (Terminates)[cite: 548].

### **▶️ Tiêu chí đánh giá thuật toán**
[cite_start]Để đánh giá hiệu quả, người ta dựa vào các tiêu chí sau[cite: 570]:
* [cite_start]**CPU utilization (Hiệu suất sử dụng CPU):** Giữ cho CPU luôn bận rộn nhất có thể[cite: 571].
* [cite_start]**Throughput (Thông lượng):** Số lượng tiến trình hoàn thành trên một đơn vị thời gian[cite: 572].
* [cite_start]**Turnaround time (Thời gian hoàn thành):** Tổng thời gian từ lúc một tiến trình được gửi vào cho đến khi nó hoàn thành[cite: 573].
* [cite_start]**Waiting time (Thời gian chờ):** Tổng thời gian một tiến trình phải đợi trong hàng đợi sẵn sàng[cite: 574].
* [cite_start]**Response time (Thời gian phản hồi):** Thời gian từ lúc yêu cầu được gửi đến khi có phản hồi đầu tiên[cite: 575].

### **▶️ Lập lịch Độc quyền và Không độc quyền**
* [cite_start]**Nonpreemptive (Không độc quyền):** Một khi CPU đã được cấp cho một tiến trình, nó sẽ không bị lấy lại cho đến khi tiến trình đó tự nguyện giải phóng CPU[cite: 549].
* [cite_start]**Preemptive (Độc quyền):** CPU có thể bị lấy đi từ một tiến trình đang chạy để cấp cho một tiến trình khác có độ ưu tiên cao hơn hoặc khi hết thời gian cho phép[cite: 550].

---

## **Các Thuật toán Lập lịch CPU ⚙️**

### **1. First-Come, First-Served (FCFS)**
Đây là thuật toán **"Đến trước, phục vụ trước"**.
* [cite_start]**Cách hoạt động:** Tiến trình nào đến hàng đợi trước sẽ được cấp CPU trước[cite: 609]. [cite_start]Đây là một thuật toán **nonpreemptive**[cite: 549].
* [cite_start]**👎 Nhược điểm:** Rất dễ xảy ra **"hiệu ứng đoàn xe" (convoy effect)**, tức là một tiến trình dài sẽ làm các tiến trình ngắn phía sau phải chờ đợi rất lâu, dẫn đến thời gian chờ trung bình tăng vọt[cite: 636].

---

### **2. Shortest-Job-First (SJF)**
Thuật toán **"Công việc ngắn nhất làm trước"**.
* [cite_start]**Cách hoạt động:** Hệ thống sẽ chọn tiến trình có thời gian thực thi (CPU burst) ngắn nhất để chạy tiếp theo[cite: 645].
* [cite_start]**⭐ Ưu điểm:** SJF được chứng minh là **tối ưu**, mang lại **thời gian chờ trung bình nhỏ nhất** trong tất cả các thuật toán[cite: 651].
* **Phân loại:**
    * [cite_start]**Nonpreemptive SJF:** Khi một tiến trình đã được cấp CPU, nó sẽ chạy cho đến khi hoàn thành xong burst time của mình[cite: 647].
    * [cite_start]**Preemptive SJF (hay Shortest-Remaining-Time-First - SRTF):** Nếu một tiến trình mới đến có burst time còn lại ngắn hơn thời gian còn lại của tiến trình đang chạy, hệ thống sẽ ngắt tiến trình hiện tại để chạy tiến trình mới đó[cite: 648].

---

### **3. Round Robin (RR)**
Thuật toán **"Lập lịch Xoay vòng"**, rất phổ biến trong các hệ thống tương tác.
* [cite_start]**Cách hoạt động:** Đây là một thuật toán **preemptive**[cite: 713]. [cite_start]Mỗi tiến trình được cấp một khoảng thời gian nhỏ gọi là **time quantum** (thường là 10-100ms)[cite: 712].
    * Nếu tiến trình hoàn thành trước khi hết quantum, nó sẽ tự giải phóng CPU.
    * [cite_start]Nếu không, nó sẽ bị ngắt và chuyển xuống cuối hàng đợi sẵn sàng, CPU sẽ được chuyển cho tiến trình tiếp theo[cite: 713].
* [cite_start]**👍 Ưu điểm:** Cung cấp **thời gian phản hồi (response time) tốt hơn** so với các thuật toán khác, tạo cảm giác hệ thống chạy mượt mà cho người dùng[cite: 727].
* **Lưu ý:** Hiệu suất của RR phụ thuộc rất nhiều vào độ lớn của time quantum. [cite_start]Nếu quantum quá lớn, nó sẽ hoạt động giống FCFS; nếu quá nhỏ, chi phí chuyển đổi ngữ cảnh sẽ rất tốn kém[cite: 718, 719].

---

### **4. Priority Scheduling**
Thuật toán **"Lập lịch theo độ ưu tiên"**.
* **Cách hoạt động:** Mỗi tiến trình được gán một mức độ ưu tiên. [cite_start]CPU sẽ được cấp cho tiến trình có **độ ưu tiên cao nhất**[cite: 743].
* [cite_start]**Phân loại:** Có thể là **preemptive** hoặc **nonpreemptive**[cite: 744, 745].
* [cite_start]**👎 Nhược điểm:** Có thể gây ra vấn đề **Starvation (Nạn đói)**, tức là các tiến trình có độ ưu tiên thấp có thể không bao giờ được thực thi[cite: 747].
* [cite_start]**Giải pháp:** Sử dụng kỹ thuật **Aging (Lão hóa)**, tức là tăng dần độ ưu tiên của các tiến trình đã phải chờ đợi quá lâu trong hệ thống[cite: 748].
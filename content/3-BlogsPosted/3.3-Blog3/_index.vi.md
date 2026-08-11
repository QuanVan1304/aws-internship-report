---
title: "Blog 3"
date: 2026-08-11
weight: 4
chapter: false
pre: " <b> 3.4. </b> "
---

# THEO DÕI THÍ NGHIỆM MACHINE LEARNING VỚI AMAZON SAGEMAKER EXPERIMENTS

Trong quá trình xây dựng một dự án dự báo doanh số bán hàng trên AWS, mình nhận ra rằng việc huấn luyện mô hình chỉ là một phần nhỏ của công việc. Phần tốn thời gian hơn, và cũng dễ bị bỏ qua hơn, là quản lý các lần thử nghiệm: mình đã thử những tham số nào, kết quả ra sao, và lần chạy nào cho ra mô hình tốt nhất. 

Amazon SageMaker Experiments là dịch vụ mình tìm đến để giải quyết vấn đề này. Điều thú vị là toàn bộ quá trình tracking có thể được tích hợp vào script Python chạy trên máy local thông qua `boto3` mà không bắt buộc phải train mô hình trên hạ tầng SageMaker.

### 1. Bối cảnh: Vấn đề của việc quản lý thử nghiệm thủ công
Khi số lần chạy thí nghiệm vượt qua vài chục, việc lưu kết quả thủ công vào file CSV bộc lộ nhiều điểm yếu:
* Khó khăn trong việc so sánh đa chiều (RMSE, MAPE, thời gian train, số lượng feature).
* Tốn công sức tự duy trì cấu trúc file và viết code để trực quan hóa (visualize).
* Dễ xảy ra sai sót (ghi nhầm, ghi thiếu).
* Khó khăn khi chia sẻ kết quả và biểu đồ cho các thành viên khác trong nhóm.

### 2. Amazon SageMaker Experiments là gì?
SageMaker Experiments là dịch vụ cho phép tổ chức, theo dõi và so sánh các lần chạy thí nghiệm Machine Learning. 
* **Cấu trúc phân cấp:** Gồm Experiment (thí nghiệm tổng thể), Run (mỗi lần chạy cụ thể), và Metric (các chỉ số được ghi lại).
* **Giao diện trực quan:** Tích hợp trực tiếp trên AWS Console, cho phép chọn các cột muốn so sánh, lọc điều kiện và xem biểu đồ mà không cần viết code.

### 3. Cách tích hợp với Script Train Local
Để tích hợp SageMaker Experiments vào máy cá nhân, bạn chỉ cần gọi API của `boto3` ngay trong script Python:
* **Quy trình:** Tạo một Experiment $\rightarrow$ Tạo một Run mới cho mỗi lần train $\rightarrow$ Ghi tham số đầu vào (learning rate, max depth...) và chỉ số đầu ra (RMSE, MAPE).
* **Cấu hình quyền (IAM):** Đảm bảo user/role có các quyền `sagemaker:CreateExperiment`, `sagemaker:CreateRun` và `sagemaker:BatchPutMetrics`. Việc thiếu quyền sẽ dẫn đến lỗi `AccessDeniedException`.

### 4. So sánh các lần chạy trên giao diện
* **Bảng so sánh song song:** Dễ dàng nhận diện lần chạy có RMSE thấp nhất hoặc đánh giá mức độ ảnh hưởng của các siêu tham số (hyperparameters).
* **Biểu đồ Tracking:** Với XGBoost, việc ghi RMSE theo từng boosting round giúp hiển thị rõ đường cong học tập (learning curve), từ đó dễ dàng nhận ra điểm overfit và đánh giá hiệu quả của cơ chế early stopping.

### 5. Những điểm đáng lưu ý
* **Tên định danh:** Tên Experiment phải là duy nhất trong cùng một region và account. Cần dùng `try/except` để bắt lỗi `ResourceInUse` hoặc thêm timestamp vào tên.
* **Quản lý dữ liệu:** Dữ liệu không bị xóa tự động. Cần chủ động sử dụng API để dọn dẹp các Run và Experiment cũ tránh làm rối giao diện.
* **Chi phí:** Được tính dựa trên số lượng metric được ghi. Nhìn chung chi phí rất nhỏ đối với dự án vừa và nhỏ, nhưng cần lưu ý nếu bạn log quá nhiều metric.

### 6. Kết luận
SageMaker Experiments mang lại một hệ thống tracking có giao diện trực quan, lưu trữ tập trung và dễ dàng chia sẻ. Chỉ với vài lệnh `boto3` bổ sung vào script hiện tại, bạn có thể giải quyết triệt để bài toán quản lý tham số mà không cần thay đổi hoàn toàn hạ tầng huấn luyện lên Cloud.

**Tài liệu tham khảo:**
* AWS Documentation – Amazon SageMaker Experiments: https://docs.aws.amazon.com/sagemaker/latest/dg/experiments.html
* AWS Documentation – SageMaker Python SDK Experiments: https://sagemaker-experiments.readthedocs.io/

[*...\[Link bài đăng trên AWS Study Group\]...*](https://www.facebook.com/groups/660548818043427/?multi_permalinks=2227796681318625&ref=share)
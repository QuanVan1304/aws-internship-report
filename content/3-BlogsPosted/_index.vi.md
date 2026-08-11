---
title: "Các bài blogs đã đăng"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Tại đây là phần liệt kê và giới thiệu các blogs mà tôi đã biên soạn và đăng tải trên cộng đồng [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj):

### [Blog 1 - TỪ LOCAL NOTEBOOK ĐẾN MLOPS THỰC CHIẾN: HÀNH TRÌNH "THUẦN PHỤC" AWS SAGEMAKER PIPELINES](3.1-Blog1/)
Blog này chia sẻ hành trình và kinh nghiệm chuyển đổi dự án Machine Learning từ môi trường Jupyter Notebook cục bộ lên hệ thống MLOps tự động trên AWS SageMaker. Bài viết phân tích chi tiết kiến trúc 3 lớp (Data Lake, Continuous Integration với SageMaker Pipelines, và Continuous Deployment với API Gateway & Lambda), đồng thời đúc kết những bài học thực chiến quý giá về việc quản lý Service Quotas, xử lý xung đột thư viện (Dependency Hell) và tối ưu chi phí ngầm từ SageMaker Endpoint.

### [Blog 2 - DEEP LEARNING CÓ LUÔN TỐT HƠN MACHINE LEARNING TRUYỀN THỐNG? BÀI HỌC TỐI ƯU HIỆU NĂNG VÀ CHI PHÍ TRÊN AWS SAGEMAKER](3.2-Blog2/)
Bài viết đi sâu vào việc so sánh hiệu năng và chi phí giữa mô hình Deep Learning (LSTM) và Machine Learning truyền thống (XGBoost) khi giải quyết bài toán dự báo doanh số E-commerce trên nền tảng AWS. Qua đó, blog nhấn mạnh tầm quan trọng của Feature Engineering đối với dữ liệu dạng bảng (tabular data), cách AWS SageMaker tính phí huấn luyện, và cung cấp các chiến lược thực tiễn để lựa chọn mô hình nhằm đạt được sự cân bằng tốt nhất giữa độ chính xác, thời gian huấn luyện và chi phí triển khai.

### [Blog 3 - THEO DÕI THÍ NGHIỆM MACHINE LEARNING VỚI AMAZON SAGEMAKER EXPERIMENTS](3.3-Blog3/)
Bài viết này giới thiệu cách giải quyết bài toán quản lý và theo dõi các lần thử nghiệm (experiments) mô hình Machine Learning bằng dịch vụ Amazon SageMaker Experiments. Blog hướng dẫn chi tiết cách tích hợp công cụ tracking này vào script Python chạy trên máy cá nhân thông qua `boto3`, giúp các kỹ sư dễ dàng so sánh đa chiều các siêu tham số (hyperparameters), trực quan hóa đường cong học tập (learning curve) và quản lý vòng đời mô hình một cách tập trung mà không cần chuyển toàn bộ hạ tầng huấn luyện lên Cloud.
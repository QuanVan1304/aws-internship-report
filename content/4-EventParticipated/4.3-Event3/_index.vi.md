---
title: "Event 3"
date: 2026-08-01
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# AWS FCAJ Agent Forge - Deepdive - August 2026

### Mục Đích Của Sự Kiện

- Trải nghiệm quy trình onboard trực tiếp, làm quen với môi trường và văn hóa làm việc tại văn phòng AWS.
- Làm rõ bản chất của hệ thống Agentic AI và phân biệt các cấp độ tự chủ trong vận hành phần mềm.
- Đi sâu bóc tách kiến trúc Amazon Bedrock Agent Core: Runtime, Identity và Gateway.
- Chia sẻ các chiến lược vận hành (Best Practices) và bảo mật để triển khai hệ thống AI quy mô lớn (production-ready).

### Danh Sách Diễn Giả

- **Anh Nghĩa** - Host & Speaker, chuyên gia dẫn dắt và chia sẻ nền tảng lý thuyết về kiến trúc Agentic AI.
- **Hải Anh** - Lab Instructor, người trực tiếp điều phối và hướng dẫn phần thực hành (Hands-on Lab).

### Nội Dung Nổi Bật

#### Bản chất của Agentic AI
- **Chủ đề:** "Định nghĩa và các cấp độ tự chủ"
- Giải thích Agentic AI là một hệ thống phần mềm có khả năng tự suy luận (reasoning), lập kế hoạch (planning) và thực hiện các nhiệm vụ phức tạp.
- Phân biệt rõ sự khác nhau giữa **Deterministic workflow** (quy trình do lập trình viên định sẵn, độ ổn định cao) và **Multi-agent system** (hệ thống nhiều agent tự động phân chia và phối hợp công việc).

#### Các lớp thành phần trong Amazon Bedrock Agent Core
- **Chủ đề:** "Giải quyết bài toán triển khai quy mô lớn (Production-ready)"
- **Runtime Environment:** Cung cấp môi trường serverless tự động scale. Sử dụng công nghệ Firecracker MicroVM để cô lập hoàn toàn các phiên làm việc, kết hợp bidirectional streaming để phản hồi theo thời gian thực.
- **Identity & Access Management:** Đóng vai trò quản lý xác thực và phân quyền. Sử dụng cơ chế chuyển đổi token thông minh (từ JWT sang Workload Access Token) nhằm tránh rò rỉ thông tin.
- **Gateway:** Lớp trung gian (middleware) quản lý kết nối giữa agent và tools. Tích hợp tính năng Semantic Search (chọn tool qua mô tả ngữ nghĩa) và cơ chế kiểm duyệt Human-in-the-loop.

#### Best Practices cho doanh nghiệp
- **Chủ đề:** "Chiến lược bảo mật và vận hành an toàn"
- Khuyến nghị sử dụng **AWS PrivateLink** để thiết lập kết nối an toàn từ hệ thống nội bộ (on-premises) lên Cloud, không đi qua Internet công cộng.
- Nhấn mạnh tầm quan trọng của việc quản lý phiên bản (Versioning) chặt chẽ để có thể dễ dàng roll-back khi hệ thống gặp lỗi trên môi trường thực tế.

### Những Gì Học Được

#### Tư Duy Thiết Kế & Bảo Mật Hệ Thống
- Nhận thức sâu sắc rằng bảo mật cho AI không chỉ nằm ở tầng ứng dụng mà phải được thiết lập từ tầng mạng (PrivateLink) và tầng ảo hóa (Firecracker MicroVM).
- Hiểu được **Human-in-the-loop** là chốt chặn bắt buộc để kiểm soát rủi ro kinh doanh đối với các tác vụ nhạy cảm như tài chính, hoàn tiền.

#### Kiến Trúc Kỹ Thuật (Technical Mindset)
- Nắm vững cách 3 lớp Runtime, Identity và Gateway phối hợp đồng bộ với nhau trong hệ sinh thái Bedrock Agent Core.
- Hiểu được sự ưu việt của tư duy dùng Semantic Search để gọi công cụ (tools) một cách linh hoạt, thay thế cho cách viết hard-code API truyền thống và cứng nhắc.

### Ứng Dụng Vào Công Việc

- **Thiết kế tính năng an toàn:** Áp dụng ngay cơ chế kiểm duyệt Human-in-the-loop khi xây dựng các module xử lý dữ liệu quan trọng trong kỳ thực tập sắp tới.
- **Tích hợp quản lý vòng đời:** Tạo thói quen áp dụng chiến lược Versioning cho mọi bản cập nhật để dễ dàng khôi phục (roll-back) khi cần thiết.
- **Tối ưu hóa luồng công việc:** Nghiên cứu và thử nghiệm cách thiết lập hệ thống Multi-agent để tự động hóa các tác vụ lặp đi lặp lại.
- **Hòa nhập môi trường:** Nhanh chóng làm quen với không gian văn phòng, rèn luyện tác phong chuyên nghiệp để phối hợp hiệu quả với các anh chị kỹ sư tại AWS.

### Trải nghiệm trong event

Tham gia sự kiện Onboard và đào tạo chuyên sâu tại văn phòng AWS vào ngày 01/08/2026 là một trải nghiệm thực tế quý giá, giúp tôi bước đầu làm quen với môi trường doanh nghiệp quốc tế. Một số trải nghiệm nổi bật:

#### Học hỏi từ lý thuyết đến thực hành
- Sự kết hợp hoàn hảo giữa bài giảng lý thuyết chuyên sâu của anh Nghĩa và phần Hands-on Lab của Hải Anh giúp tôi tiêu hóa kiến thức rất nhanh.
- Việc được trực tiếp cấu hình hệ thống giúp những khái niệm kỹ thuật trừu tượng (như Gateway, Runtime) trở nên cực kỳ trực quan.

#### Trải nghiệm không gian làm việc chuyên nghiệp
- Được cảm nhận trực tiếp văn hóa làm việc cởi mở và tiếp cận cơ sở hạ tầng công nghệ hiện đại ngay tại trụ sở văn phòng AWS.
- Ấn tượng với sự chuyên nghiệp trong khâu tổ chức sự kiện và cách truyền đạt kiến thức rất dễ hiểu của đội ngũ kỹ sư.

#### Bài học rút ra
- Để xây dựng một hệ thống Agentic AI thành công, một mô hình LLM thông minh là chưa đủ. Quan trọng hơn, kiến trúc phần mềm bao quanh nó (middleware, identity, runtime) phải thực sự vững chắc, an toàn và dễ kiểm soát.

#### Một số hình ảnh khi tham gia sự kiện
*Thêm các hình ảnh check-in ngày onboard tại văn phòng AWS và ảnh thực hành lab tại đây...*

> Tổng thể, sự kiện Onboard kết hợp đào tạo chuyên sâu này không chỉ trang bị những kiến thức kỹ thuật "hardcore" về Agentic AI mà còn giúp tôi hòa nhập, hiểu rõ hơn về văn hóa kỹ thuật và định hình rõ ràng tác phong làm việc chuyên nghiệp tại AWS.
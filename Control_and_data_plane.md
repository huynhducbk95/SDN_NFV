# Control plane và Data plane
## 
Hiện nay, trong các hệ thống mạng truyền thống, các thiết bị mạng như router,switch,... đang tồn tại cả 2 cơ chế đó là : **control plane** và **data plane**.
Chúng ta tìm hiểu sơ qua 2 cơ chế này.
- Control plane:
	- Là các tài nguyên nằm trên các thiết bị mạng thực hiện chức năng tạo ra những quyết định về con đường dữ liệu sẽ đi.
	- Các thiết bị đóng vai trò là control plane sẽ là điểm bắt gửi gói tin đi (có source address của gói tin là địa chỉ máy đang kết nối đến thiết bị mạng đó) hoặc là có đích đến của gói tin đó (có nghĩa là destination source là địa chỉ của máy đang kết nối đến thiết bị mạng đó).
	- Các công việc của control plane là cấu hình hệ thống, quản lý và trao đổi thông tin bảng định tuyến (routing table).
	- Các router điều khiển việc trao đổi topology information với các router khác và xây dựng một bảng định tuyến dựa trên một giao thức định tuyến (a routing protocol) vd: RIP, OSPF hay BGP.
- Data plane:
	- Có cách gọi khác là Forwarding plane.
	- Là các tài nguyên trên các thiết bị mạng làm nhiệm vụ chuyển tiếp các gói dựa trên những gì đã được xác định bởi control plane.
	- Các thiết bị này sẽ là các thiết bị trung gian trung quá trình chuyển tiếp gói tin, có nghĩa là thiết bị đó ko có vai trò là source address và destination address trong gói tin.
	
Trong trường hợp cụ thể, các thiết bị mạng sẽ thực hiện vai trò control plane hay là data plane. Chúng ta sẽ xét 2 ví dụ về control plane và data plane:

#### Ví dụ 1
Trong một mô hình mạng có 3 router là R1 - R2 - R3, một gói tin được chuyển bắt đầu từ R1 và đích đến là R3. Trong trường hợp này, R1 và R3 là các control plane vì trong gói tin R1 chính là source address và R3 là destination address. Và R2 là Data plane vì gói tin chỉ đi qua R2 mà R2 không đóng vai trò là source address hay là destination address.
#### Ví dụ 2
Ví dụ trong việc vận chuyển trong một thành phố.
Control plane = quyết định tuyến đường được sử dụng để di chuyển
Data plane = quá trình vận chuyển các gói hàng dựa trên tuyến được đã được xác định từ control plane.

Trong hệ thống mạng truyền thống, các nhà cung cấp mạng gặp rất nhiều khó khăn trong việc nâng cấp hiệu năng, tính bảo mật,... của các luồng dữ liệu, nguyên nhân là do phải thực hiện thay đổi control plane trên tất các các thiết bị mạng trong mạng; Đồng thời, việc quản lý và quyết định xử lý đối với từng luồng dữ liệu cần phải được thực hiện trên các thiết bị riêng biệt như router/switch,...

Công nghệ SDN - Software defined Networking ra đời nhằm giải quyết các vấn đề đang gặp phải trên của mạng truyền thống. Về cơ bản, SDN tách biệt hai cơ chế là control plane và data plane để tạo ra một khung nhìn tổng thể về mạng.
Chi tiết về SDN sẽ được giới thiệu ở tài liệu khác.

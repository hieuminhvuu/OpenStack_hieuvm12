# OpenStack là gì ?

-   Openstack là nền tảng điện toán đám mây nguồn mở, có khả năng hỗ trợ cả public cloud (đám mây công cộng) và private cloud (đám mây riêng tư). Nền tảng này cung cấp cho người dùng giải pháp xây dựng hạ tầng điện toán đám mây có khả năng mở rộng cao, với nhiều tính năng nổi bật.

-   Đây là một phần mềm đám mây có thể chạy được trên những sản phẩm phần cứng, ví dụ như x86 và ARM. Đồng thời cũng có thể tích hợp với những hệ thống kế thừa và sản phẩm của bên thứ ba.

<img src= images/openstack.png>

# OpenStack hoạt động như thế nào ?

-   OpenStack là một nền tảng gồm các thành phần dự án hoạt động dựa trên các API và có thể bổ sung cho nhau. Vì hầu hết thành phần của OpenStack không có khả năng tạo đám mây nên các tổ chức đã chỉ định một số thành phần chuyên thiết lập các tính năng và chức năng tạo ra môi trường đám mây mong muốn.

-   OpenStack hoạt động dựa trên hệ điều hành cơ bản Linux giúp xử lý các lệnh hoặc dữ liệu và nền tảng hóa VMware/Citrix hỗ trợ quản lý tài nguyên phần cứng dành cho các dự án. Một OpenStack hoàn chỉnh được triển khai hoạt động sẽ cho phép quản trị viên cung cấp và quản lý các tài nguyên phiên bản cần thiết dành cho ứng dụng thông qua lệnh gọi API.

# OpenStack service overview

-   OpenStack bao hàm một kiến trúc mô-đun để cung cấp một tập hợp các dịch vụ cốt lõi tạo điều kiện thuận lợi cho khả năng mở rộng và tính linh hoạt như các nguyên lý thiết kế cốt lõi. Chương này xem xét ngắn gọn các thành phần OpenStack, các trường hợp sử dụng và cân nhắc bảo mật của chúng.

<img src= images/openstack_service.png>

## Compute

-   OpenStack Compute, còn được gọi là Nova, là một dịch vụ quan trọng trong nền tảng OpenStack. Nova quản lý các máy ảo và tài nguyên tính toán trong hệ thống đám mây. Nova cho phép người dùng tạo, khởi động, dừng và xóa các máy ảo trên nền tảng OpenStack.

-   Các tính năng của OpenStack Compute bao gồm:

    -   Quản lý tài nguyên: Nova quản lý tài nguyên tính toán, bao gồm CPU, bộ nhớ và lưu trữ để đảm bảo rằng các tài nguyên này được sử dụng hiệu quả.

    -   Quản lý máy ảo: Nova cho phép người dùng tạo, khởi động, dừng và xóa các máy ảo trên nền tảng OpenStack. Nova hỗ trợ nhiều loại máy ảo, bao gồm các máy ảo dựa trên KVM, VMware, Hyper-V và Xen.

    -   Quản lý mạng: Nova cung cấp tính năng quản lý mạng trong hệ thống đám mây. Nova hỗ trợ các mô hình mạng khác nhau, bao gồm mạng riêng ảo, mạng công khai và mạng riêng.

    -   Tính năng tự động hóa: Nova hỗ trợ tính năng tự động hóa, cho phép người dùng triển khai các ứng dụng và máy ảo một cách tự động.

    -   Quản lý tài nguyên trong thời gian thực: Nova cung cấp tính năng giám sát và quản lý tài nguyên tính toán trong thời gian thực, cho phép người dùng theo dõi và quản lý tài nguyên của họ trong thời gian thực.

    -   Quản lý quyền truy cập: Nova hỗ trợ quản lý quyền truy cập và phân quyền để đảm bảo rằng chỉ những người dùng được ủy quyền mới có thể truy cập vào các tài nguyên tính toán.

## Object Storage

-   OpenStack Object Storage, còn được gọi là Swift, là một dịch vụ lưu trữ đám mây được phát triển bởi OpenStack. Swift cung cấp khả năng lưu trữ và quản lý đám mây cho các đối tác và khách hàng, giúp họ lưu trữ và quản lý các dữ liệu lớn một cách hiệu quả.

-   Các tính năng của OpenStack Object Storage bao gồm:

    -   Lưu trữ đối tượng: Swift cho phép người dùng lưu trữ và quản lý các đối tượng dữ liệu lớn, bao gồm các tập tin, hình ảnh và video.

    -   Phân cụm: Swift hỗ trợ phân cụm đám mây, cho phép người dùng mở rộng và tự động hóa các tài nguyên lưu trữ của mình.

    -   Tính khả dụng cao: Swift cung cấp tính năng sao lưu và phục hồi để đảm bảo khả năng sẵn sàng của dữ liệu trong trường hợp có sự cố.

    -   Tính bảo mật: Swift hỗ trợ quản lý quyền truy cập và phân quyền, cho phép người dùng quản lý và kiểm soát quyền truy cập vào các tài nguyên lưu trữ của họ.

    -   Tính mở rộng: Swift cho phép người dùng mở rộng lưu trữ của họ để đáp ứng nhu cầu của ứng dụng. Điều này giúp tối ưu hóa sự sử dụng tài nguyên và giảm thời gian chết đứng của các ứng dụng.

    -   Tính tiêu chuẩn hóa: Swift được xây dựng trên các tiêu chuẩn mã nguồn mở và là một phần của một cộng đồng lớn các nhà phát triển đang phát triển và cải tiến nền tảng này.

## Block Storage

-   OpenStack Block Storage, còn được gọi là Cinder, là một dịch vụ lưu trữ khối đám mây được phát triển bởi OpenStack. Cinder cung cấp khả năng lưu trữ và quản lý các khối dữ liệu lớn, bao gồm các ổ cứng và thiết bị lưu trữ, trong môi trường đám mây.

-   Các tính năng của OpenStack Block Storage bao gồm:

    -   Lưu trữ khối: Cinder cho phép người dùng lưu trữ và quản lý các khối dữ liệu lớn, bao gồm các ổ cứng và thiết bị lưu trữ.

    -   Tính khả dụng cao: Cinder cung cấp tính năng sao lưu và phục hồi để đảm bảo khả năng sẵn sàng của dữ liệu trong trường hợp có sự cố.

    -   Tính mở rộng: Cinder cho phép người dùng mở rộng lưu trữ của họ để đáp ứng nhu cầu của ứng dụng. Điều này giúp tối ưu hóa sự sử dụng tài nguyên và giảm thời gian chết đứng của các ứng dụng.

    -   Tính linh hoạt: Cinder hỗ trợ nhiều loại thiết bị lưu trữ khác nhau, cho phép người dùng tùy chỉnh và triển khai các ứng dụng theo cách thích hợp với nhu cầu của họ.

    -   Tính bảo mật: Cinder hỗ trợ quản lý quyền truy cập và phân quyền, cho phép người dùng quản lý và kiểm soát quyền truy cập vào các tài nguyên lưu trữ của họ.

    -   Tính hiệu suất: Cinder cung cấp tính năng tối ưu hóa hiệu suất để tăng tốc độ truy cập và giảm thời gian đáp ứng.

    -   Tính tiêu chuẩn hóa: Cinder được xây dựng trên các tiêu chuẩn mã nguồn mở và là một phần của một cộng đồng lớn các nhà phát triển đang phát triển và cải tiến nền tảng này.

## Shared File Systems

-   OpenStack Shared File Systems, còn được gọi là Manila, là một dịch vụ lưu trữ tệp chia sẻ đám mây được phát triển bởi OpenStack. Manila cung cấp khả năng lưu trữ và quản lý các tệp chia sẻ trong môi trường đám mây, cho phép nhiều máy chủ truy cập và chia sẻ dữ liệu.

-   Các tính năng của OpenStack Shared File Systems bao gồm:

    -   Lưu trữ tệp chia sẻ: Manila cho phép người dùng lưu trữ và quản lý các tệp chia sẻ, cho phép nhiều máy chủ truy cập và chia sẻ dữ liệu.

    -   Tính khả dụng cao: Manila cung cấp tính năng sao lưu và phục hồi để đảm bảo khả năng sẵn sàng của dữ liệu trong trường hợp có sự cố.

    -   Tính tương thích: Manila hỗ trợ nhiều giao thức lưu trữ tệp chia sẻ khác nhau, bao gồm NFS và SMB.

    -   Tính mở rộng: Manila cho phép người dùng mở rộng lưu trữ của họ để đáp ứng nhu cầu của ứng dụng. Điều này giúp tối ưu hóa sự sử dụng tài nguyên và giảm thời gian chết đứng của các ứng dụng.

    -   Tính linh hoạt: Manila hỗ trợ nhiều loại thiết bị lưu trữ khác nhau, cho phép người dùng tùy chỉnh và triển khai các ứng dụng theo cách thích hợp với nhu cầu của họ.

    -   Tính bảo mật: Manila hỗ trợ quản lý quyền truy cập và phân quyền, cho phép người dùng quản lý và kiểm soát quyền truy cập vào các tài nguyên lưu trữ của họ.

    -   Tính tiêu chuẩn hóa: Manila được xây dựng trên các tiêu chuẩn mã nguồn mở và là một phần của một cộng đồng lớn các nhà phát triển đang phát triển và cải tiến nền tảng này.

## Networking

-   OpenStack Networking, còn được gọi là Neutron, là một dịch vụ mạng đám mây được phát triển bởi OpenStack. Neutron cung cấp khả năng quản lý mạng đám mây, bao gồm các máy ảo và các dịch vụ mạng, như tường lửa, cân bằng tải và VPN.

-   Các tính năng của OpenStack Networking bao gồm:

    -   Quản lý mạng: Neutron cho phép người dùng quản lý mạng đám mây của họ, bao gồm các máy ảo và các dịch vụ mạng.

    -   Tính linh hoạt: Neutron hỗ trợ nhiều loại mạng khác nhau, bao gồm các mạng ảo, mạng VLAN và mạng VXLAN.

    -   Tính cân bằng tải: Neutron cung cấp tính năng cân bằng tải để phân phối tải trên các máy chủ và tăng hiệu suất của ứng dụng.

    -   Tính bảo mật: Neutron hỗ trợ quản lý quyền truy cập và phân quyền, cho phép người dùng quản lý và kiểm soát quyền truy cập vào các tài nguyên mạng của họ.

    -   Tính hiệu suất: Neutron cung cấp tính năng tối ưu hóa hiệu suất để tăng tốc độ truy cập và giảm thời gian đáp ứng.

    -   Tính mở rộng: Neutron cho phép người dùng mở rộng mạng của họ để đáp ứng nhu cầu của ứng dụng. Điều này giúp tối ưu hóa sự sử dụng tài nguyên và giảm thời gian chết đứng của các ứng dụng.

    -   Tính tiêu chuẩn hóa: Neutron được xây dựng trên các tiêu chuẩn mã nguồn mở và là một phần của một cộng đồng lớn các nhà phát triển đang phát triển và cải tiến nền tảng này.

## Dashboard

-   OpenStack Dashboard, còn được gọi là Horizon, là một giao diện người dùng web cho hệ thống đám mây OpenStack. Horizon cho phép người dùng quản lý và giám sát các tài nguyên đám mây của họ thông qua trình duyệt web.

-   Các tính năng của OpenStack Dashboard bao gồm:

    -   Quản lý tài nguyên: Horizon cho phép người dùng quản lý các tài nguyên đám mây của họ, bao gồm máy ảo, mạng và lưu trữ.

    -   Tính đa nền tảng: Horizon hỗ trợ nhiều nền tảng, bao gồm Windows, macOS và Linux.

    -   Tính tùy chỉnh: Horizon cho phép người dùng tùy chỉnh giao diện người dùng để phù hợp với nhu cầu của họ.

    -   Tính bảo mật: Horizon hỗ trợ quản lý quyền truy cập và phân quyền, cho phép người dùng quản lý và kiểm soát quyền truy cập vào các tài nguyên của họ.

    -   Tính tiêu chuẩn hóa: Horizon được xây dựng trên các tiêu chuẩn mã nguồn mở và là một phần của một cộng đồng lớn các nhà phát triển đang phát triển và cải tiến nền tảng này.

    -   Tính hiệu suất: Horizon cung cấp tính năng tối ưu hóa hiệu suất để tăng tốc độ truy cập và giảm thời gian đáp ứng.

    -   Tính linh hoạt: Horizon hỗ trợ nhiều ngôn ngữ khác nhau, cho phép người dùng sử dụng giao diện người dùng bằng ngôn ngữ của họ.

## Identity Service

-   OpenStack Identity Service, còn được gọi là Keystone, là một dịch vụ quản lý danh tính đám mây được phát triển bởi OpenStack. Keystone cho phép người dùng quản lý và xác thực các người dùng, dịch vụ và tài nguyên trong hệ thống đám mây của họ.

-   Các tính năng của OpenStack Identity Service bao gồm:

    -   Quản lý danh tính: Keystone cho phép người dùng quản lý và xác thực danh tính của các người dùng, dịch vụ và tài nguyên trong hệ thống đám mây của họ.

    -   Tính bảo mật: Keystone hỗ trợ quản lý quyền truy cập và phân quyền, cho phép người dùng quản lý và kiểm soát quyền truy cập vào các tài nguyên của họ.

    -   Tính linh hoạt: Keystone hỗ trợ nhiều loại dịch vụ đám mây khác nhau, bao gồm các máy chủ ảo, lưu trữ và mạng.

    -   Tính tiêu chuẩn hóa: Keystone được xây dựng trên các tiêu chuẩn mã nguồn mở và là một phần của một cộng đồng lớn các nhà phát triển đang phát triển và cải tiến nền tảng này.

    -   Tính hiệu suất: Keystone cung cấp tính năng tối ưu hóa hiệu suất để tăng tốc độ truy cập và giảm thời gian đáp ứng.

    -   Tính tương thích: Keystone hỗ trợ nhiều giao thức xác thực khác nhau, bao gồm OAuth, LDAP và OpenID Connect.

    -   Tính mở rộng: Keystone cho phép người dùng mở rộng hệ thống đám mây của họ để đáp ứng nhu cầu của ứng dụng. Điều này giúp tối ưu hóa sự sử dụng tài nguyên và giảm thời gian chết đứng của các ứng dụng.

## Image service

-   OpenStack Image Service, còn được gọi là Glance, là một dịch vụ quản lý hình ảnh đám mây được phát triển bởi OpenStack. Glance cho phép người dùng quản lý và chia sẻ các hình ảnh máy ảo và các tệp hình ảnh khác trong hệ thống đám mây của họ.

-   Các tính năng của OpenStack Image Service bao gồm:

    -   Quản lý hình ảnh: Glance cho phép người dùng quản lý và chia sẻ các hình ảnh máy ảo và các tệp hình ảnh khác trong hệ thống đám mây của họ.

    -   Tính linh hoạt: Glance hỗ trợ nhiều định dạng hình ảnh khác nhau, bao gồm RAW, VMDK và VDI.

    -   Tính bảo mật: Glance hỗ trợ quản lý quyền truy cập và phân quyền, cho phép người dùng quản lý và kiểm soát quyền truy cập vào các tài nguyên của họ.

    -   Tính tiêu chuẩn hóa: Glance được xây dựng trên các tiêu chuẩn mã nguồn mở và là một phần của một cộng đồng lớn các nhà phát triển đang phát triển và cải tiến nền tảng này.

    -   Tính hiệu suất: Glance cung cấp tính năng tối ưu hóa hiệu suất để tăng tốc độ truy cập và giảm thời gian đáp ứng.

    -   Tính tương thích: Glance hỗ trợ nhiều giao thức khác nhau để tải lên và tải xuống hình ảnh, bao gồm HTTP, HTTPS và BitTorrent.

    -   Tính mở rộng: Glance cho phép người dùng mở rộng hệ thống đám mây của họ để đáp ứng nhu cầu của ứng dụng. Điều này giúp tối ưu hóa sự sử dụng tài nguyên và giảm thời gian chết đứng của các ứng dụng.

## Data processing service

-   OpenStack Data Processing Service, còn được gọi là Sahara, là một dịch vụ quản lý và xử lý dữ liệu đám mây được phát triển bởi OpenStack. Sahara cho phép người dùng triển khai và quản lý các cụm xử lý dữ liệu trên hệ thống đám mây của họ.

-   Các tính năng của OpenStack Data Processing Service bao gồm:

    -   Quản lý cụm xử lý dữ liệu: Sahara cho phép người dùng triển khai và quản lý các cụm xử lý dữ liệu trên hệ thống đám mây của họ.

    -   Hỗ trợ nhiều cụm xử lý dữ liệu: Sahara hỗ trợ nhiều cụm xử lý dữ liệu khác nhau, bao gồm Apache Hadoop và Apache Spark.

    -   Tính linh hoạt: Sahara cung cấp nhiều tùy chọn cấu hình để người dùng có thể tùy chỉnh cụm xử lý dữ liệu của mình để phù hợp với nhu cầu của ứng dụng.

    -   Tính tiêu chuẩn hóa: Sahara được xây dựng trên các tiêu chuẩn mã nguồn mở và là một phần của một cộng đồng lớn các nhà phát triển đang phát triển và cải tiến nền tảng này.

    -   Tính bảo mật: Sahara hỗ trợ quản lý quyền truy cập và phân quyền, cho phép người dùng quản lý và kiểm soát quyền truy cập vào các tài nguyên của họ.

    -   Tính tương thích: Sahara hỗ trợ nhiều giao thức khác nhau để kết nối với các cơ sở dữ liệu và lưu trữ dữ liệu khác nhau.

    -   Tính mở rộng: Sahara cho phép người dùng mở rộng hệ thống đám mây của họ để đáp ứng nhu cầu của ứng dụng. Điều này giúp tối ưu hóa sự sử dụng tài nguyên và giảm thời gian chết đứng của các ứng dụng.

<img src= images/openstack_map.jpg>

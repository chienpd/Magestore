**Block:** Chứa các class php, là phần logic của một block dùng để giải
quyết một vấn đề nào đó hoặc chứa các phương thưc liên quan tới dữ
liệu, folder này chứa cả các logic cho frontend lẫn backend.

**Controller:** Chứa các Folder con, được gọi là controller, và các action
của module.

**etc:** Chứa các file cấu hình, liên quan đến các thông số thiết lập module
như quyền hay vị trí đặt các menu, khai báo module với hệ thống.

**Helper:** Chứa các class hỗ trợ ví dụ như tính toán hoặc lưu trữ các biến
hằng

**i18n**: Như bài học trước, nó chứa file ngôn ngữ mà có thể dùng cú pháp
__(‘text’) để gọi

**Model:** Chứa các file liên quan đến dữ liệu, có thể là liên quan đến CSDL
hoặc một cấu trúc dữ liệu thuần túy như Array, Collection….gọi chung
là data source.

**view:** là nơi chứa các file liên quan đến giao diện, cả ở frontend và
backend

**Setup:** Là thư mục liên quan tới việc cài đặt CSDL


--**Lession1**--
1. **Tạo file setup database**
    -> Khi cần cập nhật csdl
    Magestore/Multivendor/Setup/InstallSchema.php
    Magestore/Multivendor/registration.php
    Magestore/Multivendor/etc/module.xml
    
    $ php bin/magento setup:upgrade
    
    => Khi thêm module mới, khai báo tại module.xml(thông tin module sẽ lưu tại bảng setup_module)
2. **Tạo Backend Menu của magento 2**
    -> Thêm custom module vào sidebar menu  
    Magestore/Multivendor/etc/adminhtml/menu.xml    
    $ php bin/magento cache:flush
    
    => tạo file menu.xml: magento sẽ đọc khai báo trong file và thêm vào danh sách menu(sortOrder: ví trí, action: link truy cập, dependsOnModule: sự phụ thuộc)
    resource: chức năng phân quyền
3. **Tạo thêm một ACL (Access Control List)**
    -> quản lý từng quyền truy cập  
    Magestore/Multivendor/etc/acl.xml   
    $ php bin/magento cache:flush
    
    => có thể hạn chế truy cập các page trong backend với 1 user role đặc biệt
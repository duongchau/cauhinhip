# Cấu hình IP tĩnh động trên Ubuntu
========

[Mục lục] (#content)

 [1.Cấu hình IP tĩnh áp trên Ubuntu](#ubuntu1)
 
 [2.Cấu hình IP động áp trên Ubuntu](#ubuntu2) 
 
 [3.Lời cảm ơn](#tks)


<a name="ubuntu1"></a>
## 1.Cấu hình IP tĩnh trên Ubuntu

 Đối với Ubuntu, bạn đăng nhập vào máy ảo

<img src=http://i.imgur.com/4W8ioxn.png>

Tiếp theo , nhập vào lệnh sau  :  ``sudo nano /etc/network/interfaces`` và nhập ``password`` của bạn vào

<img src=http://i.imgur.com/9GOEMVw.png>

Chương trình sẽ xuất hiện nội dung như thế này

<img src=http://i.imgur.com/v2Pbp5d.png>

Ở đây bạn sẽ thiết lập thông số địa chỉ IP tĩnh của bạn !

Ở phần ``The primary networks interface`` :

Ở dòng ``Iface eth0 inet`` để ``static``

Thêm các thông tin sau :

– address 10.0.0.40    ( địa chỉ Ip là tùy vào cách thiết lập của bạn )    
– netmask 255.255.255.0  
– gateway 10.0.0.1   ( có thể có hoặc không – tùy vào tính chất công việc của bạn )

Nhấn **Ctrl + O** để **Save** lại và **Ctrl + X** để **Exit** 

Sau đó bạn restart lại bằng câu lệnh sau :   ``sudo /etc/init.d/networking restart``

Như vậy bạn đã thiết lập thành công địa chỉ IP tĩnh của bạn.

Để kiểm tra lại kết quả Config bạn sử dụng lệnh sau :  ``ifconfig``

<img src=http://i.imgur.com/uTAbNcW.png>

<a name="ubuntu2"></a>
## 2.Cấu hình IP động áp trên Ubuntu

Dùng lệnh  ``ifconfig -a | grep eth`` để xem máy có bao nhiêu card mạng

<img src=http://i.imgur.com/Ohh0X7G.png>
Để xem cấu hình card mạng ``ifconfig``

<img src=http://i.imgur.com/ibbc3SI.png>

Tiếp tục dùng lệnh  ``sudo nano /etc/network/interfaces`` và nhập ``password`` của bạn vào

<img src=http://i.imgur.com/gSc4Hb6.png>

Sau đó reboot hoặc restart dịch vụ mạng

 ``# sudo reboot``
``# sudo /etc/init.d/networking restart``

<a name="tks"></a>
## 3.Lời cảm ơn
Cảm ơn các bạn đã đọc hết bài viết này. Tôi hoan nghênh mọi ý kiến đóng, góp xin hãy post lên blog của tôi hoặc có thể commit lên github này.



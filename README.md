---
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![GitLab](https://img.shields.io/badge/gitlab-%23181717.svg?style=for-the-badge&logo=gitlab&logoColor=white)
![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)

![Python](https://img.shields.io/badge/python-v3.8+-blue.svg)
[![security: bandit](https://img.shields.io/badge/security-bandit-yellow.svg)](https://github.com/PyCQA/bandit)


1. Thống kê tài sản theo trạng thái
   ![image](https://github.com/user-attachments/assets/fb5aad3f-2a19-42d7-8250-0e3cd06db06d)
   ![image](https://github.com/user-attachments/assets/9697cd87-dfdc-47de-9d9f-b11e35fea26a)
   ![image](https://github.com/user-attachments/assets/630db153-de92-44bd-9e20-e982fb46d531)
2. Quản lý tài sản
   Tài sản
   ![image](https://github.com/user-attachments/assets/4e62561c-2ac5-4258-a02f-514a47bcf4ac)
   Danh mục quản lý tài sản
   ![image](https://github.com/user-attachments/assets/e9b11037-45f7-4593-8c40-d02fa7af316f)
3. Bảo trì tài sản
   ![image](https://github.com/user-attachments/assets/17af206e-7e41-47d1-9bb8-23f4343b5ca9)
4. Thanh lý tài sản
   ![image](https://github.com/user-attachments/assets/3bddc172-314e-440e-9192-c38716bafba5)
5. Mượn trả tài sản
   ![image](https://github.com/user-attachments/assets/1ec1080a-89a8-4eb4-9ff3-c95773e249c3)
6. Điều chuyển tài sản
![image](https://github.com/user-attachments/assets/7a9e15cd-9f4a-492a-8c81-7c5e905c0238)

7. Nhà cung cấp
![image](https://github.com/user-attachments/assets/06e10bbf-f039-424f-a356-39e05e3b83d2)

8. Lịch sử
   Lịch sử sử dụng tài sản
![image](https://github.com/user-attachments/assets/b174846f-87ff-4208-8d1d-87223d213425)

   Lịch sử điều chuyển tài sản
![image](https://github.com/user-attachments/assets/0e8a75c4-4e54-4e89-950f-5f5e390b5b67)

# 1. Cài đặt công cụ, môi trường và các thư viện cần thiết

## 1.1. Clone project.
```
git clone https://gitlab.com/anhlta/odoo-fitdnu.git
```
```
cd odoo-fitdnu
```
```
git checkout cntt15_02
```


## 1.2. cài đặt các thư viện cần thiết

Người sử dụng thực thi các lệnh sau đề cài đặt các thư viện cần thiết

```
sudo apt-get install libxml2-dev libxslt-dev libldap2-dev libsasl2-dev libssl-dev python3.10-distutils python3.10-dev build-essential libssl-dev libffi-dev zlib1g-dev python3.10-venv libpq-dev
```
## 1.3. khởi tạo môi trường ảo.

Thay đổi trình thông dịch sang môi trường ảo và chạy requirements.txt để cài đặt tiếp các thư viện được yêu cầu
```
python3.10 -m venv ./venv
```
```
source venv/bin/activate
```
```
pip3 install -r requirements.txt
```

# 2. Setup database

Khởi tạo database trên docker bằng việc thực thi file dockercompose.yml.
```
sudo apt install docker-compose
```
```
sudo docker-compose up -d
```

# 3. Setup tham số chạy cho hệ thống

## 3.1. Khởi tạo odoo.conf

Tạo tệp **odoo.conf** có nội dung như sau:

```
[options]
addons_path = addons
db_host = localhost
db_password = odoo
db_user = odoo
db_port = 5432
xmlrpc_port = 8069
```

# 4. Chạy hệ thống và cài đặt các ứng dụng cần thiết

Lệnh chạy
```
python3 odoo-bin.py -c odoo.conf -u all
```


Người sử dụng truy cập theo đường dẫn _http://localhost:8069/_ để đăng nhập vào hệ thống.

Hoàn tất
    

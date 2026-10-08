# Bài 5: Khởi chạy dịch vụ đơn giản với Docker Compose

## Mục tiêu
Viết tệp `docker-compose.yml` tối giản để khởi chạy 1 dịch vụ web duy nhất bằng Docker Compose CLI v2.

## Cấu trúc thư mục
```
bai5/
├── docker-compose.yml
└── README.md
```

## Nội dung docker-compose.yml
```yaml
services:
  web:
    image: nginx:alpine
    ports:
      - "8082:80"
```
Lưu ý: File YAML dùng 2 dấu khoảng trắng (space) để thụt lùi dòng, không dùng phím Tab.

## Cách chạy

```bash
# Di chuyển vào thư mục bai5
cd bai5

# Khởi chạy dịch vụ
docker compose up -d

# Kiểm tra dịch vụ
docker compose ps

# Kiểm tra web trả về
curl http://localhost:8082

# Hạ dịch vụ xuống
docker compose down
```

## Kết quả mong đợi
- Lệnh `docker compose ps` hiển thị service `web` đang chạy trên port `8082`.
- Lệnh `curl http://localhost:8082` trả về trang chào mừng mặc định của Nginx (Welcome to nginx!).

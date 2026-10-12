# Session 11 – Bài 3: Gradle Dependency Caching

## Mục tiêu
Tăng tốc CI bằng cache Gradle dependencies trong `actions/setup-java@v5`.

## Cấu hình thay đổi
Trong `.github/workflows/ci.yml`, thêm `cache: 'gradle'` tại bước Set up Java JDK 17. Giữ nguyên JUnit Test, `bootJar` và upload artifact `app-jar`.

## Phương pháp kiểm tra
1. Push workflow đã bật cache lên `main` (lần 1). Chờ workflow hoàn tất và lưu thời gian của bước **Set up Java JDK 17**, **Run JUnit tests with Gradle** và tổng job.
2. Tạo commit mới (ví dụ cập nhật README) và push lên `main` (lần 2). Đọc log **Set up Java JDK 17** để kiểm tra có cache hit/restore.
3. Điền số liệu đo thực tế dưới đây, không ước lượng.

## Kết quả thực tế (điền sau khi chạy trên GitHub)

| Chỉ tiêu | Lần 1 (cache chưa có) | Lần 2 (cache được khôi phục) |
|---|---|---|
| Link workflow run | _Chưa chạy_ | _Chưa chạy_ |
| Set up Java JDK 17 | _Chưa đo_ | _Chưa đo_ |
| Run JUnit tests with Gradle | _Chưa đo_ | _Chưa đo_ |
| Tổng thời gian job | _Chưa đo_ | _Chưa đo_ |
| Cache log | _Chưa kiểm tra_ | _Chưa kiểm tra_ |
| Trạng thái | _Chưa kiểm tra_ | _Chưa kiểm tra_ |

## Nhận xét
Điền nhận xét dựa trên số liệu đo. Cache Gradle có thể giảm thời gian tải dependency, nhưng thời gian toàn job không luôn giảm đáng kể do runner, network và bước build/test.

## Minh chứng nộp bài
- `.github/workflows/ci.yml` có `cache: 'gradle'`
- Ảnh log khôi phục cache của lần chạy thứ hai
- Ảnh thời gian chạy của hai workflow (hoặc link workflow run)

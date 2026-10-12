# ss11-b3 – Spring Boot Gradle CI với Dependency Caching

Dự án kế thừa Session 11 Bài 1 và Bài 2, thêm `cache: 'gradle'` cho `actions/setup-java@v5`.

- Java 17, Spring Boot 3.5.6, Gradle, JUnit 5
- CI khi push `main`: test → bootJar → upload artifact `app-jar`
- Báo cáo Bài 3: `homework/session_11/ex3/report.md`

## Chạy local
Windows: `.\gradlew.bat test` hoặc `.\gradlew.bat bootJar`

Linux/macOS: `chmod +x gradlew && ./gradlew test`

## Nộp bài
Push 2 lần lên `main`, chụp log cache và điền thời gian thực tế vào report.md. Không có thời gian đo sẵn trong file.

**Lưu ý:** Gradle Wrapper được kế thừa từ dự án Bài 2; chưa xác thực build thành công trong môi trường tạo gói. Nếu wrapper gặp lỗi, tạo lại bằng Gradle chính thức sửa thêm nội dung (`gradle wrapper --gradle-version 8.14.3`).

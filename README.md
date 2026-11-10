# Bai_giuaki
Hệ thống IOT giám sát chất lượng nước dùng ESP32
# ĐỀ TÀI GIỮA KỲ: HỆ THỐNG IoT GIÁM SÁT CHẤT LƯỢNG NƯỚC SỬ DỤNG ESP32

**Tên tiếng Anh:** ESP32-Based IoT Water Quality Monitoring System

## 1. Đặt bài toán (Problem Statement)

Nước là nguồn tài nguyên thiết yếu trong sinh hoạt, sản xuất nông nghiệp và nuôi trồng thủy sản. Tuy nhiên, chất lượng nước có thể thay đổi theo thời gian do các yếu tố môi trường, hoạt động sản xuất và quá trình ô nhiễm.

Trong thực tế, việc kiểm tra chất lượng nước ở nhiều hộ gia đình, bể chứa hoặc mô hình nuôi trồng thủy sản vẫn chủ yếu dựa vào phương pháp đo thủ công. Phương pháp này không cho phép theo dõi liên tục, người sử dụng khó phát hiện kịp thời những thay đổi bất thường và phải trực tiếp đến vị trí lấy mẫu để kiểm tra.

Xuất phát từ nhu cầu theo dõi chất lượng nước thường xuyên và thuận tiện hơn, đề tài đề xuất xây dựng một hệ thống giám sát chất lượng nước ứng dụng công nghệ IoT. Hệ thống sử dụng ESP32 kết hợp với các cảm biến để thu thập thông số nước, truyền dữ liệu qua Internet và cho phép người dùng giám sát từ xa trên máy tính hoặc điện thoại.

## 2. Mục tiêu đề tài (Project Objectives)

- Xây dựng thiết bị có khả năng đo và giám sát một số thông số chất lượng nước.
- Thu thập dữ liệu từ các cảm biến và xử lý bằng ESP32.
- Truyền dữ liệu lên hệ thống giám sát thông qua giao thức MQTT.
- Xây dựng giao diện Node-RED Dashboard để hiển thị thông số theo thời gian thực.
- Phát hiện và cảnh báo khi các thông số đo vượt ngưỡng cài đặt.
- Hỗ trợ điều khiển một số thiết bị ngoại vi từ xa thông qua giao diện Dashboard.

## 3. Nội dung chính (Main Contents)

Hệ thống dự kiến gồm các chức năng:

1. Đo độ pH của nước.
2. Đo tổng chất rắn hòa tan (TDS).
3. Đo độ đục của nước (Turbidity).
4. Đo nhiệt độ nước.
5. Thu thập và xử lý dữ liệu bằng ESP32.
6. Truyền dữ liệu qua Wi-Fi sử dụng giao thức MQTT.
7. Hiển thị dữ liệu và biểu đồ trên Node-RED Dashboard.
8. Cảnh báo khi các thông số vượt ngưỡng cài đặt.
9. Điều khiển thiết bị ngoại vi như bơm nước mini hoặc servo từ xa.

## 4. Phần cứng dự kiến (Proposed Hardware)

| STT | Linh kiện | Chức năng |
|---|---|---|
| 1 | ESP32 DevKit V1 | Vi điều khiển trung tâm |
| 2 | Cảm biến pH | Đo độ pH |
| 3 | Cảm biến TDS | Đo tổng chất rắn hòa tan |
| 4 | Cảm biến Turbidity | Đo độ đục |
| 5 | DS18B20 | Đo nhiệt độ nước |
| 6 | ADS1115 | Chuyển đổi tín hiệu analog sang digital |
| 7 | OLED 0.96 inch | Hiển thị thông số |
| 8 | Servo SG90 | Điều khiển cơ cấu nhỏ |
| 9 | Bơm nước mini DC | Bơm nước lấy mẫu hoặc thay mẫu |

## 5. Sơ đồ khối dự kiến (Proposed Block Diagram)

Sơ đồ khối tổng thể dự kiến gồm các phần:

- Khối cảm biến: thu thập các thông số chất lượng nước.
- Khối xử lý trung tâm: ESP32 tiếp nhận và xử lý dữ liệu.
- Khối truyền thông: sử dụng Wi-Fi và MQTT để truyền dữ liệu.
- Khối giám sát: Node-RED Dashboard hiển thị thông số và cảnh báo.
- Khối điều khiển: nhận lệnh từ Dashboard để điều khiển bơm mini và servo.

## 6. Công nghệ sử dụng (Technologies)

- Vi điều khiển: ESP32.
- Ngôn ngữ lập trình: C/C++ (Arduino Framework).
- Môi trường phát triển: PlatformIO trên Visual Studio Code.
- Giao thức truyền thông: Wi-Fi, MQTT.
- MQTT Broker: HiveMQ Cloud hoặc EMQX Cloud.
- Nền tảng giám sát: Node-RED Dashboard.
- Thiết kế mạch: KiCad.

## 7. Kết quả dự kiến (Expected Results)

- Xây dựng được mô hình giám sát chất lượng nước sử dụng ESP32.
- Đọc được dữ liệu từ các cảm biến đã lựa chọn.
- Hiển thị thông số nước trên Node-RED Dashboard theo thời gian thực.
- Có khả năng cảnh báo khi thông số vượt ngưỡng thiết lập.
- Điều khiển được một số thiết bị ngoại vi từ xa qua Internet.

## 8. Tài liệu tham khảo (References)

- Espressif Systems – ESP32 Documentation: https://docs.espressif.com/projects/esp-idf/en/stable/esp32/
- Node-RED Documentation: https://nodered.org/docs/
- MQTT – OASIS Standard: https://mqtt.org/
- DFRobot – Gravity: Analog pH Sensor: https://www.dfrobot.com/
- DFRobot – Gravity: Analog TDS Sensor: https://www.dfrobot.com/

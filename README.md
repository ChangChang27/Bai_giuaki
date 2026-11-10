# ĐỀ TÀI GIỮA KỲ: HỆ THỐNG IoT GIÁM SÁT CHẤT LƯỢNG NƯỚC SỬ DỤNG ESP32

## 📌 1. Đặt bài toán (Problem Statement)

💡 **Bối cảnh thực tế**

Nước là nguồn tài nguyên thiết yếu trong sinh hoạt, sản xuất nông nghiệp và nuôi trồng thủy sản. Tuy nhiên, chất lượng nước có thể thay đổi theo thời gian do các yếu tố môi trường, hoạt động sản xuất và quá trình ô nhiễm.

⚠️ **Vấn đề cần giải quyết**

Trong thực tế, việc kiểm tra chất lượng nước ở nhiều hộ gia đình, bể chứa hoặc mô hình nuôi trồng thủy sản vẫn chủ yếu dựa vào phương pháp đo thủ công. Phương pháp này có một số hạn chế:

- ⏱️ Không thể theo dõi chất lượng nước liên tục.
- 📉 Khó phát hiện kịp thời những thay đổi bất thường.
- 📍 Người dùng phải trực tiếp đến vị trí lấy mẫu để kiểm tra.
- 📱 Thiếu khả năng giám sát và cảnh báo từ xa.

🚀 **Ý tưởng đề xuất**

Xuất phát từ nhu cầu theo dõi chất lượng nước thường xuyên và thuận tiện hơn, đề tài đề xuất xây dựng một hệ thống giám sát chất lượng nước ứng dụng công nghệ IoT.

Hệ thống sử dụng ESP32 kết hợp với các cảm biến để thu thập thông số nước, truyền dữ liệu qua Internet và cho phép người dùng giám sát từ xa trên máy tính hoặc điện thoại thông qua Node-RED Dashboard.

## 🎯 2. Mục tiêu đề tài (Project Objectives)

- 🔬 Xây dựng thiết bị có khả năng đo và giám sát một số thông số chất lượng nước.
- ⚙️ Thu thập và xử lý dữ liệu cảm biến bằng ESP32.
- 🌐 Truyền dữ liệu lên hệ thống giám sát thông qua giao thức MQTT.
- 📊 Xây dựng giao diện Node-RED Dashboard để hiển thị thông số theo thời gian thực.
- 🔔 Phát hiện và cảnh báo khi các thông số đo vượt ngưỡng cài đặt.
- 🎮 Hỗ trợ điều khiển một số thiết bị ngoại vi từ xa thông qua Dashboard.

## 🛠️ 3. Nội dung chính (Main Contents)

Hệ thống dự kiến phát triển các chức năng sau:

| STT | Chức năng | Mô tả |
|:---:|---|---|
| 01 | 🔬 Đo pH | Xác định độ axit hoặc kiềm của nước |
| 02 | 💧 Đo TDS | Đo tổng chất rắn hòa tan |
| 03 | 🌫️ Đo độ đục | Đánh giá mức độ đục của nước |
| 04 | 🌡️ Đo nhiệt độ | Theo dõi nhiệt độ nước |
| 05 | ⚙️ Xử lý dữ liệu | ESP32 thu thập và xử lý dữ liệu cảm biến |
| 06 | 📡 Truyền thông | Gửi dữ liệu qua Wi-Fi và MQTT |
| 07 | 📊 Giám sát | Hiển thị dữ liệu trên Node-RED Dashboard |
| 08 | 🔔 Cảnh báo | Cảnh báo khi thông số vượt ngưỡng |
| 09 | 🎮 Điều khiển | Điều khiển bơm mini hoặc servo từ xa |

## 🔌 4. Phần cứng dự kiến (Proposed Hardware)

| STT | Linh kiện | Chức năng |
|:---:|---|---|
| 01 | ESP32 DevKit V1 | 🧠 Vi điều khiển trung tâm |
| 02 | Cảm biến pH | Đo độ pH |
| 03 | Cảm biến TDS | Đo tổng chất rắn hòa tan |
| 04 | Cảm biến Turbidity | Đo độ đục |
| 05 | DS18B20 | 🌡️ Đo nhiệt độ nước |
| 06 | ADS1115 | Chuyển đổi tín hiệu analog sang digital |
| 07 | OLED 0.96 inch | 📟 Hiển thị thông số |
| 08 | Servo SG90 | Điều khiển cơ cấu nhỏ |
| 09 | Bơm nước mini DC | 💧 Bơm nước lấy mẫu hoặc thay mẫu |

## 🧩 5. Sơ đồ khối dự kiến (Proposed Block Diagram)

🏗️ Hệ thống được chia thành các khối chức năng chính:

- **Khối cảm biến:** Thu thập các thông số chất lượng nước.
- **Khối xử lý trung tâm:** ESP32 tiếp nhận và xử lý dữ liệu.
- **Khối truyền thông:** Sử dụng Wi-Fi và MQTT để truyền dữ liệu.
- **Khối giám sát:** Node-RED Dashboard hiển thị thông số và cảnh báo.
- **Khối điều khiển:** Nhận lệnh từ Dashboard để điều khiển bơm mini và servo.

📷 **System Architecture:**

![System Block Diagram](images/block_diagram.png)

## 📡 6. Công nghệ sử dụng (Technologies)

| Công nghệ | Vai trò |
|---|---|
| ![ESP32](https://img.shields.io/badge/ESP32-blue?logo=espressif) | Vi điều khiển |
| ![PlatformIO](https://img.shields.io/badge/PlatformIO-orange?logo=platformio) | Môi trường phát triển |
| ![C++](https://img.shields.io/badge/C%2FC++-blue?logo=cplusplus) | Ngôn ngữ lập trình |
| ![MQTT](https://img.shields.io/badge/MQTT-purple) | Giao thức truyền dữ liệu |
| ![Node--RED](https://img.shields.io/badge/Node--RED-red?logo=nodered) | Xây dựng Dashboard |
| ![KiCad](https://img.shields.io/badge/KiCad-314CB0?logo=kicad) | Thiết kế mạch điện |

- ☁️ MQTT Broker: HiveMQ Cloud hoặc EMQX Cloud.
- 📱 Giao diện giám sát: Máy tính và điện thoại.

## 📈 7. Kết quả dự kiến (Expected Results)

Sau khi hoàn thành, hệ thống dự kiến đạt được:

- ✅ Xây dựng mô hình giám sát chất lượng nước sử dụng ESP32.
- ✅ Đọc và xử lý được dữ liệu từ các cảm biến.
- ✅ Hiển thị thông số nước trên Node-RED Dashboard theo thời gian thực.
- ✅ Lưu trữ và theo dõi lịch sử dữ liệu đo.
- ✅ Cảnh báo khi thông số vượt ngưỡng thiết lập.
- ✅ Điều khiển được một số thiết bị ngoại vi từ xa qua Internet.

## 📚 8. Tài liệu tham khảo (References)

1. [Espressif Systems – ESP32 Documentation](https://docs.espressif.com/projects/esp-idf/en/stable/esp32/)
2. [Node-RED Documentation](https://nodered.org/docs/)
3. [MQTT – OASIS Standard](https://mqtt.org/)
4. [DFRobot – Gravity Analog pH Sensor](https://www.dfrobot.com/)
5. [DFRobot – Gravity Analog TDS Sensor](https://www.dfrobot.com/)

---

<p align="center">
  💧 <b>ESP32 Water Quality Monitoring System</b>
  <br>
  <i>Smart Monitoring – Real-time Data – Remote Control</i>
</p>

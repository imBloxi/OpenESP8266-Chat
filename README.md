# OpenESP8266-Chat
ESP8266 Chat-O-Matic is a Wi-Fi-based chat server built on the ESP8266 microcontroller. 
### **Wi-Fi Chat Server with OLED Display**

## Project Name: **ESP8266 Chat-O-Matic**

### **Project Description**
ESP8266 Chat-O-Matic is a Wi-Fi-based chat server built on the ESP8266 microcontroller. This project allows users to connect to a custom Wi-Fi network, interact via a web-based chat interface, and use a One-Time Password (OTP) for secure access. Additionally, it leverages an OLED display to show connection and chat logs as well as the current OTP for enhanced security and monitoring.

### **Features**
- **Custom Wi-Fi Network:** The ESP8266 operates as an access point, creating a Wi-Fi network with a randomly generated SSID password, ensuring unique access each time it is powered on.
- **Web-Based Chat Interface:** Users can chat through a simple HTML interface served by the ESP8266, with messages logged on the server.
- **OTP Security:** Access to the chat is protected by a 4-digit One-Time Password (OTP), which is valid for 15 minutes.
- **OLED Display Integration:** An SSD1306 OLED display shows connection logs, chat logs, and the current OTP, making it easy to monitor activity in real-time.
- **Auto-Logout:** The system automatically logs out users after 5 minutes of inactivity, ensuring session security.
- **Log Rotation:** Both connection and chat logs are displayed on the OLED in a rotating fashion, switching every 5 seconds.

### **Components Used**
- **ESP8266:** The core microcontroller that hosts the Wi-Fi network and web server.
- **SSD1306 OLED Display:** A 128x64 OLED display used for visual feedback and logs.
- **Arduino Libraries:**
  - `ESP8266WiFi`: For Wi-Fi functionality.
  - `ESP8266WebServer`: To handle HTTP requests.
  - `Wire`: For I2C communication with the OLED display.
  - `SSD1306Wire`: To control the OLED display.
  - `ArduinoJson`: For handling JSON objects, if needed in future enhancements.

### **Setup Instructions**
1. **Hardware Setup:**
   - Connect the SSD1306 OLED display to the ESP8266 via I2C using pins D5 (SCL) and D6 (SDA).
   - Power the ESP8266 with an appropriate power source (e.g., USB).

2. **Software Setup:**
   - Install the required Arduino libraries (`ESP8266WiFi`, `ESP8266WebServer`, `Wire`, `SSD1306Wire`, `ArduinoJson`) through the Arduino Library Manager.
   - Open the code in the Arduino IDE and upload it to your ESP8266.
   
3. **Operating the Chat Server:**
   - Power on the ESP8266, and it will create a Wi-Fi network with the SSID "RealChatNetwork" and a randomly generated password.
   - Connect to this Wi-Fi network using the displayed password on the OLED.
   - Open a web browser and navigate to the ESP8266's IP address, typically `192.168.4.1`.
   - On the web interface, generate and enter the OTP displayed on the OLED to gain access to the chat page.

### **Project Structure**
- **`ESP8266WiFi.h`**: Handles Wi-Fi setup and management.
- **`ESP8266WebServer.h`**: Manages HTTP requests and responses.
- **`Wire.h` & `SSD1306Wire.h`**: Manages the OLED display.
- **`ArduinoJson.h`**: Optional, included for future enhancements to handle JSON data.

### **Usage Notes**
- **Security:** The chat server is intended for demonstration and should not be used in production without further security enhancements.
- **Log Size:** Connection and chat logs are capped at 2048 characters. Logs will reset when the maximum size is reached to prevent overflow.
- **OTP Display:** The OTP is displayed on the OLED for 10 seconds after generation and is valid for 15 minutes.

### **Future Enhancements**
- **Integration with NTP:** Synchronize the ESP8266 clock with an NTP server to display the real time.
- **Enhanced Security:** Implement HTTPS for secure communication and a more robust authentication system.
- **Persistent Logs:** Save logs to a file system or an external server for long-term storage and analysis.
- **User Management:** Create user roles (e.g., admin, user) with different access levels to the chat system.

### **License**
This project is open-source under the MIT License. Feel free to modify, distribute, and use it for your own projects. Contributions are welcome!

### **Contributions**
If you'd like to contribute, please fork the repository and create a pull request with your changes. We welcome improvements, bug fixes, and new features!


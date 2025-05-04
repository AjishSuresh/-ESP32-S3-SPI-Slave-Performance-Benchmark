#ESP32-S3 SPI Slave Performance Benchmark 🚀

Part 2 of the project "Optimizing Energy Consumption and Real-Time Performance in IoT-Driven Embedded Systems: ESP32-S3 SPI Slave Performance Benchmark 🚀
Welcome to the ESP32-S3 SPI Slave Performance Benchmark project! 🎉 This repository contains code and documentation to benchmark the SPI Slave performance of the ESP32-S3 microcontroller. Whether you're a hardware enthusiast, embedded systems developer, or just curious about SPI communication, this project is for you! 💻🔌

📖 Project Overview
This project showcases a full-duplex SPI communication setup using the ESP32-S3 as both an SPI Master and Slave. It includes:

SPI Master and Slave Example Code 📜: Demonstrates how to configure and use the ESP32-S3 for SPI communication with a handshake mechanism.
Performance Benchmark Report 📊: Detailed measurements of SPI Slave performance, including timing analysis and memory usage for various payload sizes.
Visualizations and Insights 📈: Data to help you understand the performance characteristics of the ESP32-S3 SPI Slave.

The code is written in C using the ESP-IDF framework and is designed to be easy to adapt for your own projects. 🛠️

🎯 Features

Full-Duplex SPI Communication 🔄: Simultaneous data transmission and reception between SPI Master and Slave.
Handshake Mechanism 🤝: Uses a dedicated GPIO pin for reliable communication synchronization.
Comprehensive Benchmarking 📏:
Timing measurements for payload sizes from 16 to 128 bytes.
Memory usage details, including DMA buffer and heap fragmentation.
Performance analysis at different CPU frequencies (80, 160, 240 MHz).


Well-Documented Code 📝: Clear comments and configurations for easy customization.
ESP32-S3 Optimized ⚡: Leverages the ESP32-S3's HSPI host and DMA for efficient data transfer.

🛠️ Getting Started
Prerequisites

Hardware:
ESP32-S3 development board 🖥️
Jumper wires for SPI pin connections 🔗


Software:
ESP-IDF (Espressif IoT Development Framework) 🌐
A C compiler (e.g., xtensa-esp32s3-elf-gcc) 🛠️
Python for ESP-IDF setup 🐍


Tools:
Git for cloning the repository 📦
A serial monitor (e.g., minicom or PuTTY) for debugging 🖨️



Installation

Clone the Repository 📥:
git clone https://github.com/AjishSuresh/-ESP32-S3-SPI-Slave-Performance-Benchmark.git
cd esp32-s3-spi-benchmark


Set Up ESP-IDF 🛠️:Follow the ESP-IDF Getting Started Guide to install and configure ESP-IDF.

Update Pin Configurations ⚙️:

Open app_main.c (both Master and Slave versions).
Update the GPIO pin definitions (GPIO_MOSI, GPIO_MISO, GPIO_SCLK, GPIO_CS, GPIO_HANDSHAKE) to match your hardware setup.


Build and Flash 🚀:
idf.py set-target esp32s3
idf.py build
idf.py -p PORT flash

Replace PORT with your serial port (e.g., /dev/ttyUSB0).

Monitor Output 📡:
idf.py monitor

Watch the SPI communication in action! 😎


📊 Benchmark Results
The included ESP32 SPI Analysis PDF provides detailed performance data. Here’s a sneak peek:

Timing Analysis ⏱️:
For a 128-byte payload at 240 MHz:
Average Receive Time: 782 µs
Average Execute Time: 189 µs
Total Time: 971 µs




Memory Usage 💾:
SPI DMA Buffer: 0.6–1.2 KB
Total Dynamic Memory: 3.2–4.0 KB
Static Memory Footprint: 124 KB



Check out the PDF for visualizations and more details! 📈

🔌 Hardware Setup
Connect the ESP32-S3 pins as follows:



Pin Function
Master GPIO
Slave GPIO



MOSI
12
12


MISO
13
13


SCLK
15
15


CS
14
14


Handshake
2
2


Ensure proper grounding and power connections. ⚡
🧑‍💻 Usage

Run the Master and Slave:
Flash the Master code to one ESP32-S3 and the Slave code to another.
Connect the SPI pins and handshake line as described above.


Observe Communication:

The Master sends incremental messages (e.g., "Sender, transmission no. 0001").
The Slave responds with its own messages (e.g., "This is the receiver, sending data for transmission number 0001").
Both devices print received data to the serial monitor.


Analyze Performance:

Use the benchmark data to optimize your SPI setup for specific payload sizes or CPU frequencies.



📂 Repository Structure
esp32-s3-spi-benchmark/
├── app_main.c (Master)         # SPI Master example code
├── app_main.c (Slave)          # SPI Slave example code
├── ESP32 SPI analysis.pdf      # Performance benchmark report
├── README.md                   # This file

🤝 Contributing

Contributions are welcome! 🌟 Feel free to:

Open issues for bugs or feature requests 🐛
Submit pull requests with improvements 🚧
Share your own benchmark results 📊

Please follow the Contributing Guidelines (coming soon!).

🙌 Acknowledgments

Espressif Systems for the ESP-IDF framework and ESP32-S3 documentation.
All contributors and testers who help make this project better! 💖

Happy coding, and enjoy exploring SPI with the ESP32-S3! 🚀✨

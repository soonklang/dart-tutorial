# How to install dart
ในการติดตั้ง Dart ลงบน Windows ของคุณนั้นไม่ใช่เรื่องยากอย่างที่คุณคิด เพียงแค่ทำตาม 5 Step ดังต่อไปนี้
## Step 1: Download Dart SDK
ไปที่ลิ้งค์ https://dart.dev/tools/sdk/archive.

เลื่อนลงมาจนเจอ Stable channel ทำการเลือก Version และ OS จากนั้น คลิ๊ก Download Dart SDK
## Step 2: Extract zip file
ทำการแตกไฟล์ zip ที่ Download มา
## Step 3: Run Dart
เปิด Command Prompt ใช้คำสั่ง dart ในการ Run Dart บนเครื่องของคุณ

ตัวอย่างการใช้คำสั่ง ; D:\software\dart-sdk\bin>dart
## Step 4: Add Dart Path to PATH Environment Variable
ทำการเปิด Settings เข้าไปที่

- System > About > Advanced system settings > Environment Variables
- ทำการเลือก Path ที่อยู่ในกล่อง System variables แล้วกด Edit
- กด new เพื่อเพิ่ม path ที่อยู่ของไฟล์ที่ได้ทำการแตกไฟล์ไวก่อนหน้า คลิ๊ก ok เพื่อเสร็จสิ้น

ตัวอย่างการใส่ที่อยู่ path ; D:\software\dart-sdk\bin\dart
## Step 5: Restart Command Prompt
ปิดหน้าต่าง command Prompt และทำการเปิดใหม่ จากนั้นใช้คำสั่ง dart

ตัวอย่างการใช้คำสั่ง ; D:\>dart

ถ้าไม่ขึ้น error แสดงว่าเสร็จสิ้นการติดตั้ง Dart
# ข้อแตกต่างในการติดตั้ง Dart กับภาษาอื่นๆ
การติดตั้งของภาษาอื่นๆนั้น ไม่มีความซับซ้อนเท่าไหร่เพียงแค่เรา Download โปรแกรมที่ใช้สำหรับการเขียนภาษานั้นๆ เราก็จะสามารถใช้ภาษานั้นๆ ได้ทันที ต่างกับ Dart ที่ต้องใส่ที่อยู่ Path
## การติดตั้ง C on Windows
การติดตั้งภาษา C โดยใช้โปรแกรม Turbo C++ ใช้ได้ทั้งภาษา C และ C++
#### 1 Download Turbo C++
https://static.javatpoint.com/cpages/software/tc3.zip
#### 2 สร้างโฟเดอร์ชื่อ turboc ไว้ในไดรฟ์ c และแตกไฟล์ zip ที่ Download มาไว้ใน c:\turboc
#### 3 click ไฟล์ที่ชื่อว่า install.exe เพื่อทำการติดตั้ง
#### 4 เปิด application TC ที่อยู่ในไฟล์ C:\TC\BIN to write the c program
## การติดตั้ง Java on Windows
การติดตั้งภาษา java ทำได้ง่ายๆ เพียงแค่ Download โปรแกรม Apache NetBeans
#### 1 Download Apache NetBeans
https://netbeans.apache.org/download/index.html
#### 2 เลือก Versions ที่ต้องการ Download
#### 3 เรียกใช้โปรแกรมเพื่อติดตั้ง Apache NetBeans
#### 4 ทดลองเรียกใช้โปรแกรม

## การติดตั้ง Python on Windows
#### 1 Download Python
https://www.python.org/downloads/
#### 2 เลือก Versions ที่ต้องการ Download
#### 3 เรียกใช้โปรแกรมเพื่อติดตั้ง Python
#### 4 ตรวจสอบการติดตั้ง Python
เปิด Command Prompt ใช้คำสั่ง python ถ้าขึ้น version ของ Python แสดงว่าติดตั้งสำเร็จ
#### 5 ตรวจสอบว่าติดตั้ง pip หรือยัง
เปิด Command Prompt ใช้คำสั่ง pip -V ถ้าขึ้น version ของ pip แสดงว่าติดตั้งสำเร็จ
# Reference
- https://www.tutorialkart.com/dart/install-dart-onwindows/#gsc.tab=0
- https://www.javatpoint.com/how-to-install-c
- https://www.tutorialspoint.com/how-to-install-python-in-windows
# Slide
- [how to install dart.pdf](https://github.com/soonklang/dart-tutorial/files/12765270/how.to.install.dart.pdf)

# Link Video
- https://youtu.be/AQoeNMXYQzs

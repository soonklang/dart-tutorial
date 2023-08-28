Datatypes in Dart (5-8)

 **DATA TYPES IN DART**
 
Data types ช่วยให้จัดหมวดหมู่ข้อมูลประเภทต่างๆ ทั้งหมดที่ใช้ในโค้ดของคุณ เช่น ตัวเลข ข้อความ สัญลักษณ์ ฯลฯ ประเภทข้อมูลจะระบุประเภทของค่าที่ตัวแปรจะจัดเก็บ ตัวแปรแต่ละตัวมีประเภทข้อมูลของตัวเอง

ประเภทข้อมูลของ Dart

 //ค่อยแก้เป็นตารางที่แคปมาหลังเติม Description เสร็จ -->>
Data Type	   Keyword	      Description
Maps       	 Map	          แทนชุดของค่าเป็นคู่ key- value
Sets	       Set	          It is an unordered list of unique values of same types
Runes     	 runes	        It represents Unicode values of String
Null	       null	        It represents null value

 **1. Map**
 
   map นั้นถ้าเทียบกับการใช้ List ซึ่งจะเป็นการเรียกใช้ตำแหน่งผ่านตัวเลข แต่ใน Map จะเรียกใช้ตามชื่อข้อมูลที่ตั้งไว้ เหมาะกับการเก็บข้อมูลโดยอาศัยชื่อเป็นตัวเรียกใช้ข้อมูล
ตัวอย่างการใช้ Map

![image](https://github.com/soonklang/dart-tutorial/assets/120002243/dd0a5948-9fc2-4fa6-9f40-e2bb3ed288e7)
![image](https://github.com/soonklang/dart-tutorial/assets/120002243/cce3274f-1297-4e7d-b1d8-1fd1d7c8240d)

กรณีเก็บแบบ list ที่ข้อมูลมีมากกว่า 1 ตัวก็สามารถเก็บแบบนี้ได้

![image](https://github.com/soonklang/dart-tutorial/assets/120002243/3903bfe2-3cb3-4926-a812-1038020ec5ed)
![image](https://github.com/soonklang/dart-tutorial/assets/120002243/b079a1c9-e7e5-4681-9add-ef9d6e20bb15)

ตัวอย่างฟังก์ชันที่มีการใช้งานร่วมกับ Map บ่อย

1.	addAll()  

addAll() คือฟังก์ชันสำหรับรวม (merge) key/value เข้ากับ map ตั้งต้น ถ้า key ไม่มีใน map จะเป็นการ add แต่ถ้ามีอยู่แล้ว จะเป็นการ update value ของ key นั้น

![image](https://github.com/soonklang/dart-tutorial/assets/120002243/3629ace3-2d09-4ac0-afa2-5c0c408a5ef0)
![image](https://github.com/soonklang/dart-tutorial/assets/120002243/935bcf35-bb6d-4bcb-833b-4ba243773b29)

2. containsKey() และ containsValue()
   
containsKey() ฟังก์ชันเช็ค key ที่ให้มาว่ามีใน map มีหรือไม่ ถ้ามี return true ถ้าไม่ return false  containsValue () ฟังก์ชันเช็ค value ที่ให้มาว่ามีใน map มีหรือไม่ ถ้ามี return true ถ้าไม่ return false

![image](https://github.com/soonklang/dart-tutorial/assets/120002243/3bcadc32-0043-4d3c-8f79-f832a1beb114)
![image](https://github.com/soonklang/dart-tutorial/assets/120002243/137d2460-c808-4028-b8b8-b63a821168a8)

3. forEach()
   
กรณีอยากทราบคู่ของแต่ล่ะ key ก็สามารถใช้ forEach วนลูปแต่ละ key/value ใน map

![image](https://github.com/soonklang/dart-tutorial/assets/120002243/250187d4-5d0a-4ca3-9b11-454440950356)
![image](https://github.com/soonklang/dart-tutorial/assets/120002243/a8720a8d-4909-4838-a268-8cb6ef6595c4)

4. remove()
   
 โดย remove () ฟังก์ชันจะลบ key/value ออกจาก map โดยใช้ key และฟังก์ชันจะ return value ของ key นั้นออกมา 

![image](https://github.com/soonklang/dart-tutorial/assets/120002243/d778fb71-08e6-4940-8237-c0e0fab8e2ab)
![image](https://github.com/soonklang/dart-tutorial/assets/120002243/a2db4392-0ae2-42cf-ad7f-3321c5292376)

5. clear()

ฟังก์ชันลบ key/value ทั้งหมดใน map

![image](https://github.com/soonklang/dart-tutorial/assets/120002243/a790c14a-3622-4dea-894e-9b055ec16fda)
![image](https://github.com/soonklang/dart-tutorial/assets/120002243/26f06fe5-8374-4ad9-ba27-d20394a7fd4d)

6. Map.from()

ฟังก์ชันสำหรับสร้าง new map จาก map เดิม (clone)

![image](https://github.com/soonklang/dart-tutorial/assets/120002243/54d355a4-4ffc-4172-a3f5-65b7ffa3f2cd)
![image](https://github.com/soonklang/dart-tutorial/assets/120002243/7491dd5a-2ac9-4d1e-a9ac-7216eb87553d)

  **2. Set**











**Reference**

-  https://siriphonnot.medium.com/10-%E0%B8%9F%E0%B8%B1%E0%B8%87%E0%B8%81%E0%B9%8C%E0%B8%8A%E0%B8%B1%E0%B8%99%E0%B8%AA%E0%B8%B3%E0%B8%AB%E0%B8%A3%E0%B8%B1%E0%B8%9A-map-object-%E0%B8%97%E0%B8%B5%E0%B9%88%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B8%87%E0%B8%B2%E0%B8%99%E0%B8%9A%E0%B9%88%E0%B8%AD%E0%B8%A2%E0%B8%97%E0%B8%B5%E0%B9%88%E0%B8%AA%E0%B8%B8%E0%B8%94%E0%B9%83%E0%B8%99%E0%B8%A0%E0%B8%B2%E0%B8%A9%E0%B8%B2-dart-1cfd879a14c0

-  https://nextflow.in.th/2018/google-flutter-using-dart-list-set-map-data-type-thai/









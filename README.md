AungPao TrueWallet API

นี่คือแอปพลิเคชัน Node.js ที่ใช้ Express ซึ่งให้ API สำหรับการแลกรับบัตรกำนัล TrueMoney (AungPao) และเติมเงินเข้าหมายเลขโทรศัพท์ที่กำหนด

คุณสมบัติ

API รูปแบบ RESTful ด้วย Express.js

เปิดใช้งาน CORS เพื่อรองรับการร้องขอจากแหล่งที่มาต่างๆ

อ่านค่าตัวแปรแวดล้อมจากไฟล์ .env

ดึงข้อมูลและแลกรับบัตรกำนัล TrueMoney AungPao

จัดการข้อผิดพลาดของบัตรกำนัลที่ไม่ถูกต้องหรือหมดอายุ

การติดตั้ง

ข้อกำหนดเบื้องต้น

ติดตั้ง Node.js แล้ว

ติดตั้ง npm หรือ yarn

ขั้นตอนการติดตั้ง

โคลนที่เก็บโค้ด:

git clone https://github.com/your-repo/aungpao-api.git
cd aungpao-api

ติดตั้งแพ็คเกจที่จำเป็น:

npm install

สร้างไฟล์ .env ในไดเรกทอรีหลักและเพิ่มข้อมูลดังนี้:

RECEIVER=YOUR_PHONE_NUMBER
PORT=8801

วิธีใช้งาน

เริ่มเซิร์ฟเวอร์

npm start

เซิร์ฟเวอร์จะทำงานที่ http://localhost:8801 (หรือพอร์ตที่กำหนดใน .env)

API Endpoints

แลกรับบัตรกำนัล AungPao

Endpoint: POST /api/aungpao

ข้อมูลที่ต้องส่ง:

{
  "aungPaoCode": "https://gift.truemoney.com/campaign/?v=018f87a62de97634b9322cf45**********"
}

ตัวอย่างการตอบกลับ:

{
  "message": "aungpao topup success",
  "amount": 50
}

การตอบกลับข้อผิดพลาด

ข้อความผิดพลาด

สาเหตุ

please provide aungpao code

ไม่ได้ระบุรหัสบัตรกำนัลในคำขอ

the voucher is out of date or out of stock please try again later

บัตรกำนัลหมดอายุหรือไม่สามารถใช้ได้

the voucher is already used or invalid

บัตรกำนัลถูกใช้ไปแล้วหรือมีรูปแบบไม่ถูกต้อง

โครงสร้างโครงการ

📦 aungpao-api
├── 📂 routes
│   ├── wallet.js  # เส้นทาง API สำหรับการแลกรับบัตรกำนัล AungPao
├── 📂 utils
│   ├── wallet.js  # ฟังก์ชันการทำงานของกระเป๋าเงินสำหรับประมวลผลบัตรกำนัล
├── .env  # ตัวแปรแวดล้อม
├── server.js  # เซิร์ฟเวอร์ Express หลัก
├── package.json  # ข้อมูลโครงการและแพ็คเกจที่ใช้
├── README.md  # เอกสารประกอบโครงการ

รายการแพ็คเกจที่ใช้

Express.js - เฟรมเวิร์คสำหรับเว็บเซิร์ฟเวอร์

Cors - จัดการการร้องขอข้ามโดเมน

Dotenv - โหลดค่าตัวแปรแวดล้อม

ใบอนุญาต

โครงการนี้เป็นโอเพ่นซอร์สและสามารถใช้งานได้ฟรี


# การพัฒนาแอพพลิเคชั่นด้วย CASDK

# ลิขสิทธิ์
ข้อความหรือรูปภาพที่พิมพ์หรือวาดขึ้นใหม่ที่ปรากฏในเว็บไซต์นี้ กำหนดให้เป็นสาธารณสมบัติ (public domain) ข้อกำหนดด้านสัญญาอนุญาตบันทึกใน UNLICENSE ใจความสำคัญคือผู้อ่านนำเนื้อหานี้ไปใช้โดยไม่มีเงื่อนไข 

หากต้องการใช้ซอฟต์แวร์ CASDK เพื่อการใดๆ ซึ่งอยู่นอกสัญญาอนุญาตของเว็บไซต์นี้ กรุณาศึกษาการใช้สัญญาอนุญาต GNU General Public License version 3 มี [@flyandi](https://github.com/flyandi/mazda-custom-application-sdk) เป็นผู้ถือลิขสิทธิ์ 

#ติดตั้ง CASDK บนระบบปฏิบัติการ windows10
1. สร้างโฟล์เดอร์ C:\CASDK
2. ดาวน์โหลดโปรแกรม [https://github.com/flyandi/mazda-custom-application-sdk/releases/download/0.0.1-alpha/casdk-simulator-0.0.1-alpha-win32.zip](https://github.com/flyandi/mazda-custom-application-sdk/releases/download/0.0.1-alpha/casdk-simulator-0.0.1-alpha-win32.zip) เก็บไว้ที่ C:\CASDK และคลายไฟล์คลิกขวาเลือก Extract All... ไม่ใช่ double click 
3. ดาวน์โหลดรันไทม์ [https://github.com/flyandi/mazda-custom-application-sdk/releases/download/0.0.1-alpha/casdk-alpha-0.0.2.zip](https://github.com/flyandi/mazda-custom-application-sdk/releases/download/0.0.1-alpha/casdk-alpha-0.0.2.zip) และคลายไฟล์แบบเดียวกับข้อ 1
4. เปิดโปรแกรม Mazda Infotainment Simulator.exe อยู่ใน C:\CASDK\casdk-simulator-0.0.1-alpha-win32\Mazda Infotainment Simulator-win32-ia32 พบหน้าจอในภาพด้านล่าง
![Casdk](images/casdk-1.jpg) 
5. เลือกเมนู Simulator อยู่ซ้ายมุมบน แล้วเลือก Choose Runtime Location เลือก C:\CASDK\casdk-alpha-0.0.2\sdcard\system แล้วจึงเลือกเมนู Reload Runtime
6. จากเมนู Simulator เลือก Choose Applications Location เลือก C:\CASDK\casdk-alpha-0.0.2\sdcard แล้วจึงเลือกเมนู Reload Applications
7. จบขั้นตอนติดตั้งโปรแกรม ซอสโค๊ด**แอพ**(ย่อจาก แอพพลิเคชั่น) บันทึกใน C:\CASDK\casdk-alpha-0.0.2\sdcard   หลังจากพัฒนาเสร็จแล้ว สามารถนำไปใช้กับรถได้โดย copy ใส่ SDCARD 

#การใช้งานจริง
**อยู่ในช่วงทดสอบ เมื่อไม่พบปัญหาจะเขียนอธิบายในคราวต่อไป**

#ซอฟต์แวร์ CASDK
CASDK เป็นซอฟต์แวร์ใช้จำลองหน้าจอ MZD Connect ในเมนู Applications จากตัวอย่างที่ซอสโค๊ตเตรียมไว้ให้มีแอพ ดังนี้ 

* Dev Tools
* Hello World
* Multicontroller Demo
* Simple Dashboard
* Speedometer
* Tetris
* Vehicle Data Diagnostic

เมื่อเปิดโปรแกรมและเลือกแอพตัวอย่างเช่น Speedometer มีหน้าจอแบบภาพด้านล่าง

![Speedometer](images/casdk-2.jpg) 

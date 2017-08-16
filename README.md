# PAP
Education....
  From rajamungkala university of technology lanna chiangmai thailand.

Name list
  - Mr.Chanachol Jommongkol
  - Mr.Kittikhun Thakham
  - Mr.Pornchai  Khamdeang
  - Mr.Wachirachai Pongtirdkiat
  
# วงจรโดยรวม วัดอุณหภูมิ , ความชื้น , และตรวจับความเคลื่อนไหว
  
![alt text](https://github.com/Chanachol/PAP/blob/master/images/finally%20circuit.jpg)

                                    #Successfuly 


   ก่อนอื่นมาดู Specification ของ DHT22 กันนะครับว่ามันทำอะไรได้บ้าง ย่านวัดความชื่น 20-90% RH โดยมีค่าความแม่นยำ +- 5% RH ความละเอียดในการวัด 1 % แสดงผลแบบ 8 บิต ย่านวัดอุณหภูมิ 0 -50 องศาเซลเซียส โดยมีค่าความแม่นยำ +- 2 องศาเซลเซียส ความละเอียดในการวัด 1 องศาเซลเซียส แสดงผลแบบ 8 บิต มิ PIN 4 ขารายละเอียดดังรูปด้านบน กินกระแส 0.5 - 2.5 mA (ขณะทำการวัดค่า) ที่ระดับแรงดัน 3 - 5.5 VDC อ่านค่าสัญญาณ (Sample Rate) ทุก 1 วินาที รายละเอียดของ Spec อื่นๆ นอกเหนือจากนี้ดูในที่ Manual นะครับ

จริงๆแล้ว Sensor วัด อุณหภูมิ กับ ความชื้นใน Series นี้มีออกมาหลายรุ่นครับ เช่น DHT11 DHT 22 DHT21 บางทีมาแต่ตัว sensor บางทีมาเป็น module ความแตกต่างก็คือความแม่นยำในการวัดค่าของ sensor ครับ

# ทีนี้มาดูวิธีการต่อใช้งานครับ

![alt text](https://github.com/Chanachol/PAP/blob/master/images/DHT22-1.jpg)

# วิธีการต่อขาของ Nodemcu

![alt text](https://github.com/Chanachol/PAP/blob/master/images/how%20dh22.jpg)
ในการการต่อวัดแบบปกติ คือ ระยะห่างระหว่าง Sensor กับตัว Arduino ห่างกันไม่เกิน 20 เมตร จะต้องใช้ Pull up resistor ขนาด 5kohm (ว่าง่ายๆ คือต่อ R 5k ไว้กับแหล่งจ่ายแรงดันและต่อเข้าไปที่ขา DATA ด้วย)

Pin 1 ต่อกับ VDD

Pin 2 ต่อเป็นขา DATA

Pin 3 ไม่ได้ใช้

Pin 4 ลงกราวด์

โดยใช้แหล่งจ่ายแรงดัน VDD ขนาด 3-5.5 VDC ครับ ซึ่งข้อดีคือจะทำให้ DHT11 นี้สามารถใช้งานได้กับ Arduino หลายรุ่น แต่ในที่นี้เราจะใช่ Arduno NodeMCU ครับ

เมื่อต่อเสร็จแล้วนำโค๊ดที่อัพโหลดให้มาทำการดัดแปลงนิดหน่อย 


# วิธีการต่อ NodeMCU ESP8266 แสดงผลออก จอ LCD

![alt text](https://github.com/Chanachol/PAP/blob/master/images/Lcd%20to%20node.jpg)

การต่อสาย ขา I2C ของ NodeMCU คือ

  - SCL - D1
 
  - SDA - D2
  
จอ LCD ส่วนมากใช้ไฟ 5V ดังนั้นต้องใช้ไฟ 5V จ่ายให้ คือไฟที่มาจากขา Vin ใน NodeMCU

# การต่อขา NodeMCU LCD - Vin - VCC

  - GND - GND
  
  - D1 - SCL
  
  - D2 - SDA
  
# วิธีการดักข้อมูลโดยใช้โปรแกรม Wireshark  

![alt text](https://github.com/Chanachol/PAP/blob/master/images/wireshak.jpg)

# การวัดค่า sleep moded

การวัดค่า sleep mode สายกราว์ อเดบเตอร์ ต่อ GND ของ node mcu สายไฟ+ของ อเดบเตอร์ ไปต่อเข้ากับ สายไฟ+ของมิเตอร์ กราว์ของมิเตอร์ไปเข้า Vinของ mode mcu ถ้าถอดสาย usb ออกไฟจะเลี้ยงไม่พอ

![alt text](https://github.com/Chanachol/PAP/blob/master/images/sleeping.jpg)

# ความคิดสร้างสรรค์

# การตรวจจับความเคลื่อนไหว Pirsensor

การต่อดังนี้..

![alt text](https://github.com/Chanachol/PAP/blob/master/images/pir%20to%20node.jpg)

ถ้ามีการเคลื่อนไหวผ่านหน้าสัมผัสเซ็นเซอร์ จะส่งเสียงเตือนที่ Speaker

และ Led show กระพริบ.


# Thankyou for folowing.





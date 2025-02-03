# Task Manager

## คำอธิบายโปรเจกต์และวัตถุประสงค์

โปรเจกต์ Task Manager เป็นโปรแกรม CLI (Command Line Interface) ที่ช่วยในการจัดการงานต่างๆ โดยให้ผู้ใช้สามารถเพิ่มงาน แสดงงานทั้งหมด มาร์กงานเป็นเสร็จสิ้น ลบงาน หรือค้นหางานได้ง่ายๆ ผ่านการป้อนคำสั่งจากคีย์บอร์ด โปรแกรมใช้ไฟล์ JSON ในการเก็บข้อมูลงานต่างๆ เพื่อให้สามารถเก็บข้อมูลได้อย่างมีระเบียบและสามารถใช้งานในระยะยาวได้


## คำแนะนำในการติดตั้ง

โปรแกรมนี้สามารถใช้งานได้บนระบบปฏิบัติการที่รองรับ Python 3.x โดยไม่จำเป็นต้องติดตั้งไลบรารีเพิ่มเติม
1. ติดตั้ง Python และ Jupyter Notebook
-ดาวน์โหลดและติดตั้ง Python 3 จาก https://www.python.org/downloads/
-ติดตั้ง Jupyter Notebook โดยใช้คำสั่ง: pip install notebook
2. ติดตั้งไลบรารีที่จำเป็น
-โค้ดนี้ใช้ไลบรารีมาตรฐานของ Python (json, os, datetime) ซึ่งมาพร้อมกับ Python อยู่แล้ว
3. ดาวน์โหลดไฟล์โปรเจกต์
-ดาวน์โหลดไฟล์ TaskManagerApplication.ipynb และ tasks.json (หากยังไม่มีไฟล์นี้ โปรแกรมจะสร้างให้เอง)


## วิธีการรันโปรแกรม

1. เปิด Jupyter Notebook โดยใช้คำสั่ง: jupyter notebook
2. ไปที่โฟลเดอร์ที่เก็บไฟล์ TaskManagerApplication.ipynb
3. เปิดไฟล์ TaskManagerApplication.ipynb
4. รันเซลล์ของโค้ดทั้งหมด โดยไปที่เมนู Cell > Run All
5. โปรแกรมจะแสดงเมนูให้เลือกใช้งานผ่านอินพุตของ Jupyter Notebook


## ฟีเจอร์หลักและตัวอย่างการใช้งาน

1. เพิ่มงานใหม่ (Add Task)
-ฟังก์ชัน add_task() ใช้สำหรับเพิ่มงานใหม่ พร้อมระบุชื่อ คำอธิบาย และวันที่กำหนดส่ง
-ข้อมูลจะถูกบันทึกลงใน tasks.json

# ตัวอย่างการใช้งาน:

Select menu: 1
Task name: Write Report
Description: Write the monthly report for the company
Due date (YYYY-MM-DD): 2025-02-28

# โปรแกรมจะบันทึกงานนี้และแสดงข้อความ:
The task 'Write Report' has been added!

2. แสดงรายการงานทั้งหมด (List Tasks)
-ฟังก์ชัน list_tasks() ใช้สำหรับแสดงรายการงานทั้งหมดในระบบ
-หากไม่มีงาน ระบบจะแจ้งว่าไม่มีงานในระบบ

# ตัวอย่างการใช้งาน:

Select menu: 2
# โปรแกรมจะบันทึกงานนี้และแสดงข้อความ:
Write Report (2025-02-28) - Pending

3. มาร์กงานว่าเสร็จสิ้น (Mark Task as Complete)
ฟังก์ชัน mark_task_complete() ใช้สำหรับเปลี่ยนสถานะงานให้เป็น "Complete"
ผู้ใช้ต้องป้อนหมายเลข ID ของงานที่ต้องการเปลี่ยนสถานะ

# ตัวอย่างการใช้งาน:

Select menu: 3
Enter the task ID that you want to mark as complete: 1

# โปรแกรมจะบันทึกงานนี้และแสดงข้อความ:
Mark task 'Write Report' is finished!

4. ลบงาน (Delete Task)
-ฟังก์ชัน delete_task() ใช้สำหรับลบงานออกจากระบบ
-ผู้ใช้ต้องป้อนหมายเลข ID ของงานที่ต้องการลบ

# ตัวอย่างการใช้งาน:

Select menu: 4
Enter the task ID that you want to delete: 1

# โปรแกรมจะบันทึกงานนี้และแสดงข้อความ:
Task ID 1 successfully deleted!

5. ค้นหางาน (Search Task)
-ฟังก์ชัน search_tasks() ใช้สำหรับค้นหางานจากชื่อที่ตรงกับคำค้นหา
-ระบบจะแสดงรายการงานที่มีชื่อสอดคล้องกับคำค้นหา

# ตัวอย่างการใช้งาน:

Select menu: 5
Enter a search term: report

# โปรแกรมจะบันทึกงานนี้และแสดงข้อความ:
Write Report (2025-02-28)

6. ออกจากโปรแกรม
-กด 6 เพื่อออกจากโปรแกรม

# ตัวอย่างการใช้งาน:
Select menu: 6

# โปรแกรมจะบันทึกงานนี้และแสดงข้อความ:
Exit the program.
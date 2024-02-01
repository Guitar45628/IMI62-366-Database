## LAB 4
1. ต้องการทราบข้อมูลแพทย์ (physician) ทั้งหมด

`SELECT * FROM Physician;`

![image](https://github.com/Guitar45628/IMI62-366-Database/assets/66988309/96355554-7180-41f4-9dae-2da690329812)


2. ต้องการทราบ รหัส และ ชื่อ ของแพทย์ที่มี ตำแหน่ง เป็น Surgical Attending Physician

 `SELECT EmployeeID, Name From Physician WHERE Position = "Surgical Attendi ng Physician";`

 ![image](https://github.com/Guitar45628/IMI62-366-Database/assets/66988309/5c8aaee7-71db-4f9a-8710-b449a14d5b24)


3. ต้องการทราบข้อมูลหัตการ (Procedure) ที่มีต้นทุน เกิน 5000

`SELECT * FROM Procedures WHERE cost > 5000;`

![image](https://github.com/Guitar45628/IMI62-366-Database/assets/66988309/b391671d-1fe5-4855-8f23-741fcc8801e0)

4. ต้องการทราบข้อมูลของห้องพักผู้ป่วย (Room) ที่ว่างอยู่ (unavalible มีค่าเป็น 0)
    ` SELECT * FROM Room WHERE Unavailable = 0;`

![image](https://github.com/Guitar45628/IMI62-366-Database/assets/66988309/0f5453ce-88c0-4e80-b23b-9ca83ef01c0f)


5. ต้องการทราบจำนวนของห้องพักผู้ป่วยที่ว่าง และไม่ว่าง

`SELECT Unavailable, COUNT(*) FROM Room GROUP BY Unavailable;`

![image](https://github.com/Guitar45628/IMI62-366-Database/assets/66988309/75d62ce9-04e2-4ac3-bed5-d608af3c5062)

6. ต้องการทราบว่าแต่ละการรักษา (Undergoes) มีต้นทุนค่าหัตการเท่าไหร่

` SELECT u.Stay, SUM(p.Cost) FROM Procedures p JOIN Undergoes u ON p.Code = u.Procedures GROUP BY u.Stay;`

![image](https://github.com/Guitar45628/IMI62-366-Database/assets/66988309/db65c7f7-7614-481d-96ab-7da36291847e)

7.ต้องการทราบชื่อ เบอร์โทรผู้ป่วย ที่มีหมอ John Dorian เคยทำหัตการให้

` SELECT u.Stay, SUM(p.Cost) FROM Procedures p JOIN Undergoes u ON p.Code = u.Procedures GROUP BY u.Stay;`



8. ต้องการทราบชื่อแพทย์ที่เคยสั่งยา Thesisin (ยังไม่เสร็จ)

` SELECT u.Stay, SUM(p.Cost) FROM Procedures p JOIN Undergoes u ON p.Code = u.Procedures GROUP BY u.Stay;`

9. ต้องการทราบจำนวนผู้ป่วยที่ที่นัดหมายในแต่ละวัน

` SELECT Starto,COUNT(*) FROM Appointment GROUP BY Starto;`

![image](https://github.com/Guitar45628/IMI62-366-Database/assets/66988309/c695c4ac-adf4-41bc-beff-be4663ce88c6)


10. ต้องการทราบวันที่ และจำนวนผู้ป่วยที่ที่นัดหมายเกิน 5 คนในแต่ละวัน

`SELECT Starto,COUNT(*) FROM Appointment GROUP BY Starto HAVING COUNT(*) >5;`

![image](https://github.com/Guitar45628/IMI62-366-Database/assets/66988309/450f9e56-c45a-4b1e-8973-0600801b9487)

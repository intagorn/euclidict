# โจทย์โปรแกรมมิ่ง: การคำนวณระยะทางระหว่างเมืองโดยใช้ Dictionary และ Tuple

## คำอธิบายปัญหา:
คุณต้องเขียนโปรแกรม Python ที่ทำตามขั้นตอนต่อไปนี้:
1. รับจำนวนเต็ม `n` เป็นบรรทัดแรก ซึ่งระบุจำนวนเมือง
2. จากนั้นรับข้อมูลเมืองและพิกัดของเมืองแต่ละเมือง ซึ่งประกอบด้วย:
   - บรรทัดแรก: ชื่อเมือง (string)
   - บรรทัดถัดมา: ค่าพิกัด x (float)
   - บรรทัดถัดมา: ค่าพิกัด y (float)
3. หลังจากรับข้อมูลเมืองเรียบร้อยแล้ว จะมีชื่อเมืองอีกสองบรรทัด (เมืองแรกและเมืองที่สอง) สำหรับการคำนวณระยะทางระหว่างเมือง
4. โปรแกรมของคุณต้อง:
   - สร้าง dictionary ที่เก็บชื่อเมืองเป็น key และเก็บพิกัดของเมือง (x, y) เป็น tuple เป็น value
   - พิมพ์ dictionary ที่สร้างขึ้นเป็นบรรทัดแรกของ output
   - คำนวณระยะทางแบบ Euclidean ระหว่างสองเมืองที่ระบุ ระยะทางที่ได้ต้องปัดเศษเป็นทศนิยม 2 ตำแหน่งโดยใช้ฟังก์ชัน `round()`
   - หากชื่อเมืองใดเมืองหนึ่งหรือทั้งสองเมืองไม่อยู่ใน dictionary ให้พิมพ์ **NA** แทนระยะทาง

## การรับข้อมูล:
- บรรทัดแรก: จำนวนเต็ม `n` ที่ระบุจำนวนเมือง
- ต่อจากนั้น `3 * n` บรรทัด ซึ่งประกอบด้วย:
  1. ชื่อเมือง (string)
  2. พิกัด x (float)
  3. พิกัด y (float)
- บรรทัดสุดท้าย 2 บรรทัดจะเป็นชื่อของเมืองสองเมืองที่ต้องการคำนวณระยะทาง

## การแสดงผล:
1. แสดง dictionary ของชื่อเมืองและพิกัดของเมืองที่สร้างขึ้นในบรรทัดแรก
2. แสดงระยะทางแบบ Euclidean ระหว่างสองเมืองที่ระบุ โดยปัดเศษเป็นทศนิยม 2 ตำแหน่ง
3. หากเมืองใดเมืองหนึ่งไม่อยู่ใน dictionary ให้แสดง **NA** แทนระยะทาง

## ตัวอย่างการทำงาน:

**อินพุต**:
```
3
NewYork
3
5
LosAngeles
1
1
Chicago
0
2
NewYork
Chicago
```

**ผลลัพธ์**:
```
{'NewYork': (3.0, 5.0), 'LosAngeles': (1.0, 1.0), 'Chicago': (0.0, 2.0)}
3.61
```

**อินพุต**:
```
3
Paris
2.5
4.8
London
1.2
3.5
Berlin
0
0
Paris
Madrid
```

**ผลลัพธ์**:
```
{'Paris': (2.5, 4.8), 'London': (1.2, 3.5), 'Berlin': (0.0, 0.0)}
NA
```

## สูตรการคำนวณระยะทางแบบ Euclidean:
```python
distance = ((x2 - x1)**2 + (y2 - y1)**2)**0.5
```

## หมายเหตุ:
- ใช้ฟังก์ชัน `round(distance, 2)` เพื่อปัดเศษระยะทางเป็นทศนิยม 2 ตำแหน่ง
- หากเมืองใดเมืองหนึ่งไม่อยู่ใน dictionary ให้พิมพ์ **NA** สำหรับระยะทางนั้น

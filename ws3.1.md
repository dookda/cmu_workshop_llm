
<a name="กิจกรรม 3.1"></a>
## กิจกรรมที่ 4 — คลัง Prompt พร้อมใช้ 8 แบบ

### 1 Prompt แบบมีโครงสร้าง (ใช้ได้กับทุกงาน)
```text
ROLE
คุณเป็น [บทบาท]

TASK
[งานที่ต้องการ]

CONTEXT
[ผู้อ่านคือใคร เอาไปทำอะไร มีข้อจำกัดอะไร]

REQUIREMENTS
- [ข้อกำหนดที่ 1]
- [ข้อกำหนดที่ 2]

OUTPUT FORMAT
[รูปแบบผลลัพธ์ที่ต้องการ]

QUALITY
ถ้ามีศัพท์เทคนิค ให้นิยามก่อนใช้
ถ้าไม่แน่ใจข้อมูลใด ให้ระบุ uncertainty แทนการเดา
```

### 2 ติวเตอร์แบบ Socratic
```text
ทำหน้าที่เป็น tutor เรื่อง [TOPIC]
ระดับของฉัน: [LEVEL]

อย่าเฉลยทันที
ถามฉันทีละคำถามเพื่อช่วยให้ฉันหาคำตอบเอง
ถ้าฉันตอบผิด ให้ hint ก่อน
เฉลยเมื่อฉันขอเท่านั้น
เมื่อจบ ให้สรุปสิ่งที่ฉันควรทบทวน
```

### 3 ตรวจความเข้าใจแบบ Feynman
```text
นี่คือคำอธิบายของฉันเกี่ยวกับ [TOPIC]:

[วางคำอธิบายของคุณที่นี่]

อย่าเพิ่งเขียนใหม่ให้
ให้ทำตามลำดับนี้:
1. ระบุส่วนที่ถูกต้อง
2. ระบุส่วนที่คลุมเครือ
3. ระบุส่วนที่ผิด
4. ตั้งคำถาม 3 ข้อให้ฉันแก้ความเข้าใจเอง

รอฉันตอบก่อน แล้วค่อยช่วยปรับคำอธิบาย
```

### 4 ตอบจากเอกสารเท่านั้น (Grounded)
```text
ใช้เฉพาะเอกสารที่ฉันแนบ
ตอบคำถาม: [QUESTION]

สำหรับแต่ละข้อสรุป:
- ระบุหลักฐานจากเอกสาร
- ระบุหน้าหรือหัวข้อที่สนับสนุน
- หากไม่พบ ให้ตอบว่า "ไม่พบในเอกสาร"

ห้ามสร้างข้อมูลเพื่อเติมช่องว่าง
ห้ามสร้าง citation ที่ตรวจสอบไม่ได้
```

### 5 แยกข้ออ้างจากหลักฐาน (ใช้ตอนทำรายงาน)
```text
ตอบคำถามนี้โดยแยกเป็น 3 ส่วนชัดเจน:

1. CLAIMS — ข้อสรุปของคุณ
2. EVIDENCE — หลักฐานหรือแหล่งที่สนับสนุนแต่ละข้อ
3. UNCERTAINTY — ส่วนที่คุณยังไม่แน่ใจ

อย่าสร้างแหล่งอ้างอิงที่คุณตรวจสอบไม่ได้
คำถาม: [QUESTION]
```

### 6 วิเคราะห์ข้อมูล
```text
วิเคราะห์ dataset นี้เพื่อตอบคำถาม: [QUESTION]

ก่อนวิเคราะห์:
1) ตรวจ schema และ data types
2) ตรวจ missing values และ duplicate records
3) ตรวจค่าผิดปกติที่อยู่นอกช่วงที่เป็นไปได้
4) ระบุข้อจำกัดของข้อมูล

จากนั้น: วิเคราะห์ + เสนอ visualization ที่เหมาะสม
แยกผลเป็น Observation / Interpretation / Limitation
แสดงสูตรหรือ code ที่ใช้ และห้ามสรุป causation จาก correlation
```

### 7 โครงร่างงานนำเสนอ
```text
สร้างโครงร่าง presentation [N] slides
หัวข้อ: [TOPIC]
ผู้ฟัง: [AUDIENCE]
เวลานำเสนอ: [MINUTES] นาที

แต่ละ slide ให้มี:
- Title
- Key message 1 ประโยค
- Bullet ไม่เกิน 3 ข้อ
- Visual suggestion
- Speaker note

เรียงเรื่องแบบ Problem → Evidence → Solution → Action
ถ้า slide ใดมีมากกว่า 1 ประเด็นหลัก ให้เสนอการแยก slide
```

### 8 สร้างภาพประกอบ
```text
Create an illustration for a university lecture slide

Subject: [สิ่งที่ต้องการให้มีในภาพ]
Scene: [ฉาก/บริบท]
Composition: wide shot, negative space on the left for slide title
Style: clean flat illustration, editorial, blue and white palette
Lighting: soft and even
Aspect ratio: 16:9

Constraints:
- no text or logos in the image
- no watermark
```

---
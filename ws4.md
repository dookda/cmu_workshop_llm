
<a name="กิจกรรม-4"></a>
## กิจกรรมที่ 4 — Info graphic + PPTX

---

**ต้องดาวน์โหลด PDF แล้วอัปโหลดเข้า ChatGPT ด้วยตัวเอง** — อย่าแค่วางลิงก์ให้ AI

เหตุผล:
- เว็บไซต์ราชการหลายแห่งบล็อกการเข้าถึงอัตโนมัติ AI จะเปิดไม่ได้
- ถ้า AI เปิดลิงก์ไม่ได้ มันมักจะ **ตอบจากความจำแทน** โดยไม่บอก → ได้ตัวเลขที่ดูน่าเชื่อแต่ผิด
- การอัปโหลดไฟล์จริงคือการทำ **Grounded AI** ตามที่สอนในสไลด์ 18 และ 38

**ไฟล์ต้นฉบับ:** `ข้อมูลเกี่ยวกับ sdgs (17goal 169target 248kpi).pdf`
ที่ http://pad.moi.go.th/images/form-download/

> 📌 หมายเหตุเรื่องตัวเลข: กรอบ SDGs สากลมี **17 Goals / 169 Targets** ส่วนจำนวนตัวชี้วัดต่างกันตามแหล่ง (UN global framework ระบุ 231 ตัวชี้วัดที่ไม่ซ้ำ ขณะที่เอกสารฉบับนี้ระบุ 248) — **ให้ยึดตัวเลขจากไฟล์ที่อัปโหลด** และเป็นตัวอย่างที่ดีมากสำหรับสอนเรื่องการตรวจสอบแหล่งข้อมูล

---

## ภาพรวม Workflow

```text
PDF ต้นฉบับ
   ↓ ① อัปโหลด + สรุปแบบ Grounded
สรุปที่ตรวจสอบได้
   ↓ ② สกัดโครงสร้างเป็น JSON
ข้อมูลที่เครื่องอ่านได้
   ↓ ③ ออกแบบ Infographic
ภาพ 1 ชิ้น
   ↓ ④ สร้างสไลด์ PPTX
ไฟล์ .pptx ที่แก้ไขต่อได้
   ↓ ⑤ ตรวจสอบ
งานที่ส่งได้จริง
```

---

## ① สรุป PDF แบบ Grounded

อัปโหลดไฟล์ แล้วก๊อบ Prompt นี้:

```text
ฉันแนบเอกสาร SDGs ของกรมการปกครองมาให้

สรุปเอกสารนี้โดยใช้ข้อมูลจากไฟล์เท่านั้น แยกเป็น 5 ส่วน:

1. ภาพรวมโครงสร้าง — มีกี่ Goal กี่ Target กี่ตัวชี้วัด (ระบุตัวเลขตามที่เอกสารเขียนไว้จริง)
2. ชื่อ Goal ทั้งหมด พร้อมหมายเลข
3. การจัดกลุ่ม Goal ตามมิติ (ถ้าเอกสารมีการจัดกลุ่มไว้)
4. ประเด็นที่เกี่ยวข้องกับบทบาทของกรมการปกครอง
5. คำศัพท์เฉพาะที่ควรรู้ พร้อมนิยามจากเอกสาร

ข้อกำหนด:
- ใช้เฉพาะเนื้อหาในไฟล์ ห้ามเติมความรู้ภายนอก
- ทุกตัวเลขให้ระบุว่าอยู่หน้าไหนของเอกสาร
- ถ้าข้อมูลใดไม่มีในไฟล์ ให้เขียนว่า "ไม่พบในเอกสาร"
```

**เช็คก่อนไปต่อ:** ถ้า ChatGPT ตอบโดยไม่อ้างหน้าเลย แปลว่าอาจตอบจากความจำ ให้ถามย้ำ:
```text
ยืนยันอีกครั้ง ข้อมูลข้างต้นมาจากไฟล์ที่ฉันแนบทั้งหมดใช่หรือไม่
ระบุหน้าที่พบของแต่ละตัวเลข ถ้าหาไม่เจอในไฟล์ให้บอกตรง ๆ
```

---

## ② สกัดโครงสร้างเป็น JSON

ขั้นนี้สำคัญ เพราะ JSON เอาไปสร้างทั้ง Infographic และ PPTX ได้โดยไม่ต้องพิมพ์ซ้ำ

```text
จากเอกสารที่แนบ สกัดข้อมูลออกมาเป็น JSON ตาม schema นี้

{
  "framework": "SDGs",
  "source": "ชื่อเอกสารและหน่วยงาน",
  "summary": {
    "goals": ตัวเลข,
    "targets": ตัวเลข,
    "indicators": ตัวเลข
  },
  "goals": [
    {
      "number": 1,
      "title_th": "",
      "title_en": "",
      "dimension": "People / Planet / Prosperity / Peace / Partnership",
      "key_targets": ["", ""]
    }
  ]
}

ข้อกำหนด:
- ตอบเป็น JSON อย่างเดียว ไม่ต้องมีคำอธิบายนำหรือปิดท้าย
- ถ้าฟิลด์ใดไม่มีข้อมูลในเอกสาร ให้ใส่ค่าเป็น null
- ห้ามเดาชื่อ Goal จากความรู้ทั่วไป ให้ใช้ชื่อตามเอกสาร
```

**ตรวจ:** เปิดดู JSON แล้วสุ่มเช็ค 3 Goal เทียบกับ PDF ด้วยตา

---

## ③ สร้าง Infographic

### 3.1 เลือกโครงสร้างก่อนสั่งสร้างภาพ

```text
จากข้อมูล SDGs ที่สกัดมา ฉันจะทำ infographic 1 ชิ้นสำหรับนักศึกษาปริญญาตรี

เสนอโครงสร้างการนำเสนอ 3 แบบที่เป็นไปได้
สำหรับแต่ละแบบให้ระบุ:
- ชื่อโครงสร้าง (เช่น Hierarchy, Grid, Cycle)
- เหมาะกับการสื่อสารประเด็นอะไร
- ข้อจำกัด

จากนั้นแนะนำแบบที่ดีที่สุด พร้อมเหตุผล
```

> โครงสร้างที่มักเหมาะกับ SDGs: **Grid 17 ช่อง** (เห็นครบ) · **Hierarchy** (Goal → Target → KPI) · **5 Dimensions** (จัดกลุ่ม 5P)

### แบบที่ 1 — พีระมิดโครงสร้าง 3 ระดับ

```text
Create a clean infographic for a university lecture slide

SUBJECT: three-level pyramid showing the SDGs framework hierarchy
LEVELS: top level "17 Goals", middle level "169 Targets", bottom level "Indicators"
STYLE: flat vector, editorial, blue and white palette, rounded corners
TYPOGRAPHY: very large numbers with short labels underneath
COMPOSITION: centered, generous white space, clear separation between levels
ASPECT RATIO: 16:9
CONSTRAINTS: no logos, no watermark, no small unreadable text, no decorative clutter
```


### แบบที่ 2 — การ์ดเปล่า 17 ช่อง

เหมาะกับ: ให้เห็นครบทั้ง 17 เป้าหมายในภาพเดียว

```
Create a clean infographic showing all 17 SDG goals as a grid

LAYOUT: 6 columns x 3 rows grid of rounded square cards
EACH CARD: large goal number at the top, short label below, simple line icon
STYLE: flat vector, minimal, consistent icon weight across all cards
COLOR: white background, blue accent tones, each card slightly different shade
ASPECT RATIO: 16:9
CONSTRAINTS: no logos, no watermark, keep all text large enough to read on a projector
```

>แบบนี้ AI มักสะกดชื่อเป้าหมายผิด — แนะนำให้สร้างเป็น การ์ดเปล่าที่มีแค่หมายเลข แล้วพิมพ์ชื่อทับใน Canva

### แบบที่ 3 — จัดกลุ่มตาม 5P 

เหมาะกับ: ทำให้ 17 เป้าหมายจำง่ายขึ้นด้วยการจัดหมวด


```
Create a clean infographic grouping the SDGs into five dimensions

GROUPS: People, Planet, Prosperity, Peace, Partnership
LAYOUT: five horizontal bands, each band shows its dimension name and the goal numbers it contains
STYLE: flat vector editorial, blue and white palette, rounded corners
EMPHASIS: dimension names should be the most prominent text
ASPECT RATIO: 16:9
CONSTRAINTS: no logos, no watermark, no small text
```

>ข้อมูลสำหรับกรอกเอง: People = 1–5 · Planet = 6, 12–15 · Prosperity = 7–11 · Peace = 16 · Partnership = 17


### แบบที่ 4 — เจาะลึกเป้าหมายเดียว

เหมาะกับ: งานที่ต้องนำเสนอ Goal ใด Goal หนึ่ง

```
Create a clean infographic explaining one SDG goal in depth

SUBJECT: SDG Goal [ใส่หมายเลขและชื่อ]
STRUCTURE: left side shows the goal statement, right side shows 3 to 4 key targets as a vertical list
STYLE: flat vector editorial, blue and white palette
COMPOSITION: leave negative space at the top for a slide title
ASPECT RATIO: 16:9
CONSTRAINTS: no logos, no watermark, no text inside icons
```

ทางเลือกที่ตัวเลขไม่มีทางผิด (แนะนำที่สุด)

โมเดลสร้างภาพสะกดตัวเลขและข้อความผิดบ่อยมาก ถ้างานต้องแม่นยำ ใช้ Mermaid แทน:

```
สร้างโค้ด Mermaid flowchart แสดงโครงสร้าง SDGs แนวตั้ง 4 ระดับ

ระดับ 1: SDGs เป้าหมายการพัฒนาที่ยั่งยืน
ระดับ 2: 17 Goals
ระดับ 3: 169 Targets
ระดับ 4: ตัวชี้วัดตามเอกสารอ้างอิง

ใช้โทนสีน้ำเงินไล่เฉดจากเข้มไปอ่อน
ตอบเป็นโค้ด Mermaid อย่างเดียว ไม่ต้องมีคำอธิบาย
```


Prompt แก้ภาพต่อ (ใช้หลังได้ภาพแรก)


```
เก็บองค์ประกอบและสไตล์เดิมไว้ แต่แก้ตามนี้
- เพิ่มพื้นที่ว่างด้านบนสำหรับวางหัวข้อสไลด์
- ทำตัวเลขให้ใหญ่ขึ้นอีกประมาณ 30 เปอร์เซ็นต์
- ลดรายละเอียดตกแต่งที่ไม่จำเป็นลง
```


### 3.3 ทางเลือกที่ควบคุมได้มากกว่า

| เครื่องมือ | เหมาะกับ | ข้อดี |
|---|---|---|
| **Napkin AI** | แปลงข้อความเป็น diagram | ข้อความคมชัด แก้ไขได้ทีละองค์ประกอบ |
| **Canva Magic Studio** | Infographic ที่ต้องคุมแบรนด์ | มี template และแก้ข้อความง่าย |
| **ChatGPT + Mermaid** | แผนภาพลำดับชั้น | เป็นโค้ด ตรวจสอบและแก้ได้ 100% |

**Prompt สำหรับ Mermaid (ตัวเลขไม่มีทางผิด):**
```text
สร้างโค้ด Mermaid diagram แสดงโครงสร้าง SDGs
ระดับที่ 1: SDGs
ระดับที่ 2: 17 Goals
ระดับที่ 3: 169 Targets
ระดับที่ 4: 248 Indicators

ใช้ flowchart แนวตั้ง ตอบเป็นโค้ด Mermaid อย่างเดียว
```

---

## ④ สร้างสไลด์ PPTX

### วิธีที่ 1 — ให้ ChatGPT สร้างไฟล์ .pptx ให้เลย (ต้องเปิด Data Analysis)

```text
จาก JSON ที่สกัดไว้ ให้สร้างไฟล์ PowerPoint (.pptx) ด้วย python-pptx

โครงสไลด์ 8 หน้า:
1. หน้าปก: SDGs คืออะไร
2. โครงสร้าง 3 ระดับ: Goals / Targets / Indicators พร้อมตัวเลข
3-7. Goal แบ่งตาม 5 มิติ (People Planet Prosperity Peace Partnership) มิติละ 1 สไลด์
8. บทบาทของหน่วยงานท้องถิ่นและสรุป

ข้อกำหนดการออกแบบ:
- ขนาด 16:9
- ธีมสีขาว-น้ำเงิน ตัวอักษรอ่านง่าย
- แต่ละสไลด์มีหัวข้อ 1 บรรทัด และ bullet ไม่เกิน 5 ข้อ
- ใส่ speaker notes ทุกสไลด์
- ใช้ฟอนต์ที่รองรับภาษาไทย

สร้างไฟล์แล้วให้ฉันดาวน์โหลด
```

**ปัญหาที่เจอบ่อยและวิธีแก้:**

| อาการ | วิธีแก้ |
|---|---|
| ภาษาไทยเป็นสี่เหลี่ยม □□□ | สั่งเพิ่ม: `ใช้ฟอนต์ Sarabun หรือ Noto Sans Thai และฝังฟอนต์ในไฟล์` |
| ข้อความล้นกรอบ | สั่ง: `จำกัด bullet ไม่เกิน 5 ข้อ ข้อละไม่เกิน 15 คำ` |
| สไลด์เปล่าท้ายไฟล์ | สั่ง: `ลบ layout ที่ไม่ได้ใช้ออก` |

### วิธีที่ 2 — สร้างเองด้วย python-pptx (คุมได้เต็มที่)

ให้ ChatGPT สร้าง outline เป็น JSON ก่อน แล้วรันสคริปต์นี้เอง:

```python
from pptx import Presentation
from pptx.util import Inches, Pt
from pptx.dml.color import RGBColor
import json

# outline.json มาจากขั้นที่ 2 หรือให้ ChatGPT สร้างตาม schema นี้
# [{"title": "...", "bullets": ["...", "..."], "notes": "..."}]
slides = json.load(open("outline.json", encoding="utf-8"))

BLUE = RGBColor(0x1B, 0x4F, 0x8A)
FONT = "Sarabun"          # ต้องติดตั้งฟอนต์ในเครื่องก่อน

prs = Presentation()
prs.slide_width  = Inches(13.333)   # 16:9
prs.slide_height = Inches(7.5)

for s in slides:
    slide = prs.slides.add_slide(prs.slide_layouts[1])

    # หัวข้อ
    title = slide.shapes.title
    title.text = s["title"]
    p = title.text_frame.paragraphs[0]
    p.font.name = FONT
    p.font.size = Pt(34)
    p.font.bold = True
    p.font.color.rgb = BLUE

    # เนื้อหา
    body = slide.placeholders[1].text_frame
    body.clear()
    for i, b in enumerate(s["bullets"]):
        para = body.paragraphs[0] if i == 0 else body.add_paragraph()
        para.text = b
        para.font.name = FONT
        para.font.size = Pt(20)
        para.level = 0

    # speaker notes
    slide.notes_slide.notes_text_frame.text = s.get("notes", "")

prs.save("sdgs_summary.pptx")
print("saved: sdgs_summary.pptx")
```

> 💡 ฟอนต์ไทยฟรีที่ใช้ได้: **Sarabun** และ **Noto Sans Thai** จาก Google Fonts
> ถ้าเปิดไฟล์ในเครื่องที่ไม่มีฟอนต์ ตัวอักษรจะเพี้ยน → แนะนำ export เป็น PDF ตอนนำเสนอจริง

### วิธีที่ 3 — ผ่าน Canva / Gamma
ให้ ChatGPT สร้าง outline เป็น Markdown แล้ว import เข้า Canva หรือ Gamma
ข้อดี: ดีไซน์สวยกว่า · ข้อเสีย: แก้โครงสร้างทีหลังยากกว่า

---

## ⑤ ตรวจสอบก่อนใช้งาน 

```text
ตรวจสอบสไลด์ที่สร้างขึ้นเทียบกับเอกสาร PDF ต้นฉบับที่ฉันแนบไว้

สำหรับแต่ละสไลด์ ให้ระบุ:
1. ตัวเลขทุกตัวตรงกับเอกสารหรือไม่ ถ้าไม่ตรงให้ชี้ว่าต่างอย่างไร
2. มีข้อความใดที่ไม่ได้มาจากเอกสารแต่คุณเติมเข้าไปเอง
3. มีประเด็นสำคัญในเอกสารที่ยังไม่ได้ขึ้นสไลด์

ตอบเป็นตาราง และห้ามแก้ไฟล์จนกว่าฉันจะยืนยัน
```

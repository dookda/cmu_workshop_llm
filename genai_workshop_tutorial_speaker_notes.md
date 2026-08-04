# Tutorial & Speaker Notes
## Workshop: Generative AI for University Students (3 ชั่วโมง, 13.00–16.30 น.)

> ใช้คู่กับสไลด์ Canva ธีม White-Blue / Rounded Corner / Flat Design
> โครงสร้าง: Slide = key message | เอกสารนี้ = speaker notes + ภาพประกอบ + ขั้นตอน hands-on
> วิธีใส่ Speaker Notes ใน Canva: เปิดสไลด์ → คลิก "Notes" ที่แถบด้านล่าง → วางข้อความจากเอกสารนี้

---

## กำหนดการโดยสรุป

| เวลา | Session | สไลด์ที่เกี่ยวข้อง |
|---|---|---|
| 13.00–13.15 | 1. Introduction to AI | 3–6 |
| 13.15–13.35 | 2. Understanding LLMs | 7–13 |
| 13.35–13.55 | 3. Capabilities & Limitations | 14–17 |
| 13.55–14.15 | 4. Choosing the Right AI Tool | 18–19 |
| 14.15–14.45 | 5. AI for Learning (+hands-on) | 20–22 |
| 14.45–15.00 | Coffee Break | 23 |
| 15.00–15.45 | 6. Prompt Engineering Workshop | 24–27 |
| 15.45–16.05 | 7. AI for Data Analysis (+hands-on) | 28–30 |
| 16.05–16.25 | 8. AI for Content Creation | 31–32 |
| 16.25–16.30 | 9. Wrap-up & Q&A | 33 |

---

# Speaker Notes รายสไลด์

## Slide 1 — Title: Generative AI for University Students
**Note:** ทักทาย แนะนำตัว บอกเวลา 3 ชั่วโมง (13.00–16.30) และรูปแบบ: ฟังสั้น + ลงมือทำจริง + ตรวจสอบผลลัพธ์อย่างมีวิจารณญาณ ขอให้นักศึกษาเตรียมโน้ตบุ๊กและบัญชี AI อย่างน้อย 1 ตัว (ChatGPT / Claude / Gemini)
**ภาพ:** Hero image สไตล์ flat illustration "students + AI"
- unDraw (ฟรี, ปรับสีเป็นโทนน้ำเงินได้): https://undraw.co/illustrations (ค้น "artificial intelligence", "studying")
- Storyset: https://storyset.com/ (ค้น "education technology")

## Slide 2 — Objectives & Agenda
**Note:** เป้าหมาย 3 ข้อ: (1) เข้าใจว่า Generative AI ทำงานอย่างไรและมีข้อจำกัดอะไร (2) ใช้ AI ช่วยเรียน วิเคราะห์ข้อมูล และสร้างงานได้จริง (3) ตรวจสอบผลลัพธ์เป็น ไม่เชื่อ AI แบบไม่มีเงื่อนไข เดินตาราง agenda เร็ว ๆ ชี้ว่ามี hands-on 3 ช่วงและ break 15 นาที
**ภาพ:** icon set แบบ flat (target, clock, checklist) — SVG Repo: https://www.svgrepo.com/

## Slide 3 — Artificial Intelligence คืออะไร
**Note:** เน้นว่า AI ≠ ChatGPT เท่านั้น AI เป็นสาขากว้างครอบคลุมระบบแนะนำสินค้า การตรวจจับวัตถุ การแปลภาษา ฯลฯ ถามเปิด: "หนึ่งสัปดาห์ที่ผ่านมา ใช้ AI ทำอะไรบ้าง และงานไหนที่เชื่อคำตอบทันทีโดยไม่ตรวจ?" (2–3 นาที)
**ภาพ:** collage ตัวอย่างการใช้ AI ในชีวิตประจำวัน — Unsplash: https://unsplash.com/s/photos/artificial-intelligence

## Slide 4 — AI → ML → DL → Generative AI
**Note:** อธิบายเป็นวงซ้อน: AI กว้างสุด → ML เรียนรู้จากข้อมูลแทนการเขียนกฎทุกอย่าง → DL ใช้โครงข่ายประสาทหลายชั้น → Generative AI สร้างเนื้อหาใหม่ (text/image/audio/video/code) Key takeaway: "ChatGPT ≠ all of AI"
**ภาพ:** ให้ Canva วาด nested circles diagram หรือใช้ diagram จากเนื้อหา (แนะนำวาดเองใน Canva ด้วย shape มุมโค้ง โทนน้ำเงินไล่เฉด)

## Slide 5 — Predictive AI vs Generative AI
**Note:** Predictive: Input → Model → Prediction (เช่น ภาพดาวเทียม → ประเภทการใช้ที่ดิน) / Generative: Prompt → Model → New Content จุดสำคัญ: Generative AI ไม่ได้ "ค้นคำตอบ" แต่ "สร้างผลลัพธ์ใหม่" จากรูปแบบที่เรียนรู้ — เป็น setup สำหรับเรื่อง hallucination
**ภาพ:** two-column comparison diagram (สร้างใน Canva)

## Slide 6 — AI เปลี่ยนวิธีทำงานอย่างไร
**Note:** โชว์ workflow ใหม่: Human → Intent/Data → AI Assistant → Draft → Human Review → Final เน้นคำว่า "Co-pilot ไม่ใช่ Autopilot" — AI ช่วยคิดช่วยร่าง แต่มนุษย์ตรวจและรับผิดชอบ
**ภาพ:** flat illustration "human + robot collaboration" — Storyset: https://storyset.com/search?q=collaboration

## Slide 7 — Large Language Model คืออะไร
**Note:** LLM เรียนรู้รูปแบบภาษาจากข้อมูลมหาศาลเพื่อประมวลผลและสร้างลำดับ token ใช้ได้กับ Q&A, สรุป, แปล, เขียน, โค้ด, reasoning ย้ำว่า session นี้จะเข้าใจ "ข้างใน" แบบ conceptual ไม่ลงสมการ
**ภาพ:** LLM pipeline diagram: Prompt → Tokenizer → Embeddings → Transformer → Next token → Response

## Slide 8 — Token & Embedding
**Note:** LLM ไม่เห็นข้อความแบบมนุษย์ แต่แบ่งเป็น token แล้วแทนด้วยเวกเตอร์ (embedding) Demo แนะนำ: เปิด OpenAI Tokenizer (https://platform.openai.com/tokenizer) พิมพ์ประโยคไทย/อังกฤษให้เห็นการแบ่ง token จริง อธิบาย embedding ว่าทำให้ "cat" ใกล้ "dog" ใน vector space → โมเดลเข้าใจความหมาย ไม่ใช่แค่ตัวสะกด
**ภาพ:** semantic space scatter (cat/dog/tiger vs car/bus/truck) — วาดใน Canva

## Slide 9 — Transformer & Attention
**Note:** ตัวอย่าง: "นักศึกษาวางหนังสือไว้บนโต๊ะ เพราะ **มัน** หนัก" — โมเดลต้องใช้บริบทตัดสินว่า "มัน" คืออะไร นี่คือหน้าที่ของ Attention ไม่ต้องสอนสมการ ชี้แหล่งอ่านต่อ
**ภาพ/ลิงก์:** The Illustrated Transformer: https://jalammar.github.io/illustrated-transformer/ (มีภาพ attention สวยมาก ใช้ screenshot ประกอบได้โดยอ้างอิงที่มา) | Paper: https://arxiv.org/abs/1706.03762

## Slide 10 — LLM สร้างคำตอบอย่างไร
**Note:** วนลูป: Predict next token → Append → Predict อีก จุดสำคัญที่สุดของ session: "LLM สร้างข้อความจากความน่าจะเป็น ไม่ได้เปิดฐานข้อมูลความจริงมาคัดลอก" — ประโยคนี้คือรากของ hallucination ให้นักศึกษาจดไว้
**ภาพ:** next-token loop diagram (Canva) — ทำเป็นวงกลมลูกศรวน

## Slide 11 — Context Window
**Note:** Context = ทุกอย่างที่โมเดลเห็นตอนตอบ: prompt, ประวัติสนทนา, ไฟล์แนบ, instructions "Context ไม่ชัด → ผลลัพธ์ไม่ตรง" — เป็นสะพานไปสู่ Prompt Engineering ช่วงบ่าย
**ภาพ:** icon "window/frame" + เลเยอร์ข้อมูล (Canva shapes)

## Slide 12 — Multimodal AI
**Note:** AI รุ่นใหม่รับ text/image/audio/video/files → ตอบได้หลายรูปแบบ การใช้งานเปลี่ยนจาก "Chatbot" เป็น "AI Workspace" Demo สั้น: อัปโหลดภาพหนึ่งภาพให้ AI อธิบาย
**ภาพ:** multimodal input/output diagram

## Slide 13 — เลือกแพลตฟอร์ม: ไม่มี "ดีที่สุด" มีแต่ "เหมาะที่สุด"
**Note:** เดินเร็ว ๆ: ChatGPT อเนกประสงค์ / Claude เด่นเอกสารยาว+artifacts / Gemini อยู่ใน Google ecosystem / Copilot อยู่ใน Microsoft 365 / NotebookLM เน้น source-grounded learning คำถามที่ถูก: "AI ตัวไหนเหมาะกับงานนี้ ภายใต้ข้อมูลและข้อจำกัดของเรา?" หมายเหตุ: ตรวจฟีเจอร์ล่าสุดก่อนวันอบรมเพราะเปลี่ยนเร็ว
**ภาพ:** logo grid (ใช้ screenshot หน้าเว็บทางการใกล้วันอบรม): https://chatgpt.com/ | https://claude.ai/ | https://gemini.google.com/ | https://copilot.microsoft.com/ | https://notebooklm.google/

## Slide 14 — AI เก่งอะไร
**Note:** Brainstorm, สรุป, ปรับระดับคำอธิบาย, ร่างเอกสาร, ตรวจภาษา, ช่วยโค้ด, สำรวจข้อมูล, สร้างภาพ Insight: คุณค่าสูงสุดคือ "จากหน้ากระดาษเปล่า → ร่างแรก" แต่ไม่ได้ลบขั้นตอนตรวจสอบ
**ภาพ:** capability map (Understand / Create / Transform) — Canva diagram

## Slide 15 — Fluent ≠ Correct & Hallucination
**Note:** ข้อความอ่านลื่น ดูวิชาการ มีตัวเลข ≠ ถูกต้อง Hallucination = สร้างข้อมูลผิดแบบดูน่าเชื่อ: ชื่อบทความปลอม, DOI ปลอม, อ้างกฎหมายผิดมาตรา สาเหตุ: เป้าหมายของโมเดลคือสร้างข้อความสอดคล้องบริบท ไม่ใช่ตรวจข้อเท็จจริง Demo แนะนำ (Case Study 2): ให้ AI สร้าง references หัวข้อเฉพาะทาง แล้วให้นักศึกษาลองเปิด DOI จริง — "Citation-looking text is not evidence"
**ภาพ:** สมการภาพ "Fluent + Confident ≠ Verified" ตัวใหญ่กลางสไลด์

## Slide 16 — Verification Workflow
**Note:** AI Output → ระบุ factual claims → หาหลักฐาน → ตรวจ primary source → เปรียบเทียบ → Accept/Revise/Reject สิ่งที่ต้องตรวจพิเศษ: ตัวเลข วันที่ ชื่อคน กฎหมาย งานวิจัย citation ข้อมูลสุขภาพ/การเงิน แนะนำ Verification Pyramid + เกณฑ์ Currency/Authority/Accuracy/Purpose
**ภาพ:** pyramid diagram (Canva) — AI Answer → Citation → Original Publication → Primary Source → Cross-validation

## Slide 17 — Bias, Privacy & Academic Integrity
**Note:** Bias: ข้อมูลฝึกมีอคติทางสังคม/ภูมิศาสตร์/ภาษา — ถามเสมอ "ใครถูกนำเสนอ ใครถูกละเลย?" Privacy: ก่อน paste ถามว่า "ฉันมีสิทธิ์นำข้อมูลนี้เข้า AI หรือไม่?" ห้าม: รหัสผ่าน, API key, ข้อมูลส่วนบุคคล, งาน NDA Integrity: AI ช่วยอธิบาย/feedback ได้ แต่นักศึกษารับผิดชอบผลงานสุดท้ายและต้องทำตามนโยบายรายวิชา
**ภาพ:** 3-column icon layout (scale/lock/graduation cap) — SVG Repo

## Slide 18 — เริ่มจาก Task ไม่ใช่ Tool
**Note:** อย่าถาม "วันนี้ใช้ ChatGPT ทำอะไรดี" ให้ถาม "ต้องทำอะไร ใช้ข้อมูลอะไร" Framework: TASK → INPUT → OUTPUT → RISK/PRIVACY → NEED SOURCES? → CHOOSE TOOL แบ่งงาน 5 ประเภท: General / Source-grounded / Data Analysis / Office / Visual
**ภาพ:** vertical decision flow (Canva)

## Slide 19 — Decision Matrix & Multi-tool Workflow
**Note:** ตัวอย่าง: สรุปบทเรียน → ต้องการ file upload + grounding | วิเคราะห์ Excel → data analysis + charts | ทำสไลด์ → presentation generation งานเดียวใช้หลาย AI ได้: PDF → NotebookLM สรุป → General AI ทำ outline → Design AI ทำสไลด์ → Human review Hands-on สั้น (3 นาที): ให้แต่ละคนระบุงานที่ทำบ่อย 1 งานแล้วตอบ 5 คำถาม (input/output/source/sensitive/tool)
**ภาพ:** multi-tool pipeline diagram

## Slide 20 — AI ช่วยให้เรียนรู้ ≠ AI ทำแทน
**Note:** เทียบ 2 workflow: Weak = Question → AI → Copy | Better = Attempt → AI hint → Reasoning → Feedback → Understanding อภิปราย (Case Study 1): workflow ไหนสนับสนุนการเรียนรู้ เพราะอะไร ชี้ว่าแบบแรกได้คะแนนระยะสั้น แบบหลังได้ความเข้าใจที่อยู่ถึงห้องสอบ
**ภาพ:** side-by-side flow comparison

## Slide 21 — AI เป็น Explainer & Socratic Tutor
**Note:** โชว์ prompt 2 แบบ: (1) Explainer: "อธิบาย [หัวข้อ] สำหรับปี 1 + ตัวอย่างชีวิตจริง + คำถามตรวจความเข้าใจ 3 ข้อ" (2) Socratic: "อย่าเฉลยทันที ถามทีละคำถาม ให้ hint ก่อน เฉลยเมื่อฉันขอ" เทคนิคเสริม: อธิบาย 3 ระดับ (ง่ายมาก/ป.ตรี/เทคนิค), Teach-back แบบ Feynman
**ภาพ:** screenshot ตัวอย่างบทสนทนา tutor mode จริง (จับภาพก่อนวันอบรม)

## Slide 22 — Hands-on #1: AI Study Pack (15 นาที)
**Note:** ให้นักศึกษาใช้เอกสารเรียนของตัวเอง 1 ไฟล์ ทำ 5 อย่าง: (1) Summary แบบกำหนดเป้าหมาย (แนวคิด/ศัพท์/สิ่งที่มักสับสน/คำถามที่น่าจะออกสอบ) (2) อธิบาย concept ยาก 1 เรื่อง (3) Flashcards 5 ใบ (4) Quiz 5 ข้อแบบถามทีละข้อ (5) Tutor mode อย่างน้อย 3 รอบ Deliverable: One-page AI Study Pack เดินดูรอบห้อง ช่วยคนที่ติด
**ภาพ:** "TRY THIS" card layout พร้อม prompt สั้น + timer icon

## Slide 23 — Coffee Break (14.45–15.00)
**Note:** พัก 15 นาที บอกว่าช่วงบ่ายเป็น workshop เข้มข้น: Prompt Engineering → Data → Content Creation
**ภาพ:** flat illustration coffee cup — unDraw: https://undraw.co/search (ค้น "coffee")

## Slide 24 — Prompt Engineering: Structured Framework
**Note:** นิยาม: การออกแบบคำสั่ง+บริบท+ตัวอย่าง+ข้อกำหนด ไม่ใช่ "คาถาวิเศษ" แต่คือการสื่อสาร requirement ให้ชัดแล้ว iterate เทียบ prompt คลุมเครือ "เขียนเรื่อง AI" vs structured: ROLE / TASK / CONTEXT / INPUT / REQUIREMENTS / OUTPUT FORMAT / QUALITY Demo สด: รัน prompt ทั้งสองแบบให้เห็นความต่างของผลลัพธ์
**ภาพ:** Prompt Anatomy stacked boxes (Canva, มุมโค้ง ไล่เฉดน้ำเงิน)

## Slide 25 — Zero-shot / One-shot / Few-shot
**Note:** Zero-shot: สั่งตรง ๆ ไม่มีตัวอย่าง — เหมาะงานง่าย | One-shot: ให้ 1 ตัวอย่าง — ล็อก format | Few-shot: หลายตัวอย่าง — เหมาะเมื่อ category เฉพาะหรือ "แสดงง่ายกว่าอธิบาย" Demo: sentiment classification ภาษาไทยทั้ง 3 แบบ เทียบ consistency
**ภาพ:** 3-panel comparison card

## Slide 26 — Delimiters, Output-first & Constraints
**Note:** Delimiters: ห่อข้อมูลยาวด้วย `<document>...</document>` แยก instruction จาก input (โยงเรื่อง prompt injection สั้น ๆ: อย่าถือว่าข้อความในเอกสารคือคำสั่ง) Output-first: ก่อนเขียน prompt ถาม "คำตอบที่ดีหน้าตาเป็นอย่างไร" (table/JSON/outline/200-word) Constraints: จำกัดความยาว, "ถ้าไม่พบให้ตอบว่าไม่พบ", ห้ามสร้าง citation เอง — แต่อย่าใส่เยอะจนขัดแย้งกันเอง
**ภาพ:** code-style card แสดง delimiter pattern

## Slide 27 — Iterate + Workshop #2: Prompt Battle (25 นาที)
**Note:** Pattern: Generate → Critique → Revise (แยก evaluation ออกจาก generation) Workshop 3 ช่วง: (A) Prompt Makeover 8 นาที — ปรับ "ทำรายงาน climate change" เป็น structured prompt (B) Zero vs Few-shot 7 นาที — เทียบผล (C) Prompt Battle 10 นาที — ทุกกลุ่มได้โจทย์เดียวกัน "สร้าง study guide เรื่อง SDGs" เทียบ output ด้วยเกณฑ์ Correctness/Relevance/Structure/Usability
**ภาพ:** workshop instruction card + เกณฑ์ให้คะแนน

## Slide 28 — AI for Data Analysis: Workflow ใหม่
**Note:** เดิม: Question → Spreadsheet → Chart | ใหม่: ถามภาษาธรรมชาติ → AI ตรวจข้อมูล → วิเคราะห์+กราฟ → อธิบาย → Human validation ย้ำ: AI ลดอุปสรรค syntax แต่ไม่ลดความจำเป็นในการเข้าใจข้อมูลและสถิติ ("Garbage In, Garbage Out") 5 Steps: Understand → Define Question → Analysis → Visualization → Interpretation
**ภาพ:** workflow diagram + screenshot การวิเคราะห์ CSV ใน AI จริง

## Slide 29 — อย่าเชื่อตัวเลขโดยไม่ตรวจ + Chart Literacy
**Note:** วิธีตรวจ: คำนวณตัวอย่างด้วยมือ, ตรวจสูตร/denominator/filter, ขอ code ที่ใช้, ทำซ้ำด้วยวิธีอื่นเมื่อผลสำคัญ Chart literacy: Bar=เปรียบเทียบ, Histogram=distribution, Scatter=ความสัมพันธ์, Line=เวลา คำถามทอง: "กราฟนี้ทำให้ตีความผิดได้อย่างไร?" Case Study 3: "อ่านหนังสือนาน→คะแนนสูง ดังนั้นเพิ่มชั่วโมงอ่าน=คะแนนเพิ่ม" — ให้นักศึกษาจับผิด (correlation ≠ causation, confounders, sample size)
**ภาพ:** ตัวอย่างกราฟหลอกตา (truncated axis) — สร้างเทียบ before/after ใน Canva

## Slide 30 — Hands-on #3: Data Challenge (15 นาที)
**Note:** แจก student_scores.csv (StudentID, Faculty, StudyHours, Attendance, Midterm, Final) งาน: (1) Data profile (2) ตรวจ missing (3) ค่าเฉลี่ย (4) เปรียบเทียบกลุ่ม (5) กราฟ 1 อัน (6) insight 3 ข้อ (7) limitation 2 ข้อ Deliverable: Chart + 3 Insights + 2 Limitations เตือน: ห้ามสรุป causation จาก correlation
**ภาพ:** dataset preview table + checklist card

## Slide 31 — Content Creation: Pipeline & Presentation
**Note:** อย่าใช้ Prompt → Generate → Submit ให้ใช้ Purpose → Audience → Structure → Generate → Edit → Verify → Design หลัก "One Slide, One Message": ถ้าจำได้อย่างเดียวจากสไลด์นี้ ควรจำอะไร? โชว์ Before/After slide exercise (bullet ยาว 6 ข้อ vs diagram + 1 takeaway) Prompt ตัวอย่าง: outline 8 สไลด์ + key message + speaker note + visual suggestion เรื่อง Problem→Evidence→Solution→Action
**ภาพ:** before/after slide mockup

## Slide 32 — Infographic, Image & Video
**Note:** Infographic: เลือกโครงสร้างตามเนื้อหา (Process/Timeline/Comparison/Cycle) เครื่องมือ: Napkin AI (https://www.napkin.ai/), Canva Magic Studio (https://www.canva.com/magic/) — ตรวจ label/ตัวเลขทุกครั้ง Image prompt: SUBJECT+SCENE+COMPOSITION+STYLE+LIGHTING+RATIO+CONSTRAINTS โชว์ weak "smart city" vs improved prompt Video: อย่าข้าม storyboard — แบ่ง 6 shots ควบคุม consistency ง่ายกว่า prompt เดียวยาว ๆ จริยธรรม: อย่าอ้างภาพ AI เป็นภาพเหตุการณ์จริง เปิดเผยการใช้ AI เมื่อบริบทกำหนด
**ภาพ:** image prompt anatomy card + ตัวอย่างภาพ AI ที่ generate ไว้ล่วงหน้า

## Slide 33 — Wrap-up: 5 Rules & Workflow
**Note:** Workflow ที่ควรจำ: DEFINE → CONTEXT → PROMPT → GENERATE → VERIFY → REFINE → OWN Five Rules: (1) AI is an assistant, not an authority (2) Better context → better output (3) Fluent ≠ Correct (4) Verify important claims (5) You remain responsible ปิดด้วยกรอบ UNESCO: Understand → Apply → Create — วันนี้ผ่าน Understand+Apply แล้ว ก้าวต่อไปคือ Create เปิด Q&A
**ภาพ:** 5 rules card layout + คำว่า "OWN" เน้นตัวใหญ่

---

# ชุดลิงก์ภาพ/ทรัพยากร (ตรวจ license ก่อนใช้)

**Illustration ฟรีสไตล์ flat (ปรับสีน้ำเงินได้):**
- unDraw — https://undraw.co/illustrations
- Storyset — https://storyset.com/
- SVG Repo (icons) — https://www.svgrepo.com/

**ภาพถ่าย:**
- Unsplash — https://unsplash.com/
- Wikimedia Commons — https://commons.wikimedia.org/

**Diagram/Technical (ใช้ screenshot พร้อมอ้างอิง):**
- The Illustrated Transformer — https://jalammar.github.io/illustrated-transformer/
- Attention Is All You Need — https://arxiv.org/abs/1706.03762
- Google ML Crash Course — https://developers.google.com/machine-learning/crash-course
- Stanford AI Index (charts) — https://aiindex.stanford.edu/

**Product screenshots (จับภาพใกล้วันอบรม เพราะ UI เปลี่ยนเร็ว):**
- ChatGPT — https://chatgpt.com/
- Claude — https://claude.ai/
- Gemini — https://gemini.google.com/
- NotebookLM — https://notebooklm.google/
- Microsoft Copilot — https://copilot.microsoft.com/
- Canva Magic Studio — https://www.canva.com/magic/
- Napkin AI — https://www.napkin.ai/
- Gamma — https://gamma.app/

---

# Instructor Checklist (ก่อนวันอบรม)

- [ ] ตรวจบัญชี ChatGPT / Claude / Gemini / NotebookLM ที่จะสาธิต
- [ ] เตรียม PDF ตัวอย่างสำหรับ Hands-on #1 (Session 5)
- [ ] เตรียม student_scores.csv สำหรับ Hands-on #3 (Session 7)
- [ ] เตรียม prompt ที่ทดสอบแล้วว่าให้ผลดี + prompt สาธิตข้อจำกัด (hallucinated citations)
- [ ] จับ screenshot ทุกผลิตภัณฑ์ + เตรียมผลลัพธ์ demo สำรอง (กันเน็ตล่ม)
- [ ] ตรวจทุก URL ในเอกสารนี้
- [ ] ตรวจนโยบายการใช้ AI ของมหาวิทยาลัย/รายวิชา
- [ ] ห้ามใช้ข้อมูลส่วนบุคคลจริงใน demo

# CSV ตัวอย่างสำหรับ Hands-on #3

```csv
StudentID,Faculty,StudyHours,Attendance,Midterm,Final
S001,Science,8,92,78,84
S002,Arts,5,81,69,74
S003,Science,10,96,88,91
S004,Business,4,76,65,70
S005,Arts,7,89,75,80
S006,Business,6,85,72,78
S007,Science,3,70,61,66
S008,Arts,9,94,82,88
```

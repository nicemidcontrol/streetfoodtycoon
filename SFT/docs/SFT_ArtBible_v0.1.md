\
# SFT — Isometric 16-bit Art Bible (v0.1)

> เป้าหมาย: ทำให้ “ทุกชิ้นงาน” ดูเป็นเกมเดียวกันทันที โดยกำหนดกฎเรื่องสเกล, ไทล์, สี, แสงเงา, เส้น, และการ export ให้ชัดเจน

---

## 1) Style Pillars
- **16-bit nostalgia** แต่คมชัด/อ่านง่ายบนมือถือ
- **Isometric (2:1)** มุมมองคลาสสิก สบายตา
- **Readable first**: ทุกอย่างต้องอ่านออกในขนาดมือถือ โดยไม่ต้องซูม
- **Warm street vibe**: ไฟนีออน/ไฟเหลือง, ตลาดกลางคืน, อาหารน่ากิน

---

## 2) Isometric Specs (มาตรฐานหลัก)
### Tile Geometry
- **ฐานไทล์พื้น (Ground tile): 64×32 px** (อัตราส่วน 2:1)
- **Sub-tile:** 32×16 px (ใช้สำหรับรายละเอียดเล็ก/จุดยืน)
- **Grid:** Isometric diamond 2:1 (ไม่ใช้ true 3D perspective)

### Sprite Scale
- **ตัวละคร (Customer/Staff):** สูงประมาณ **48–64 px** (หัวถึงเท้า)
- **รถเข็น/เคาน์เตอร์หลัก:** footprint ประมาณ **2×2 tiles** (128×64 px) เป็นค่าเริ่มต้น
- **ของตกแต่งเล็ก:** 0.5–1 tile
- **ความสม่ำเสมอ:** อย่าผสม scale ต่างกันในฉากเดียวโดยไม่มีเหตุผล

### Anchor / Pivot (สำคัญมาก)
- ทุก sprite ที่ “วางบนพื้น” ให้ตั้ง **origin/pivot ที่จุดสัมผัสพื้นตรงกลาง** (ประมาณกึ่งกลางฐาน)
- สำหรับวัตถุสูง ให้ pivot อยู่ที่ “ฐานสัมผัสพื้น” ไม่ใช่กลางรูป

---

## 3) Camera & Pixel-Perfect Rules (สำหรับ Godot)
- ตั้ง **2D pixel art**: ปิดการกรองภาพ (Filter) ให้หมด
- ใช้ **integer scaling** เท่านั้น (กันเบลอ)
- แนะนำ **ฐานความละเอียด**: 480×270 หรือ 640×360 แล้วคูณขึ้น (2x, 3x, 4x) ตามเครื่อง
- หลีกเลี่ยงการขยับกล้องเป็นทศนิยม (ทำให้ pixel swim)

> Checklist (นำไปตั้งใน Godot Import/Project Settings)
- Texture Import: **Filter OFF**, **Mipmaps OFF**
- Compression: เลือกแบบที่ไม่ทำให้พิกเซลเละ (สำหรับ pixel art ให้ทดสอบ)
- Stretch: **viewport** หรือ **canvas_items** + integer scale

---

## 4) Lighting & Shading Rules
### Light Direction (กฎเดียวทั้งเกม)
- แสงหลักมาจาก **มุมซ้ายบน (North-West)**  
  → ด้านบน/ซ้ายสว่างกว่า, ด้านล่าง/ขวาเข้มกว่า

### Contrast
- ใช้ **3–4 ขั้นเงา** ต่อวัสดุเป็นหลัก (Highlight / Mid / Shadow / Deep shadow)
- หลีกเลี่ยง gradient เรียบ ๆ ยาว ๆ (จะหลุด 16-bit)

### Highlights
- อาหาร/ซอส/น้ำมันทอด ให้มี highlight เล็ก ๆ เพื่อ “น่ากิน”
- โลหะ (หม้อ/กระทะ) ให้ highlight ชัด + ขอบสะท้อน

---

## 5) Linework & Outlines
- ใช้ outline แบบ **selective**:
  - วัตถุที่ต้องเด่น: outline 1 px สีเข้ม
  - รายละเอียดเล็ก: ลด outline หรือใช้สีเข้มของวัสดุแทน
- หลีกเลี่ยงเส้นดำสนิท 100% ทุกจุด (ทำให้แข็ง)
- ขอบด้านที่อยู่ในเงา สามารถใช้ “outline สีเข้มของเงา” แทนดำ

---

## 6) Color Palette & Mood
### Mood
- โทนอุ่น: เหลืองส้ม/ไฟนีออนอ่อน + เงาอมม่วง/น้ำเงิน
- ความอิ่มสี (saturation) **ปานกลาง** เพื่อไม่ล้าตา

### Palette Guidance (ไม่บังคับเลขสี แต่บังคับตรรกะ)
- เลือก palette หลัก ~ **24–40 สี** สำหรับ world
- แยกกลุ่มสี:
  - **Warm lights:** ส้ม/เหลือง
  - **Cool shadows:** น้ำเงิน/ม่วงเข้ม
  - **Food accents:** แดง/เขียวผัก/น้ำตาลทอด
- ทุกชิ้นต้องเช็ค “อ่านค่าใน grayscale” (ถ้าแยกไม่ออก = contrast ยังไม่ดี)

---

## 7) Materials Cheatsheet (สูตรลัด)
- **ไม้:** ลายเสี้ยน 2–3 เส้น + highlight แคบ
- **โลหะ:** highlight แข็ง + เงาลึก + เส้นสะท้อน
- **ผ้า/ผ้ากันเปื้อน:** เงานุ่ม, ไม่ต้อง highlight แข็ง
- **พลาสติกแก้ว:** ขอบ highlight บาง ๆ + เงาภายในเล็กน้อย
- **อาหารทอด:** texture จุด/ปาดแปรงพิกเซล + highlight น้ำมัน

---

## 8) Character Style
- สัดส่วนแบบ chibi-16bit: หัวใหญ่กว่านิดเพื่ออ่านง่าย
- สีผิว/ทรงผม/เสื้อผ้า: เน้นความหลากหลาย แต่คุม palette ให้อยู่ในโทนเกม
- Animation แนะนำขั้นต่ำ:
  - **Walk:** 4–6 frames
  - **Idle:** 2–4 frames (กระพริบ/ขยับเล็กน้อย)
  - **Buy/Interact:** 2–4 frames

---

## 9) Environment & Props
### Scene Composition (ตลาดกลางคืน)
- พื้น: tile ซ้ำได้ + มี variation 3–5 แบบ (กันจำเจ)
- ชิ้นใหญ่ (landmarks): ป้ายไฟ, เสาไฟ, เต็นท์ผ้าใบ
- Props: กล่องลัง, ถังน้ำ, เก้าอี้, ถังขยะ, ป้ายเมนู

### Readability
- อย่าใส่รายละเอียดถี่เท่ากันทั้งฉาก  
  → “โซนโล่ง” ทำให้ของสำคัญเด่นขึ้น

---

## 10) UI Style (ให้ไปทางเดียวกับโลกเกม)
- กล่อง UI มุมมนเล็กน้อย + เงา 1–2 ขั้น
- ปุ่ม: สีสดขึ้น 10–20% จากพื้นหลังเพื่อเด่น
- Icons: พิกเซลอาร์ต 16–24 px (แล้วคูณสเกลในเกม)

### Typography
- ใช้ฟอนต์ pixel ที่อ่านไทยได้ (ถ้ามี) หรือใช้ฟอนต์อ่านง่ายแล้วทำ “pixel-ish” ผ่านสเกล
- ขนาดตัวอักษรในมือถือ: เน้นอ่านง่ายก่อนความเท่

---

## 11) File Formats & Export
- Sprite/Tile: **PNG 32-bit** (มี alpha)
- หลีกเลี่ยง JPEG (ทำให้พิกเซลแตก)
- Export scale: ทำที่ **1x** แล้วให้เกมคูณสเกล (หรือทำ 2x แบบ pixel-perfect)

### Naming Convention (แนะนำ)
- Characters: `chr_customer_01_walk_ne_000.png`
- Props: `prop_trashcan_a.png`
- Tiles: `tile_ground_a_01.png`
- UI: `ui_btn_primary.png`, `ui_icon_coin.png`

---

## 12) “Do / Don’t” Quick List
**DO**
- ยึด tile 64×32 ให้เป็นฐาน
- แสงมุมซ้ายบนอย่างเดียวทั้งเกม
- ทำ variation ของพื้น/ผนัง 3–5 แบบ
- เช็ค readability ในมือถือจริงเสมอ

**DON’T**
- ผสม perspective หลายแบบในฉากเดียว
- ใช้ gradient เรียบยาว ๆ
- ขยับกล้อง/วัตถุแบบทศนิยมจน pixel swim
- ใส่รายละเอียดแน่นทุกจุดจนอ่านไม่ออก

---

## 13) Next Art Deliverables (หลังจากไฟล์นี้)
- `SFT_TileSet_Spec_v0.1.md` (รายการไทล์ที่ต้องมี + จำนวน)
- `SFT_Character_Sheet_v0.1.md` (ชุดตัวละครขั้นต่ำ + สี/variant)
- `SFT_UI_Kit_v0.1.md` (ปุ่ม/กรอบ/ไอคอนที่ต้องทำ)

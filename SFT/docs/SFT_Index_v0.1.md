# SFT — Project Index (v0.1)

> จุดประสงค์: เป็น “หน้าเดียวจบ” สำหรับลิงก์ไฟล์, สถานะ, และแผนผังแชท  
> แนวคิด: ไฟล์คือความจริงล่าสุด (single source of truth) แชทคือพื้นที่ทำงานรายระบบ

---

## 1) Current Status (อัปเดตสั้น ๆ)
- วันที่อัปเดตล่าสุด: 2025-12-23 (Asia/Bangkok)
- สถานะโปรเจกต์: Pre-Production → กำลังล็อกสโคป + สเปคภาพ/ระบบ
- MVP Target: 1 โซน / 3 เมนู / 3 สายอัปเกรด / offline earnings / local save

---

## 2) Key Documents (Source of Truth)
- **GDD (1-page):** `SFT/docs/SFT_GDD_v0.1.md`
- **Milestones:** `SFT/docs/SFT_Milestones_v0.1.md`
- **Art Bible:** `SFT/docs/SFT_ArtBible_v0.1.md`
- **Decision Log:** `SFT/docs/SFT_Decisions_v0.1.md`

---

## 3) Design & Data
- **Economy Starter (CSV):** `SFT/design/SFT_EconomyStarter_v0.1.csv`

---

## 4) Firebase
- **Analytics Event Catalog (JSON):** `SFT/firebase/firebase_events_v0.1.json`

---

## 5) Chat Map (ใช้เปิดแชทใหม่/กลับไปถาม)
### HQ / Summary
- `SFT – Master Plan & Milestone` (ภาพรวม/ล็อกสโคป)

### Systems (หนึ่งระบบต่อหนึ่งแชท)
- `SFT - GDD Core Loop & Progression`
- `SFT - Economy & Balancing`
- `SFT - Isometric Art Bible`
- `SFT - Godot Project Setup`
- `SFT - NPC Customer AI & Pathing`
- `SFT - UI/UX & HUD`
- `SFT - Save/Load Local`
- `SFT - Offline Earnings`
- `SFT - Firebase Analytics & Events`
- `SFT - Remote Config & Live Balance`
- `SFT - Monetization (Rewarded Ads only)`
- `SFT - QA Checklist & Bug Triage`
- `SFT - Android Build & Release Pipeline`
- `SFT - Playtest Feedback & Iteration`
- `SFT - Content Pipeline (Menus/Zones)`

---

## 6) “เมื่อไหร่ควรทำเป็นไฟล์” (กติกาเร็ว ๆ)
ทำเป็นไฟล์ทันทีถ้า:
- โค้ดยาว/หลายไฟล์/ต้องคอมไพล์
- ตารางตัวเลข/บาลานซ์/curve
- มาตรฐาน (art rules / naming / schema)
- ต้องอ้างอิงซ้ำหรือมีเวอร์ชัน

---

## 7) Next Files To Create (แนะนำลำดับ)
1) `SFT/docs/SFT_TileSet_Spec_v0.1.md` (รายการไทล์ + จำนวน + priority)
2) `SFT/docs/SFT_UI_Kit_v0.1.md` (ปุ่ม/กรอบ/ไอคอนที่ต้องทำ)
3) `SFT/docs/SFT_Character_Sheet_v0.1.md` (ชุดตัวละครขั้นต่ำ + variant)
4) `SFT/docs/SFT_RemoteConfig_Defaults_v0.1.json` (ค่าเริ่มต้นบาลานซ์หลังบ้าน)


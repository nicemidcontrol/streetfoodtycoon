# SFT (Street Food Tycoon) — 1-Page GDD (v0.1)

**Genre:** Idle/Clicker + Light Management  
**Visual:** 16-bit, Isometric  
**Platform:** Android (first), later iOS  
**Tech:** Godot + Firebase (Analytics/Remote Config)

---

## Core Fantasy
จากรถเข็นเล็ก ๆ ในตลาด → ขยายเป็นร้านระดับตำนาน → เปิดสาขา/ทีมงาน/เมนูเด็ด

## Core Loop (10 วินาทีอธิบายได้)
1) ทำอาหาร/ขาย → 2) ได้เงิน → 3) อัปเกรดเตา/เมนู/พนักงาน → 4) ขายได้เร็วขึ้น/กำไรมากขึ้น → 5) ปลดล็อกของใหม่ → วน

## MVP Scope (ห้ามหลุด)
- 1 สถานที่หลัก (เช่น “ตลาดกลางคืน”)
- 3 เมนูเริ่มต้น
- 3 สายอัปเกรดหลัก: **เตา / เมนู / พนักงาน**
- ลูกค้าเดินเข้ามา-ซื้อ-เงินเด้ง (isometric)
- Offline earnings (มีเพดานเวลา)
- Save/Load (Local ก่อน)

## Meta Progression (หลัง MVP)
- ปลดล็อกโซน/ช่วงเวลา (เช้า-เย็น-ดึก)
- ตกแต่งร้าน (cosmetic)
- ระบบภารกิจรายวัน/รางวัลล็อกอิน

## Key Systems (v0.1)
**Economy**
- เมนูมี: ราคา (Price), ต้นทุน (Cost), เวลา/ชิ้น (Cook time)
- กำไร = Price - Cost
- Throughput = ขึ้นกับ Cook time + เตา + พนักงาน

**Upgrades**
- เตา: ลดเวลา Cook / เพิ่ม batch / ลดโอกาสพลาด
- เมนู: เพิ่มราคา/เพิ่มทิป/เพิ่มความนิยม
- พนักงาน: ทำงานอัตโนมัติ/เพิ่มความเร็ว/ลดเวลารอคิว

**Customers**
- สุ่มเข้ามาเป็นระยะ → ต่อคิว → ซื้อ → เงินเข้าทันที
- (หลัง MVP) ความอดทน/ความพอใจ → ส่งผลต่อทิป

**Offline Earnings**
- คิดรายได้แบบอัตราคงที่ (หรือเฉลี่ย) × เวลาออฟไลน์
- เพดานเริ่มต้นแนะนำ 4 ชม. (ปรับด้วย upgrade/ads)

## Monetization (เบา ๆ ไม่กวน)
- Rewarded Ads เท่านั้น (เช่น x2 รายได้ 5 นาที / boost offline claim)
- ไม่มี interstitial ช่วงแรก

## Analytics (ขั้นต่ำ)
- session_start
- upgrade_purchase
- unlock_item_or_zone
- offline_claim
- rewarded_ad_watched (ถ้ามี)

## Definition of Done (v0.1)
- คนเล่นใหม่เข้าใจใน 3 นาที
- เล่นได้ 30–60 นาทีแบบไหล ๆ ไม่ตันเร็ว

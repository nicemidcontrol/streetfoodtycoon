# SFT – GDD Monetization & Ads Economy (Draft v0.1)

> Project: **Street Food Tycoon**  
> Scope: Monetization design, ad placements, economy balance, guardrails

---

## 1) Monetization Goals (North Star)
- **Fair & non-annoying**: ผู้เล่นที่ไม่ดูโฆษณายัง “เล่นสนุก + จบคอนเทนต์ได้”
- **Rewarded-first**: รายได้หลักมาจาก *Rewarded Ads* (ผู้เล่นกดเลือกเอง)
- **Low friction**: โฆษณาเป็น “ตัวเร่ง” ไม่ใช่ “กำแพง”
- **Long-term retention**: กระตุ้นกลับมาเล่นด้วย Offline + Daily + Event

---

## 2) Business Mix (แนะนำ)
### A) Ads (Primary)
- Rewarded Ads (หลัก)
- Optional Interstitial (รอง, จำกัดความถี่)
- Banner (ไม่แนะนำช่วงแรก / ใช้เฉพาะหน้าที่ไม่ทำลาย UX)

### B) IAP (Secondary แต่สำคัญ)
- Remove Ads (ตัด Interstitial/Banner แต่ **ยังให้ Rewarded ได้**)
- Starter Pack (คุ้มช่วงต้น)
- Permanent Boost (เช่น x2 income ถาวร หรือ VIP)
- Cosmetic (สกินรถเข็น/ชุดพ่อค้า/ลูกค้า/ป้ายร้าน) = ปลอดภัยต่อบาลานซ์

---

## 3) Currencies & Economy Hooks
### Soft Currency: “Coins”
- ใช้อัปเกรดอุปกรณ์, วัตถุดิบ, ปลดล็อกเมนู
- เป็นสิ่งที่โฆษณาช่วย “เร่ง” ได้ง่ายที่สุด

### Hard Currency: “Gems” (ถ้ามี)
- ได้จาก Daily/Quest/Event + ซื้อ IAP
- ใช้กับของที่ “หายาก/พิเศษ” เช่น รีโรลร้านค้า, สกิน, บูสต์ระดับสูง
- ระวังไม่ให้ “ต้องใช้ Gem เพื่อเล่นต่อ”

---

## 4) Ad Placements (ตำแหน่งโฆษณา) — เน้น Rewarded
### 4.1 “Watch News” = **Double Income Boost** (ในรอบเล่น)
**แฟนตาซี/ธีม**: ผู้เล่นดู “ข่าวเศรษฐกิจ/เทรนด์อาหาร” ผ่านทีวี/มือถือที่หน้าร้าน

- Type: Rewarded (ผู้เล่นกดเอง)
- Reward: **x2 Coins income** ชั่วคราว
- Duration (แนะนำเริ่มต้น): 3–5 นาที หรือ 1 รอบบริการ (เช่น 30–60 ออเดอร์)
- Cooldown: 20–30 นาที (กันสแปม)
- Stacking rules:
  - ไม่ซ้อนทับกัน (ถ้ากดซ้ำให้ “ต่อเวลา” หรือ “รีสตาร์ทเวลา” อย่างใดอย่างหนึ่ง)
  - ถ้าผู้เล่นมีบูสต์อื่น (เช่น x1.5) ให้คูณกันได้แต่ต้องระวังเศรษฐกิจแตก

**UX Button copy**
- “Watch News (30s) → Double Earnings for 5 min”
- แสดงตัวนับเวลา + ไอคอน x2 ใกล้ HUD

### 4.2 **Double Offline Reward**
**หลักการ**: ผู้เล่นกลับมาเก็บเงินออฟไลน์ได้ปกติ 1 เท่า และ “เลือกดูโฆษณาเพื่อคูณ 2”

- Type: Rewarded
- Reward: Offline coins ×2 (หรือ ×3 ในบาง event)
- Frequency cap: 1–3 ครั้ง/วัน (ขึ้นกับระยะออฟไลน์)
- Rule: ไม่ควรให้ Offline เก็บได้ “ไม่จำกัดชั่วโมง” แนะนำ cap 4–8 ชม. เพื่อชวนกลับมา

### 4.3 “Instant Finish / Speed Up” (ทางเลือก)
- Type: Rewarded
- Reward examples:
  - จบการทำอาหารทันที 1 ครั้ง
  - บูสต์สปีดครัว +20–30% 5 นาที
  - เร่งอัปเกรดก่อสร้าง (ถ้ามีระบบเวลา)

### 4.4 “Second Chance / Save Run” (ถ้ามีระบบพลาด)
- Type: Rewarded
- Reward:
  - ชุบชีวิต 1 ครั้ง
  - ยกเลิกความพลาด/ไหม้/ลูกค้าโกรธ 1 ครั้ง
- ต้องไม่บังคับดู ถ้าไม่ดูให้แพ้ได้แต่ไม่ frustrate เกินไป

### 4.5 “Mystery Box / Daily Deal”
- Type: Rewarded หรือ ใช้ Gem
- Reward: Coins/Boost/Ingredient pack/ชิ้นส่วนอัปเกรด
- ดีต่อ retention มาก

---

## 5) Interstitial Policy (ถ้าจะใส่)
> ใส่เฉพาะ “จังหวะธรรมชาติ” และมี frequency cap ชัดเจน

- หลังจบ “วัน/ด่าน” เท่านั้น (ไม่กลางเกม)
- Cap: ทุก 3–5 ด่าน หรือทุก 5–8 นาที (เลือกอย่างใดอย่างหนึ่ง)
- ปิด Interstitial สำหรับผู้ซื้อ Remove Ads
- ช่วง Soft launch ทดลอง A/B: Interstitial OFF vs ON (ดู retention/ARPDAU)

---

## 6) Economy Guardrails (กันบาลานซ์แตก)
- **Rewarded ต้องไม่กลายเป็นข้อบังคับ**: อัปเกรดหลักต้องทำได้ด้วยการเล่นปกติ
- **Cap รายได้โฆษณาต่อวัน** แบบนุ่ม ๆ:
  - จำกัดจำนวน watch-news ต่อชั่วโมง
  - จำกัด offline x2 ต่อวัน
- **Anti-inflation**:
  - เพิ่ม sink (ค่าอัปเกรดขั้นสูงแพงขึ้น, วัตถุดิบพรีเมียม, ค่าสต๊อก)
  - เพิ่มความคุ้ม “ความชำนาญ” (เล่นเก่งได้มากขึ้น) มากกว่า “ดูโฆษณาแล้วรวยทันที”

---

## 7) Recommended Default Tuning (เริ่มต้นเพื่อทดสอบ)
> ใช้เป็น baseline ก่อน แล้วค่อยปรับจากข้อมูลจริง

- Watch News x2 duration: **5 นาที**
- Watch News cooldown: **25 นาที**
- Offline cap: **6 ชม.**
- Offline x2 cap: **2 ครั้ง/วัน**
- Mystery box rewarded: **1–3 ครั้ง/วัน**
- Interstitial: **ปิดในเวอร์ชันแรก** (ค่อยเพิ่มตอนมี retention พอ)

---

## 8) IAP Packages (ชุดขายแนะนำ)
- **Remove Ads**: ตัด Interstitial/Banner, Rewarded ยังดูได้ตามสมัครใจ
- **Starter Pack**: Gems + Boost + Cosmetic (ราคาน่ารัก)
- **VIP / Permanent x2**: x2 income ถาวร (ระวังชนกับ watch-news — อาจทำเป็น x2.5 ชั่วคราวแทน)
- **Cosmetics Store**: สกินรถเข็น/ชุด/ป้ายร้าน/เอฟเฟกต์

---

## 9) Analytics & KPIs ที่ต้องเก็บ
- Ad impressions / DAU, Rewarded opt-in rate, completion rate
- ARPDAU, eCPM by placement
- Retention D1/D7/D30 (เทียบกลุ่มเห็น interstitial vs ไม่เห็น)
- Economy: coins earned vs spent, upgrade progression time
- Pain points: จุดที่คนเริ่มดูโฆษณาเยอะ = ตรงนั้นอาจยากเกิน

---

## 10) Notes for Implementation
- ทุก placement ต้องมี “เหตุผลในโลกเกม” (ข่าว, กล่องสุ่ม, โปรโมชัน)
- UI ต้องสื่อสารชัด: “ดูโฆษณา 30 วินาที → ได้อะไร → นานแค่ไหน”
- ทำระบบ feature flag เพื่อ A/B ได้ง่าย

---

## 11) Open Decisions (ค้างไว้ก่อน)
- จะมี Gem (hard currency) ไหม?
- จะมีระบบ “เวลาอัปเกรด/ก่อสร้าง” ไหม? (ถ้ามีจะเพิ่ม placement เร่งเวลาได้)
- จะทำ watch-news เป็น “เมนู” หรือ “พร็อพในฉาก” (ทีวีหน้าร้าน)?

# VENEFICA — เอกสารการทดสอบระบบและคุณภาพเกมเพลย์ (QA Documentation)

ยินดีต้อนรับสู่คลังเอกสารการทดสอบคุณภาพเกมเพลย์ (Quality Assurance) สำหรับเกม **VENEFICA** เกมแนวผจญภัยแม่มดสไตล์ Cozy Gothic ที่พัฒนาด้วย Unity Universal Render Pipeline (URP)

![ภาพรวมเกมเพลย์](../Media/Prototype_Overview.png)

---

## โครงสร้างเอกสารฉบับภาษาไทย (Repository Structure)

```
THAI_VER/
├── Test_Plan/
│   └── TEST_PLAN.md                # แผนการทดสอบหลัก (ขอบเขต กลยุทธ์ และเกณฑ์การผ่าน)
├── Test_Suites/
│   ├── 01_Player_Movement_and_Camera.md    # การเดิน วิ่ง และมุมมองกล้องไม่มุดกำแพง
│   ├── 02_Interaction_and_Targeting.md      # การตรวจจับเป้าหมายและการกันกดทะลุกำแพง
│   ├── 03_NPC_Dialogue_System.md            # บทสนทนา NPC Lina และ Rowan
│   ├── 04_Foraging_and_World_Nodes.md       # การเก็บ Moonleaf และการกันเก็บซ้ำ
│   ├── 05_Quest_and_Economy.md              # ส่งเควสต์ รับเงิน และการกันแจกเงินซ้ำ
│   ├── 06_Inventory_and_Modal_HUD.md        # กระเป๋า Tab และการล็อกตัวละครขณะเปิดเมนู
│   └── 07_Workstation_Inspection.md         # การซูมกล้องส่องโต๊ะปรุงยาและแปลงดิน
├── Defect_Reports/
│   └── BUG_REPORTS.md              # รายงานบันทึกบัค บัคที่แก้แล้ว และข้อจำกัดปัจจุบัน
└── Checklists/
    └── M1_SMOKE_CHECKLIST.md       # เช็กลิสต์ทดสอบความพร้อมเกมเพลย์ 20 ข้อ
```

---

## สรุปผลการทดสอบเวอร์ชันต้นแบบ (Milestone M1)
- **จำนวนเคสการทดสอบทั้งหมด:** 20 สถานการณ์ ครอบคลุม 7 โมดูลหลัก
- **อัตราการผ่านของ Smoke Test:** 100% (ผ่าน 20 / 20 ข้อ)
- **บัคระดับวิกฤตที่ยังค้างอยู่:** 0 ข้อ (แก้ไขจุดบกพร่องสำคัญหมดแล้ว)
- **ระบบหลักที่ผ่านการรับรอง:** การเคลื่อนที่ตัวละคร, มุมกล้องบุคคลที่สาม, บทสนทนา NPC, การเก็บเกี่ยวสมุนไพร, การคำนวณเงินและเควสต์, หน้าต่างกระเป๋า และจุดสำรวจในฉาก

---

## ลิงก์เอกสารสำคัญ
- [แผนการทดสอบหลัก (Master Test Plan)](Test_Plan/TEST_PLAN.md)
- [รายงานบันทึกบัค (Bug Reports)](Defect_Reports/BUG_REPORTS.md)
- [เช็กลิสต์ทดสอบ Smoke Test](Checklists/M1_SMOKE_CHECKLIST.md)
- [ตารางบันทึกการทดสอบ Excel (QA Workbook)](../Workbook/VENEFICA_QA_Workbook.xlsx)


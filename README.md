# AI Workshop: ใช้ AI ช่วยเชื่อมโยงข้อมูลและทำแผนที่สถานการณ์โรค

Lab สำหรับ Workshop 40 นาที: เชื่อมโยงข้อมูล 3 แหล่ง → คำนวณอัตราป่วย → ทำแผนที่ แบบผสมระหว่าง **กดรัน** กับ **พิมพ์ถาม Gemini** ใน Google Colab โดยไม่ต้องเขียนโค้ดเอง

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/rittiin/ai_workshopsit/blob/main/workshop_lab.ipynb)

## วิธีเริ่ม (ผู้เข้าอบรม)
1. คลิกปุ่ม **Open in Colab** ด้านบน แล้วล็อกอินบัญชี Google (แนะนำ Gmail ส่วนตัว)
2. เมนู **File → Save a copy in Drive**
3. ทำตามลำดับใน notebook: ▶️ กดรัน, ✨ ถาม Gemini, 🔑 เฉลย

## ข้อมูล (`data/`)
| ไฟล์ | เนื้อหา |
|---|---|
| `influenza_cases_2568.csv` | ผู้ป่วยและผู้เสียชีวิตไข้หวัดใหญ่รายจังหวัด ปี 2568 (**ข้อมูลสมมติ**) |
| `population_2568.csv` | ประชากรรายจังหวัด (**ตัวเลขประมาณการสมมติ**) |
| `health_region.csv` | จังหวัด → เขตสุขภาพที่ 1–13 |
| `thailand_provinces.geojson` | ขอบเขต 77 จังหวัด (ลดความละเอียด) |

ทุกไฟล์เชื่อมกันด้วย `pro_code` (รหัสจังหวัด 2 หลัก)

โฟลเดอร์ `fonts/` มีฟอนต์ไทย Sarabun สำหรับแผนที่แบบรูปภาพ (PNG พื้นขาว / พื้นโปร่งใส)

## ลำดับใน Lab (40 นาที)
| นาที | ส่วน |
|---|---|
| 0–5 | แนะนำ + ส่วนที่ 1 เรียกข้อมูล |
| 5–15 | ส่วนที่ 2–3 เชื่อมข้อมูล อัตราป่วย สรุปรายเขต |
| 15–22 | ส่วนที่ 4 แผนที่ |
| 22–37 | ส่วนที่ 5 โจทย์ Gemini (ดู [PROMPTS.md](PROMPTS.md)) |
| 37–40 | สรุปและข้อควรระวัง |

## แหล่งข้อมูล
- ขอบเขตจังหวัด: [OpenGISData-Thailand](https://github.com/chingchai/OpenGISData-Thailand) โดย chingchai (CC BY 4.0) ลดความละเอียดเพื่อให้โหลดเร็ว
- ข้อมูลผู้ป่วยและประชากร: ข้อมูลสมมติเพื่อการสอน **ไม่ใช่สถานการณ์จริง**
- ฟอนต์: [Sarabun](https://github.com/cadsondemak/Sarabun) โดย Cadson Demak (SIL Open Font License 1.1, ดู `fonts/OFL.txt`)

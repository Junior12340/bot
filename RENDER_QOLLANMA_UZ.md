# 🚀 TELEGRAM BOTNI RENDER.COM DA ISHGA TUSHIRISH
# TO'LIQ QADAM-BA-QADAM QO'LLANMA

## 📋 KERAKLI NARSALAR:
1. ✅ GitHub akkaunt (bepul)
2. ✅ Render.com akkaunt (bepul)
3. ✅ Telegram bot (sizda bor)
4. ✅ Bot kodlari (bot_updated.py)

---

## 1-QADAM: GITHUB REPOSITORY YARATISH

### 1.1. GitHub ga kiring
- https://github.com ga o'ting
- Agar akkauntingiz yo'q bo'lsa, ro'yxatdan o'ting (bepul)

### 1.2. Yangi repository yaratish
1. O'ng yuqori burchakda **"+"** belgisini bosing
2. **"New repository"** ni tanlang
3. Repository nomi: `telegram-murojaat-bot` (yoki istalgan nom)
4. **Public** yoki **Private** tanlang (ikkalasi ham ishlaydi)
5. **"Create repository"** tugmasini bosing

### 1.3. Fayllarni GitHub ga yuklash

**VARIANT A: GitHub web orqali (osonroq):**

1. Repository ochiq turganida **"Add file"** -> **"Upload files"** bosing

2. Quyidagi fayllarni yuklang:
   - `bot_updated.py` (sizning bot kodingiz)
   - `requirements.txt` (men yaratgan)
   - `.gitignore` (keyingi qadamda yaratamiz)

3. **"Commit changes"** tugmasini bosing

**VARIANT B: Git orqali (terminal):**

```bash
# Kompyuteringizda papka yarating
mkdir telegram-bot
cd telegram-bot

# Git ni boshlang
git init

# Fayllarni ko'chiring
# bot_updated.py, requirements.txt, .gitignore

# GitHub ga yuklang
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/SIZNING_USERNAME/telegram-murojaat-bot.git
git push -u origin main
```

---

## 2-QADAM: KERAKLI FAYLLARNI TAYYORLASH

### 2.1. requirements.txt (ALLAQACHON BOR)
```
aiogram==3.4.1
aiosqlite==0.19.0
apscheduler==3.10.4
openpyxl==3.1.2
```

### 2.2. .gitignore yaratish
GitHub repository da yangi fayl yarating: `.gitignore`

```
# Database
*.db
*.sqlite
*.sqlite3

# Python
__pycache__/
*.py[cod]
*$py.class
*.so
.Python
env/
venv/
ENV/

# Media
media_photos/
*.jpg
*.png
*.jpeg

# Logs
*.log

# OS
.DS_Store
Thumbs.db
```

### 2.3. render.yaml (IXTIYORIY - avtomatik deploy uchun)
```yaml
services:
  - type: web
    name: telegram-murojaat-bot
    env: python
    buildCommand: pip install -r requirements.txt
    startCommand: python bot_updated.py
    envVars:
      - key: PYTHON_VERSION
        value: 3.11
```

---

## 3-QADAM: RENDER.COM DA ACCOUNT YARATISH

### 3.1. Render.com ga kiring
- https://render.com ga o'ting
- **"Get Started"** yoki **"Sign Up"** bosing

### 3.2. GitHub bilan ulanish
1. **"Sign up with GitHub"** ni tanlang
2. GitHub akkauntingiz bilan login qiling
3. Render ga repository kirish ruxsatini bering

✅ Endi siz Render dashboard da bo'lishingiz kerak!

---

## 4-QADAM: YANGI WEB SERVICE YARATISH

### 4.1. Dashboard da
1. Chap tarafda **"New +"** tugmasini bosing
2. **"Web Service"** ni tanlang

### 4.2. Repository ulanish
1. **"Build and deploy from a Git repository"** ni tanlang
2. **"Next"** bosing

### 4.3. GitHub repository tanlash
1. O'zingizning `telegram-murojaat-bot` repository ni toping
2. **"Connect"** tugmasini bosing

(Agar repository ko'rinmasa, "Configure account" bosib GitHub ruxsatini yangilang)

---

## 5-QADAM: WEB SERVICE SOZLAMALARI

### 5.1. Asosiy sozlamalar:

**Name:** `telegram-murojaat-bot` (yoki istalgan nom)

**Region:** `Frankfurt (EU Central)` (yoki yaqin region)

**Branch:** `main` (yoki `master`)

**Runtime:** `Python 3`

**Build Command:**
```bash
pip install -r requirements.txt
```

**Start Command:**
```bash
python bot_updated.py
```

### 5.2. Instance Type:
- **Free** ni tanlang (0$/oy)

### 5.3. Environment Variables (muhim!)
**"Advanced"** bo'limini oching va quyidagi o'zgaruvchilarni qo'shing:

Har birini qo'shish uchun **"Add Environment Variable"** bosing:

| KEY               | VALUE                                          |
|-------------------|------------------------------------------------|
| `PYTHON_VERSION`  | `3.11`                                         |

(BOT_TOKEN va GROUP_CHAT_ID kodda bor, lekin xavfsizlik uchun bu yerga ham qo'shishingiz mumkin)

**IXTIYORIY** (xavfsizroq):
| KEY               | VALUE                                          |
|-------------------|------------------------------------------------|
| `BOT_TOKEN`       | `8311683221:AAFWy1J5sq-9-_Kdp5qf3c7kMl9upEQoj4k` |
| `GROUP_CHAT_ID`   | `-1003773765959`                               |

---

## 6-QADAM: DEPLOY QILISH

### 6.1. Deploy boshlash
1. Pastdagi **"Create Web Service"** tugmasini bosing
2. Render avtomatik deploy ni boshlaydi

### 6.2. Deploy jarayoni (5-10 daqiqa):
- **Build:** Kutubxonalar o'rnatilmoqda...
- **Deploy:** Kod yuklanmoqda...
- **Live:** Bot ishga tushdi! ✅

### 6.3. Loglarni ko'rish:
- Dashboard da **"Logs"** tabni oching
- Real-time loglarni ko'rasiz:
  ```
  ✅ Media papka yaratildi: media_photos
  ✅ Database tayyor
  ✅ Scheduler ishga tushdi
  ✅ Bot ishga tushdi!
  Start polling
  ```

---

## 7-QADAM: BOT ISHLAYOTGANINI TEKSHIRISH

### 7.1. Telegram da test qiling:
1. Botga `/start` yuboring
2. "✍️ Murojaat yuborish" tugmasini bosing
3. Murojaat yuboring

### 7.2. Guruhda test qiling:
1. Guruhda `/statistics` yozing
2. Excel export tugmasini bosing

✅ Agar hammasi ishlasa - TABRIKLAYMAN! 🎉

---

## 8-QADAM: MUHIM SOZLAMALAR

### 8.1. Auto-Deploy sozlash (tavsiya qilinadi)
1. Render dashboard da service ni oching
2. **"Settings"** ga o'ting
3. **"Build & Deploy"** bo'limida:
   - **Auto-Deploy:** `Yes` (har commit da avtomatik deploy)

### 8.2. Health Check sozlash
1. **"Settings"** -> **"Health & Alerts"**
2. **Health Check Path:** `/` (yoki bo'sh qoldiring)

### 8.3. Restart Policy
- **Manual** yoki **Always** (tavsiya: Always)

---

## 9-QADAM: XAVFSIZLIK (MUHIM!)

### 9.1. BOT_TOKEN ni koddan o'chirish
Bot kodida (bot_updated.py) token ni o'zgaruvchidan oling:

```python
import os

# Eski:
# BOT_TOKEN = "8311683221:AAFWy1J5sq-9-_Kdp5qf3c7kMl9upEQoj4k"

# Yangi:
BOT_TOKEN = os.getenv("BOT_TOKEN", "8311683221:AAFWy1J5sq-9-_Kdp5qf3c7kMl9upEQoj4k")
GROUP_CHAT_ID = int(os.getenv("GROUP_CHAT_ID", "-1003773765959"))
```

Keyin Render da Environment Variables qo'shing (5.3 qadam).

### 9.2. Database backup
- Render bepul rejada fayllar vaqti-vaqti bilan o'chishi mumkin
- Muhim ma'lumotlarni tashqi joyda saqlang (Google Drive, Dropbox)

---

## 10-QADAM: MUAMMOLARNI HAL QILISH

### 10.1. Bot ishlamayapti?
**Loglarni tekshiring:**
1. Dashboard -> Logs
2. Qizil xatoliklarni toping

**Umumiy muammolar:**
- ❌ `Module not found` -> requirements.txt tekshiring
- ❌ `Connection error` -> BOT_TOKEN noto'g'ri
- ❌ `Database error` -> DB fayl yaratilmagan

### 10.2. Bot sekin ishlayapti?
- Render bepul reja 15 daqiqa ishlamaslik keyin "sleep" ga o'tadi
- Birinchi so'rov 30-60 soniya davom etishi mumkin
- **Yechim:** Har 14 daqiqada ping yuborish (ixtiyoriy)

### 10.3. Database yo'qoldi?
- Render bepul rejada fayllar restart da o'chishi mumkin
- **Yechim:** PostgreSQL yoki tashqi database ishlatish

---

## 11-QADAM: QULAYLIK UCHUN QUSHIMCHA

### 11.1. Custom Domain (ixtiyoriy)
1. Settings -> Custom Domain
2. O'z domeningizni qo'shing (agar bor bo'lsa)

### 11.2. Environment Groups
1. Bir nechta botlar uchun umumiy sozlamalar

### 11.3. Logs download
- Loglarni yuklab olish va tahlil qilish

---

## 🎯 XULOSA

✅ **GitHub:** Repository yaratdingiz
✅ **Render:** Service deploy qildingiz  
✅ **Bot:** 24/7 ishlayapti
✅ **Bepul:** Hech narsa to'lamasdan!

---

## 📱 QUSHIMCHA MASLAHATLAR

### Render.com bepul reja cheklovlari:
- ✅ 750 soat/oy (24/7 uchun yetarli)
- ✅ 0.1 CPU
- ✅ 512 MB RAM
- ⚠️ 15 daqiqa faolsizlikdan keyin "sleep"
- ⚠️ Fayllar restart da o'chishi mumkin

### Yaxshilashlar (kelajakda):
1. **PostgreSQL database** ishlatish (Render bepul beradi)
2. **Uptime monitoring** (UptimeRobot.com - bepul)
3. **Paid plan** ($7/oy) - sleep yo'q, tezroq

---

## 🆘 YORDAM KERAKMI?

Agar qayerdadir tiqilib qolsangiz:
1. Render Logs ni tekshiring
2. Bot kodini qayta ko'rib chiqing
3. GitHub issues yarating
4. Render support ga murojaat qiling (https://render.com/docs)

---

## ✨ TABRIKLAYMAN!

Endi sizning Telegram botingiz professional cloud serverda ishlayapti!

Omad! 🚀

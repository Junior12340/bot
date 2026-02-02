# 🤖 Telegram Murojaat Bot

Davlat organlari va tashkilotlarga elektron murojaat yuborish uchun Telegram bot.

## ✨ Imkoniyatlar

- ✍️ Murojaat yuborish (F.I.Sh, pasport, telefon, manzil)
- 📋 Murojaatlar tarixini ko'rish
- 💬 Javoblarni qabul qilish
- 📊 Guruhda statistika
- 📥 Excel formatda export
- ⏰ Avtomatik eslatmalar (15 kundan eski murojaatlar)
- 🚫 Kunlik limit (5 ta murojaat)

## 🚀 Ishga tushirish

### Kerakli kutubxonalar

```bash
pip install -r requirements.txt
```

### Sozlamalar

`bot_updated.py` faylida yoki environment variables da:

```python
BOT_TOKEN = "sizning_bot_token"
GROUP_CHAT_ID = -1234567890  # guruh ID
```

### Ishga tushirish

```bash
python bot_updated.py
```

## 📦 Deployment

### Render.com (Tavsiya qilinadi)

1. GitHub repository yarating
2. Render.com ga kiring
3. "New Web Service" yarating
4. Repository ni ulang
5. Deploy!

Batafsil: [RENDER_QOLLANMA_UZ.md](RENDER_QOLLANMA_UZ.md)

### Railway.app

```bash
railway login
railway init
railway up
```

## 🗂 Fayl strukturasi

```
telegram-murojaat-bot/
├── bot_updated.py          # Asosiy bot
├── requirements.txt        # Kutubxonalar
├── murojaatlar.db         # Database (avtomatik yaratiladi)
├── media_photos/          # Rasmlar (avtomatik yaratiladi)
└── README.md              # Bu fayl
```

## 📊 Database strukturasi

### Jadvallar:
- **users** - Foydalanuvchilar
- **murojaatlar** - Murojaatlar
- **javoblar** - Javoblar

## 🔧 Buyruqlar

### Foydalanuvchilar uchun:
- `/start` - Botni boshlash
- `✍️ Murojaat yuborish` - Yangi murojaat
- `📋 Mening murojaatlarim` - Tarix
- `🏠 Bosh sahifa` - Asosiy menyu

### Guruh (admin) uchun:
- `/statistics` - To'liq statistika
- `/stats` - Qisqa statistika
- `/debug` - Debug ma'lumotlari
- **Reply** xabarga javob berish

## 🛡 Xavfsizlik

- Bot token ni `.env` faylda saqlang
- `.gitignore` da maxfiy ma'lumotlarni qo'shing
- Environment variables ishlatishing (Render/Railway da)

## 📝 Litsenziya

MIT License

## 👨‍💻 Muallif

Telegram: @yourhandle

## 🆘 Yordam

Muammolar bo'lsa, GitHub Issues da xabar bering.

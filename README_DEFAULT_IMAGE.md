# 🤖 BOT - DEFAULT RASM BILAN

## ✅ O'ZGARISHLAR

Endi bot quyidagicha ishlaydi:

1. **Foydalanuvchi rasm yuborsa** → O'z rasmi guruhga yuboriladi ✅
2. **Foydalanuvchi rasm yubormasa** → Default rasm ("Rasmsiz xabar yuborildi") bilan yuboriladi ✅

## 📁 FAYLLAR

- `bot_with_default_image.py` - Yangilangan bot kodi
- `default_image.png` - Default rasm (ko'k fon, "Rasmsiz xabar yuborildi")

## 🚀 ISHGA TUSHIRISH

### 1️⃣ Fayllarni joylashtirish

```bash
# Botingiz turgan papkaga ikkalasini ham qo'ying:
# - bot_with_default_image.py
# - default_image.png
```

### 2️⃣ Eski database ni o'chirish (agar kerak bo'lsa)

```bash
rm murojaatlar.db
```

### 3️⃣ Botni ishga tushirish

```bash
python bot_with_default_image.py
```

## 💡 QANDAY ISHLAYDI

### Rasm yuborilganda:
```
Foydalanuvchi: [O'z rasmi] + Murojaat matni
        ↓
Guruhga: [O'z rasmi] + Ma'lumotlar
```

### Rasm yuborilmaganda (o'tkazib yuborilganda):
```
Foydalanuvchi: "⏭️ Rasmni o'tkazib yuborish"
        ↓
Guruhga: [Default rasm] + Ma'lumotlar
```

## 🔧 DEFAULT RASMNI O'ZGARTIRISH

Agar boshqa rasm qo'ymoqchi bo'lsangiz:

1. Yangi rasmni tayyorlang (PNG/JPG)
2. Nomini `default_image.png` qiling
3. Bot fayli yoniga qo'ying
4. Botni qayta ishga tushiring

## ⚠️ MUHIM

- Default rasm (`default_image.png`) **bot fayli bilan bir joyda** bo'lishi kerak!
- Agar default rasm topilmasa, oddiy matnli xabar yuboriladi
- Bot logda `📸 Default rasm ishlatildi` deb ko'rsatadi

## 📊 LOG XABARLARI

```
✅ Guruhga yuborildi: message_id=123, rasm=ha     <- Foydalanuvchi rasmi
📸 Default rasm ishlatildi                        <- Default rasm
⚠️ Default rasm topilmadi: default_image.png      <- Default rasm yo'q
```

---

**Hammasi tayyor!** 🎉

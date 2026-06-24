# 🏠 Smart Home IoT System — ESP32 + Blynk + Wokwi  
سیستم هوشمند مدیریت انرژی و کنترل خانه





---

## 📌 معرفی پروژه
این پروژه یک **سیستم خانه هوشمند** ساده و کاربردی است که با استفاده از **ESP32** و **پلتفرم Blynk IoT** سه بخش اصلی خانه را کنترل می‌کند:

- روشنایی (Lamp)  
- گرمایش (Heating)  
- سرمایش (Cooling)

تمام سیستم در محیط **Wokwi** شبیه‌سازی شده و بدون نیاز به سخت‌افزار واقعی قابل اجراست.

---

## 🚀 ویژگی‌ها
- کنترل سه خروجی اصلی خانه از طریق اینترنت  
- اتصال پایدار به Blynk IoT Cloud  
- شبیه‌سازی کامل در Wokwi  
- طراحی مدار استاندارد با مقاومت محافظ  
- کدنویسی ساده و قابل توسعه  

---

## 🧠 معماری کلی سیستم
- **ESP32** → اجرای Firmware و کنترل GPIO  
- **Blynk Cloud** → مدیریت دیتاستریم‌ها و کنترل از راه دور  
- **Wokwi** → شبیه‌سازی مدار و تست کد  

---

## 🔌 اتصالات سخت‌افزار (GPIO Mapping)

| واحد عملیاتی | GPIO | توضیح |
|--------------|-------|--------|
| **لامپ** | 23 | LED روشنایی |
| **گرمایش** | 22 | LED گرمایش |
| **سرمایش** | 21 | LED سرمایش |

اتصال LEDها:  
LED → مقاومت 220Ω → GPIO  
کاتد → GND





---

## 📱 پین‌های مجازی Blynk (Virtual Pins)

| عملکرد | پین مجازی |
|--------|------------|
| کنترل لامپ | V0 |
| کنترل گرمایش | V1 |
| کنترل سرمایش | V2 |

---

## 🧩 کد اصلی (main.cpp)

```cpp
#define BLYNK_TEMPLATE_ID "TMPLe8H8_b8fs"
#define BLYNK_TEMPLATE_NAME "Smart Home"
#define BLYNK_AUTH_TOKEN "YOUR_TOKEN"

#include <WiFi.h>
#include <WiFiClient.h>
#include <BlynkSimpleEsp32.h>

char ssid[] = "Wokwi-GUEST";
char pass[] = "";

#define LAMP_PIN 23
#define HEATING_PIN 22
#define COOLING_PIN 21

BLYNK_WRITE(V0) { digitalWrite(LAMP_PIN, param.asInt()); }
BLYNK_WRITE(V1) { digitalWrite(HEATING_PIN, param.asInt()); }
BLYNK_WRITE(V2) { digitalWrite(COOLING_PIN, param.asInt()); }

void setup() {
  Serial.begin(115200);
  pinMode(LAMP_PIN, OUTPUT);
  pinMode(HEATING_PIN, OUTPUT);
  pinMode(COOLING_PIN, OUTPUT);
  Blynk.begin(BLYNK_AUTH_TOKEN, ssid, pass);
}

void loop() {
  Blynk.run();
}
```

---

## 🧪 شبیه‌سازی در Wokwi
این پروژه به‌طور کامل در Wokwi تست شده و عملکرد آن تأیید شده است.

برای اجرای شبیه‌سازی:  
**اجرای پروژه در Wokwi**

---

## 📄 مستندات پروژه
فایل‌های PDF شامل:

- گزارش کامل پروژه  
- فایل ارائه (Presentation)  

در پوشه‌ی `docs/` قرار داده شده‌اند.

---

## 📦 ساختار ریپازیتوری

```
Smart-Home-IoT-ESP32/
│
├── code/
│   └── main.cpp
│
├── schematics/
│   └── circuit.png
│
├── docs/
│   ├── IoT.pdf
│   └── IoT_view.pdf
│
├── README.md
└── LICENSE
```

---

## 🏁 نتیجه‌گیری
این پروژه یک نمونه‌ی کامل و ساده برای شروع کار با **IoT، ESP32، Blynk و شبیه‌سازی Wokwi** است.  
قابل توسعه برای:

- کنترل رله‌های واقعی  
- اضافه‌کردن سنسور دما  
- سیستم تهویه هوشمند  
- اتصال به دیتابیس  

---

## ✨ نویسنده  
**محمدحسین الماسی**

---

اگر خواستی می‌تونم همین README رو:

- **نسخه انگلیسی** کنم  
- **نسخه Markdown با عکس‌های واقعی** بسازم  
- **نسخه حرفه‌ای‌تر با Badge و GIF** آماده کنم  

کافیه بگی:  
**نسخه حرفه‌ای‌تر می‌خوام**

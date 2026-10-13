# STM32 Ultrasonic Distance Meter

![demo](docs/demo.gif)

یک جمله دربارهٔ پروژه: فاصله را با HC-SR04 اندازه می‌گیرد و روی
سون‌سگمنت ۴ رقمی نمایش می‌دهد.

## Features
- اندازه‌گیری فاصله با سنسور اولتراسونیک (TRIG/ECHO)
- نمایش روی سون‌سگمنت ۴ رقمی common anode با مالتی‌پلکس
- رفرش نمایشگر با وقفهٔ تایمر (TIM3)، بدون delay و بدون فلیکر

## Hardware
| قطعه | توضیح |
|---|---|
| STM32 (Blue Pill / مدل خودتان) | میکروکنترلر |
| HC-SR04 | سنسور فاصله |
| سون‌سگمنت ۴ رقمی common anode | نمایشگر |
| مقاومت‌های سری سگمنت‌ها | مقدار را بنویسید |

## Pinout
| سیگنال | پین |
|---|---|
| Segments A–DP | PB0–PB7 (پین‌های واقعی خودتان) |
| Digits G1–G4 | PA... |
| TRIG | PA... |
| ECHO | PA... |

## How it works
۱. پالس ۱۰ µs روی TRIG
۲. زمان HIGH بودن ECHO اندازه‌گیری می‌شود (Input Capture یا شمارش تایمر)
۳. فاصله از فرمول زیر به دست می‌آید
۴. عدد روی سون‌سگمنت با مالتی‌پلکس نمایش داده می‌شود

d = (t × v) / 2  ،  v ≈ 343 m/s  →  d(cm) ≈ t(µs) / 58

## Build & Flash
- IDE: STM32CubeIDE (نسخه)
- فایل `.ioc` برای دیدن تنظیمات کلاک و تایمرها
- Build → Flash با ST-Link

## Project Structure
├── Core/Src, Core/Inc
├── docs/ (عکس، گیف، شماتیک)
└── README.md

## Results / Limitations
- بازهٔ کاری، دقت و نرخ به‌روزرسانی (واقعی، اندازه‌گیری‌شده)
- محدودیت‌ها و ایده‌های بعدی

## Author
Mahyar — Electrical Engineering, SBU | لینک LinkedIn یا ایمیل

<p align="center">
<img width="660" height="517" alt="image" src="https://github.com/user-attachments/assets/83f5c38e-75ff-40bc-b12d-591bffe0bbce" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

تا چه اندازه می‌توانید عملیات پایه روی اعداد باینری را انجام دهید؟

برای شروع چالش باید با استفاده از Netcat به سرویس زیر متصل شویم:

</div>

```text
nc titan.picoctf.net 64272
```

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

ابتدا با دستور زیر به سرویس چالش متصل شدیم پس از اتصال، برنامه دو عدد باینری زیر را نمایش داد:

</div>

<p align="center">
<img width="906" height="796" alt="image" src="https://github.com/user-attachments/assets/926c4a46-9ce1-421c-b63a-878517c392ca" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
nc مخفف Netcat است و برای برقراری ارتباط مستقیم با یک سرویس شبکه‌ای روی یک Host و Port مشخص استفاده می‌شود.
</blockquote>

<div dir="rtl">

در سوال اول برنامه درخواست کرد:

</div>

```text
Operation 1: <<
Perform a left shift of Binary Number 1 by 1 bits.
```

<div dir="rtl">

عدد اول:

</div>

```text
00001011
```

<div dir="rtl">

در Left Shift یک‌بیتی، تمام بیت‌ها یک خانه به سمت چپ حرکت می‌کنند و یک صفر در سمت راست اضافه می‌شود:

</div>

```text
00001011 << 1
00010110
```

<div dir="rtl">

اگر صفرهای ابتدایی را حذف کنیم:

</div>

```text
10110
```

<div dir="rtl">

در سوال دوم برنامه درخواست کرد:

</div>

```text
Operation 2: |
Perform the operation on Binary Number 1 & 2.
```

<div dir="rtl">

علامت زیر عملگر Bitwise OR است:

</div>

```text
|
```

<div dir="rtl">

قاعده OR:

| بیت اول | بیت دوم | نتیجه |
|---:|---:|---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

دو عدد را زیر یکدیگر قرار می‌دهیم:

</div>

```text
00001011
00011110
--------
00011111
```

<div dir="rtl">

محاسبه بیت‌به‌بیت:

</div>

```text
0 OR 0 = 0
0 OR 0 = 0
0 OR 0 = 0
0 OR 1 = 1
1 OR 1 = 1
0 OR 1 = 1
1 OR 1 = 1
1 OR 0 = 1
```

<div dir="rtl">

نتیجه بدون صفرهای ابتدایی:

</div>

```text
11111
```

<div dir="rtl">

در سوال سوم برنامه درخواست کرد:

</div>

```text
Operation 3: >>
Perform a right shift of Binary Number 2 by 1 bits.
```

<div dir="rtl">

عدد دوم:

</div>

```text
00011110
```

<div dir="rtl">

در Right Shift یک‌بیتی، بیت‌ها یک خانه به سمت راست حرکت می‌کنند و بیت سمت راست حذف می‌شود:

</div>

```text
00011110 >> 1
00001111
```

<div dir="rtl">

بدون صفرهای ابتدایی:

</div>

```text
1111
```

<div dir="rtl">

در سوال چهارم برنامه درخواست کرد:

</div>

```text
Operation 4: *
Perform the operation on Binary Number 1 & 2.
```

<div dir="rtl">

عددهای Decimal:

</div>

```text
11 × 30 = 330
```

<div dir="rtl">

حال عدد ۳۳۰ را به باینری تبدیل می‌کنیم:

</div>

```text
330 = 256 + 64 + 8 + 2
```

<div dir="rtl">

ارزش‌های مکانی:

</div>

```text
256 128 64 32 16 8 4 2 1
 1   0   1  0  0 1 0 1 0
```

<div dir="rtl">

پس:

</div>

```text
330₁₀ = 101001010₂
```

<div dir="rtl">

در سوال پنجم برنامه درخواست کرد:

</div>

```text
Operation 5: +
Perform the operation on Binary Number 1 & 2.
```

<div dir="rtl">

محاسبه Decimal:

</div>

```text
11 + 30 = 41
```

<div dir="rtl">

تبدیل عدد ۴۱ به باینری:

</div>

```text
41 = 32 + 8 + 1
```

<div dir="rtl">

پس:

</div>

```text
41₁₀ = 101001₂
```

<div dir="rtl">

در سوال ششم برنامه درخواست کرد:

</div>

```text
Operation 6: &
Perform the operation on Binary Number 1 & 2.
```

<div dir="rtl">

علامت زیر عملگر Bitwise AND است:

</div>

```text
&
```

<div dir="rtl">

قاعده AND:

| بیت اول | بیت دوم | نتیجه |
|---:|---:|---:|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

دو عدد:

</div>

```text
00001011
00011110
--------
00001010
```

<div dir="rtl">

فقط در محل‌هایی که هر دو بیت برابر `1` هستند، نتیجه نیز `1` می‌شود.

نتیجه بدون صفرهای ابتدایی:

</div>

```text
1010
```

<div dir="rtl">

بعد از پاسخ صحیح به شش سؤال، برنامه درخواست کرد:

</div>

```text
Enter the results of the last operation in hexadecimal:
```

<div dir="rtl">

نتیجه آخرین عملیات:

</div>

```text
1010
```

<div dir="rtl">

برای تبدیل Binary به Hexadecimal، بیت‌ها را از راست در گروه‌های چهارتایی قرار می‌دهیم:

</div>

```text
1010
```

<div dir="rtl">

مقدار Decimal این گروه:

</div>

```text
8 + 2 = 10
```

<div dir="rtl">

در مبنای Hexadecimal، مقدار Decimal ده با حرف زیر نمایش داده می‌شود:

</div>

```text
A
```

<div dir="rtl">

بنابراین:

</div>

```text
1010₂ = A₁₆
```

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_d9a7ddc2}
```

</details>

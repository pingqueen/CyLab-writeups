<p align="center">
<img width="658" height="676" alt="image" src="https://github.com/user-attachments/assets/42d1a6e3-e65c-4f60-bae2-d72be6b2ea1f" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

این بازی کوتاه را انجام دهید تا با برنامه‌های تعاملی ترمینال و تعدادی از مهم‌ترین قوانین محدوده مسابقه یا `Scope` در picoCTF آشنا شوید.

برای اتصال به برنامه باید از Netcat استفاده کنیم:

</div>

```text
nc verbal-sleep.picoctf.net 59569
```

<div dir="rtl">

#### سرنخ:
هنگامی که انتخاب‌ها به‌صورت زیر نمایش داده می‌شوند:

</div>

```text
[a/b/c]
```

<div dir="rtl">

باید یکی از گزینه‌ها را وارد کنیم؛ برای مثال حرف `c` را تایپ کرده و سپس کلید Enter را فشار دهیم.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

ابتدا در ترمینال دستور زیر را اجرا کردیم:

</div>

<p align="center">
<img width="588" height="769" alt="image" src="https://github.com/user-attachments/assets/d0b57bcb-f009-49fd-a94e-0ae003e05988" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
nc مخفف Netcat است. از این ابزار برای برقراری ارتباط مستقیم با یک سرویس شبکه‌ای روی یک Host و Port مشخص استفاده می‌شود.
</blockquote>

<div dir="rtl">

این چالش یک برنامه تعاملی خط فرمان است؛ یعنی برنامه در بعضی مراحل منتظر دریافت ورودی از کاربر می‌ماند و تا زمانی که Enter یا یکی از گزینه‌ها را وارد نکنیم، ادامه پیدا نمی‌کند. پس از چند بار فشردن Enter، برنامه گزینه‌های زیر را نمایش داد:

</div>

```text
A → چند حساب کاربری ثبت کن
B → یک حساب را با دوستت به اشتراک بگذار
C → یک حساب شخصی و خصوصی ثبت کن
```

<div dir="rtl">

در این مرحله گزینه صحیح `C` است؛ بنابراین حرف زیر را وارد کردیم:

</div>

```text
c
```

<div dir="rtl">

و سپس Enter را فشار دادیم.

با ادامه‌دادن داستان و فشردن Enter، به انتخاب دوم رسیدیم:

</div>

<p align="center">
<img width="608" height="689" alt="image" src="https://github.com/user-attachments/assets/0ddacf8b-e4e9-44af-8327-e414b77c89bd" />
</p>

<div dir="rtl">

معنی گزینه‌ها:

</div>

```text
A → بازی را انجام بده
B → در Ether به‌دنبال فلگ بگرد
```

<div dir="rtl">

در این مرحله گزینه صحیح `A` است؛ بنابراین حرف زیر را وارد کردیم:

</div>

```text
a
```

<div dir="rtl">

و Enter را فشار دادیم.

برنامه توضیح می‌دهد که هیچ‌گاه نباید فلگ‌ها یا فایل‌های مربوط به چالش را با دیگران به اشتراک بگذاریم.

سپس شبیه‌سازی اجرای بازی آغاز شد:

</div>

```text
Playing the Game: 100%
Playing the Game completed successfully!
```

<div dir="rtl">

پس از پایان بازی و چند بار فشردن Enter، شخصیت داستان اعلام کرد که فلگ را پیدا کرده است:

</div>

<p align="center">
<img width="586" height="622" alt="image" src="https://github.com/user-attachments/assets/1f4e788d-c808-4eef-93c8-b6eabb944fa7" />
</p>

<div dir="rtl">

در پایان برنامه، قوانین اصلی مسابقه دوباره نمایش داده شدند:

</div>

<p align="center">
<img width="578" height="284" alt="image" src="https://github.com/user-attachments/assets/a3638497-227a-4b58-933f-0470703627eb" />
</p>

<div dir="rtl">

قوانین نمایش‌داده‌شده:

</div>

```text
1. فقط یک حساب کاربری ثبت کنید.
2. حساب‌ها، فلگ‌ها یا فایل‌های دانلودشده چالش را به اشتراک نگذارید.
3. برای انتشار عمومی رایتاپ‌ها تا اعلام برندگان توسط برگزارکنندگان صبر کنید.
```

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{m1113n1um_3d1710n_dd015572}
```

</details>

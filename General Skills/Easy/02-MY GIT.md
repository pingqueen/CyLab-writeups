<p align="center">
<img width="655" height="679" alt="image" src="https://github.com/user-attachments/assets/73203d82-409c-42f5-8dc8-f534cc7f7cf0" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

من سرور Git خودم را با قوانین مخصوص خودم ساخته‌ام!  
می‌توانی Repository یا مخزن چالش را با دستور زیر Clone کنی.

</div>

```text
git clone ssh://git@foggy-cliff.picoctf.net:55116/git/challenge.git
```

<div dir="rtl">

رمز عبور این است:

</div>

```text
550851c0
```

</details>

<br>

<details>
<summary dir="rtl"><strong>💡 سرنخ</strong></summary>

<br>

<div dir="rtl">

چگونه نام کاربری و ایمیل Git را مشخص می‌کنی؟

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<p align="center">
<img width="1058" height="330" alt="image" src="https://github.com/user-attachments/assets/cba3a8d2-57c2-4025-8f2b-0e89871c6f89" />
</p>

<div dir="rtl">

در ترمینال لینوکس،یا محیط Workspace دستور زیر را اجرا کن:

</div>

```bash
git clone ssh://git@foggy-cliff.picoctf.net:55116/git/challenge.git
```

<div dir="rtl">

سپس وقتی رمز خواست رمز زیر را وارد کن:

</div>

```text
550851c0
```

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
Clone یعنی دریافت یک نسخه‌ی کامل از Repository موجود روی یک سرور و ساختن یک نسخه‌ی محلی روی کامپیوتر خودت.
</blockquote>

<div dir="rtl">

بعد از Clone، پوشه‌ای به نام challenge ساخته می‌شود که بعد از ورود به این پوشه خروجی شامل:

</div>

<p align="center">
<img width="863" height="431" alt="image" src="https://github.com/user-attachments/assets/21374185-b0a0-4b1c-8472-bf7cd84b31df" />
</p>

<div dir="rtl">

سرور از ما می‌خواست:  
یک فایل به نام flag.txt بسازیم و آن را داخل یک Commit قرار دهیم وAuthor آن Commit برابر root <root@picoctf> باشد و سپس Commit را Push کنیم.

</div>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
Commit یعنی ثبت یک نسخه‌ی مشخص از تغییرات پروژه در تاریخچه‌ی Git. می‌توان Commit را شبیه ذخیره‌ کردن یک نقطه‌ی قابل‌ بازگشت در تاریخچه تصور کرد. هر Commit معمولاً شامل این موارد است:(تغییرات فایل‌ها/نام نویسنده/ایمیل نویسنده/تاریخ و زمان/پیام Commit/شناسه یا Hash/اشاره به Commit قبلی)
</blockquote>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
Push یعنی ارسال Commitهای محلی از کامپیوتر خودت به Repository روی سرور.
</blockquote>

<p align="center">
<img width="508" height="124" alt="image" src="https://github.com/user-attachments/assets/3244befe-3da6-4911-86ef-981f9212ec34" />
</p>

<div dir="rtl">

این دستورات را زدیم تا Commit جدید ظاهراً با نام root و ایمیل root@picoctf ساخته شود؛ چون سرور چالش به همین اطلاعات قابل‌جعل اعتماد می‌کرد.

</div>

<p align="center">
<img width="467" height="133" alt="image" src="https://github.com/user-attachments/assets/ecb8a6fc-faae-47e8-8af7-c28dbda3622c" />
</p>

<div dir="rtl">

دستور printf 'give me the flag\n' > flag.txt متن را تولید کرد و با استفاده از > آن را داخل فایل جدیدی به نام flag.txt نوشت تا شرط وجود این فایل در چالش را فراهم کنیم.

</div>

<p align="center">
<img width="815" height="229" alt="image" src="https://github.com/user-attachments/assets/ccf1efc0-8e03-4c9b-bf42-66a018aeb04b" />
</p>

<div dir="rtl">

دستور git status را زدیم تا بدون ایجاد هیچ تغییری، وضعیت فایل‌ها را بررسی کنیم؛ خروجی Untracked files: flag.txt نیز می‌گفت فایل ساخته شده، اما هنوز با git add برای Commit انتخاب نشده است.

</div>

<p align="center">
<img width="589" height="254" alt="image" src="https://github.com/user-attachments/assets/f820b780-55e0-4859-9948-359c10607144" />
</p>

<div dir="rtl">

نسخه فعلی flag.txt را برای قرارگرفتن در Commit بعدی آماده میکند. این دستور فایل را نه Commit می‌کند و نه به سرور می‌فرستد؛ فقط آن را وارد Staging Area می‌کند.

</div>

<p align="center">
<img width="339" height="126" alt="image" src="https://github.com/user-attachments/assets/a73b1878-638a-4c02-b36a-33dc41774711" />
</p>

<div dir="rtl">

این دستور را زدیم تا فایل flag.txt که قبلاً با git add آماده کرده بودیم، به‌صورت یک نسخه رسمی در تاریخچه محلی Git ثبت شود.

</div>

<p align="center">
<img width="757" height="308" alt="image" src="https://github.com/user-attachments/assets/4a607c05-7378-4e9a-8628-c8439df3ff14" />
</p>

<div dir="rtl">

سپس آن Commit را با git push برای بررسی به سرور چالش ارسال کنیم.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{1mp3rs0n4t4_g17_345y_506743df}
```

</details>

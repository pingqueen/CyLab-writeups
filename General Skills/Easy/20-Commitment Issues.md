<p align="center">
<img width="662" height="669" alt="image" src="https://github.com/user-attachments/assets/db921d96-9493-4689-a779-341e89111c19" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

من به‌صورت تصادفی فلگ را داخل یک فایل نوشتم؛ خوشبختانه بعداً آن را حذف کردم!

فایل‌های چالش داخل آرشیو زیر قرار دارند:

</div>

```text
challenge.zip
```

</details>

<br>

<details>
<summary dir="rtl"><strong>💡 سرنخ</strong></summary>

<br>

<div dir="rtl">

سیستم‌های Version Control می‌توانند نسخه‌های قبلی فایل‌هایی را که تغییر کرده یا حذف شده‌اند بازیابی کنند.

برای حل چالش باید با مفاهیم پایه Git آشنا باشیم.

می‌توانیم یک Commit قدیمی را `checkout` کنیم یا محتوای فایل را مستقیماً از همان Commit بخوانیم.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

ابتدا فایل‌های موجود در مسیر فعلی را مشاهده کردیم برای استخراج آن از دستور زیر استفاده کردیم:

</div>

<p align="center">
<img width="573" height="729" alt="image" src="https://github.com/user-attachments/assets/c132b345-977c-47a4-ad2e-49463a6a9e3d" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور unzip فایل‌ها و پوشه‌های داخل یک Archive از نوع ZIP را استخراج می‌کند.
</blockquote>

<div dir="rtl">

با دستور زیر وارد پوشه پروژه شدیم سپس تمام فایل‌ها، از جمله موارد مخفی را نمایش دادیم بعد از آن محتوای نسخه فعلی فایل را خواندیم:

</div>

<p align="center">
<img width="543" height="280" alt="image" src="https://github.com/user-attachments/assets/94c52c79-e242-4b76-a0d5-4d2f582f99f6" />
</p>

<div dir="rtl">

برای مشاهده خلاصه تاریخچه Git از دستور زیر استفاده کردیم:

</div>

<p align="center">
<img width="432" height="92" alt="image" src="https://github.com/user-attachments/assets/8650569b-0cf6-4292-b2de-20b8d651c58d" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور git log برای نمایش تاریخچه‌ی Commitهای یک مخزن Git استفاده می‌شود و اطلاعاتی مثل شناسه Commit، نویسنده، تاریخ و پیام Commit را نشان می‌دهد. گزینه --oneline هر Commit را به‌صورت خلاصه در یک خط نمایش می‌دهد.
</blockquote>

<div dir="rtl">

برای خواندن نسخه فایل `message.txt` در Commit قدیمی، دستور زیر را اجرا کردیم:

</div>

<p align="center">
<img width="312" height="63" alt="image" src="https://github.com/user-attachments/assets/3671b98f-a8f3-4647-8c36-0adf7cabd5e4" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور git show برای مشاهده جزئیات یک Commit یا محتوای یک فایل در یک Commit مشخص استفاده می‌شود.
</blockquote>

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{s@n1t1z3_30e86d36}
```

</details>

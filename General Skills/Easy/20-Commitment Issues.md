<img width="662" height="669" alt="image" src="https://github.com/user-attachments/assets/db921d96-9493-4689-a779-341e89111c19" />

#### متن سؤال:
من به‌صورت تصادفی فلگ را داخل یک فایل نوشتم؛ خوشبختانه بعداً آن را حذف کردم!

فایل‌های چالش داخل آرشیو زیر قرار دارند:

```text
challenge.zip
```

#### سرنخ‌ها:
سیستم‌های Version Control می‌توانند نسخه‌های قبلی فایل‌هایی را که تغییر کرده یا حذف شده‌اند بازیابی کنند.

برای حل چالش باید با مفاهیم پایه Git آشنا باشیم.

می‌توانیم یک Commit قدیمی را `checkout` کنیم یا محتوای فایل را مستقیماً از همان Commit بخوانیم.

***

#### مراحل حل:
ابتدا فایل‌های موجود در مسیر فعلی را مشاهده کردیم برای استخراج آن از دستور زیر استفاده کردیم:

<img width="573" height="729" alt="image" src="https://github.com/user-attachments/assets/c132b345-977c-47a4-ad2e-49463a6a9e3d" />

`نکته: دستور unzip فایل‌ها و پوشه‌های داخل یک Archive از نوع ZIP را استخراج می‌کند.`

با دستور زیر وارد پوشه پروژه شدیم سپس تمام فایل‌ها، از جمله موارد مخفی را نمایش دادیم بعد از آن محتوای نسخه فعلی فایل را خواندیم:

<img width="543" height="280" alt="image" src="https://github.com/user-attachments/assets/94c52c79-e242-4b76-a0d5-4d2f582f99f6" />

برای مشاهده خلاصه تاریخچه Git از دستور زیر استفاده کردیم:

<img width="432" height="92" alt="image" src="https://github.com/user-attachments/assets/8650569b-0cf6-4292-b2de-20b8d651c58d" />

`نکته: دستور git log برای نمایش تاریخچه‌ی Commitهای یک مخزن Git استفاده می‌شود و اطلاعاتی مثل شناسه Commit، نویسنده، تاریخ و پیام Commit را نشان می‌دهد. گزینه --oneline هر Commit را به‌صورت خلاصه در یک خط نمایش می‌دهد.`

برای خواندن نسخه فایل `message.txt` در Commit قدیمی، دستور زیر را اجرا کردیم:

<img width="312" height="63" alt="image" src="https://github.com/user-attachments/assets/3671b98f-a8f3-4647-8c36-0adf7cabd5e4" />

`نکته: دستور git show برای مشاهده جزئیات یک Commit یا محتوای یک فایل در یک Commit مشخص استفاده می‌شود.`

فلگ نهایی:

```text
picoCTF{s@n1t1z3_30e86d36}
```

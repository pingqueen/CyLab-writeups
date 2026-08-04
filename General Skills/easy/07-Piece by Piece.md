<img width="656" height="496" alt="image" src="https://github.com/user-attachments/assets/4d1d7a21-cd03-494e-8e5d-3cab3d04f6ab" />

#### متن سؤال:
بعد از ورود به سرور، چند قطعه فایل در Home Directory قرار دارند. این قطعه‌ها باید با یکدیگر ترکیب و سپس استخراج شوند تا فلگ آشکار شود.

برای اتصال به سرور:
```text
ssh -p 49159 ctf-player@dolphin-cove.picoctf.net
```
رمز عبور:
```text
a15d25e1
```
***
#### مراحل حل:
دستور زیر را اجرا کردیم و پس از آن، رمز عبور را وارد کردیم و با موفقیت وارد سیستم شدیم.

<img width="1054" height="520" alt="image" src="https://github.com/user-attachments/assets/23a78577-7112-4c8e-9c23-ebef078696d4" />

<img width="714" height="288" alt="image" src="https://github.com/user-attachments/assets/e61a5578-ab67-41b1-97c1-509815465c22" />

`نکته: دستور ls -lah فایل‌های عادی و مخفی را همراه با اطلاعات کامل و اندازه خوانا نمایش می‌دهد.`

دستور زیر را اجرا کردیم:

<img width="958" height="173" alt="image" src="https://github.com/user-attachments/assets/43bb362a-b64f-4f87-894c-3fd941d0283a" />

فلگ داخل یک فایل ZIP قرار داشته که به چند قطعه تقسیم شده است.

با دستورات لینوکس قطعه‌ها را دوباره به یک فایل تبدیل کن.

فایل ZIP رمزگذاری شده است و برای استخراج آن باید از رمز supersecret استفاده کنی.

بعد از استخراج، فایل متنی ایجادشده را برای پیدا کردن فلگ بررسی کن.

قطعه‌های فایل را با دستور زیر باهم ترکیب کردیم:

<img width="806" height="29" alt="image_2026-07-28_17-25-53" src="https://github.com/user-attachments/assets/2c6d1b99-7e1c-4a7a-b5e2-efacd2be6bb1" />

`نکته: علامت > به معنی Output Redirection است. و خروجی دستور سمت چپ را به‌جای نمایش روی صفحه، داخل فایل سمت راست ذخیره میکند.`

`نکته: ترتیب قطعه‌ها هنگام بازسازی فایل Split‌شده بسیار مهم است.`

فایل ZIP به نام combined را با رمز supersecret استخراج میکنیم:

<img width="684" height="104" alt="image" src="https://github.com/user-attachments/assets/11905d28-18fc-4b00-a122-2ce5294673d8" />

`نکته: unzip برای استخراج ZIP و گزینه -P برای مشخص‌کردن رمز استفاده می‌شود.`

فلگ نهایی:
```text
picoCTF{z1p_and_spl1t_f1l3s_4r3_fun_da494d2e}
```

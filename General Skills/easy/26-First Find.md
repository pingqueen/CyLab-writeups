<img width="662" height="409" alt="image" src="https://github.com/user-attachments/assets/5f83e928-018f-4104-936c-8b3f54300db8" />

#### متن سؤال:
آرشیو ZIP را از حالت فشرده خارج کنید و فایلی با نام زیر را پیدا کنید:

```text
uber-secret.txt
```

فایل دانلودشده:

```text
files.zip
```

***

#### مراحل حل:
ابتدا فایل ZIP دانلودشده را با دستور زیر استخراج کردیم:

<img width="1023" height="825" alt="image" src="https://github.com/user-attachments/assets/ef5225f7-84b8-4107-8121-731be680a97b" />

`نکته: دستور unzip فایل‌ها و پوشه‌های داخل یک Archive با فرمت ZIP را استخراج می‌کند.`

برای پیدا‌کردن فایل موردنظر دستور زیر را اجرا کردیم:

<img width="863" height="86" alt="image" src="https://github.com/user-attachments/assets/7390e4d6-1e24-41ae-8648-f61265f0ab46" />

خروجی، مسیر کامل فایل پیدا‌شده را نسبت به پوشه فعلی نمایش می‌دهد:
- find جست‌وجو را شروع می‌کند.
 - یعنی جست‌وجو از پوشه فعلی و تمام زیرپوشه‌های آن انجام شود.
- type f یعنی فقط فایل‌های معمولی بررسی شوند.
- name 'uber-secret.txt' یعنی فایلی با همین نام پیدا شود.

`نکته: دستور find برای جست‌وجوی فایل‌ها و پوشه‌ها در لینوکس استفاده می‌شود و می‌تواند بر اساس نام، نوع، اندازه، زمان تغییر و ویژگی‌های دیگر جست‌وجو کند.`

پس از مشخص‌شدن مسیر، محتوای فایل را با دستور زیر خواندیم:

<img width="950" height="75" alt="image" src="https://github.com/user-attachments/assets/a702c7c9-833a-473c-a9ae-f867e50a4198" />

فلگ نهایی:

```text
picoCTF{f1nd_15_f457_ab443fd1}
```

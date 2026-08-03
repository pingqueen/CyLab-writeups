<img width="667" height="595" alt="image" src="https://github.com/user-attachments/assets/d4cd0e08-f22b-4e17-affe-c6ed2ce960c4" />

#### متن سؤال:
آیا می‌توانید رمز عبور را پیدا کنید و فلگ را به‌دست آورید؟

برای حل چالش باید دو فایل زیر را دانلود کرده و در یک پوشه قرار دهیم:

```text
level2.py
level2.flag.txt.enc
```

#### سرنخ‌ها:
نحوه نمایش رمز داخل شرط برنامه ممکن است آشنا باشد.

برای حل این چالش نیازی نیست تابع `str_xor` را مهندسی معکوس کنیم؛ کافی است رمز ورودی صحیح را از شرط موجود در کد استخراج کنیم.

***

#### مراحل حل:
ابتدا فایل‌های موجود در مسیر فعلی را مشاهده کردیم؛ سپس برای بررسی منطق برنامه، سورس‌کد فایل `level2.py` را مشاهده کردیم:

<img width="1085" height="711" alt="image" src="https://github.com/user-attachments/assets/3a11cb4f-5a43-4fee-a9fe-14ebdfb16253" />

در ابتدای فایل تابع زیر قرار داشت:

```python
def str_xor(secret, key):
    # extend key to secret length
    new_key = key
    i = 0

    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)

    return "".join(
        [
            chr(ord(secret_c) ^ ord(new_key_c))
            for (secret_c, new_key_c) in zip(secret, new_key)
        ]
    )
```

اما بالای تابع نوشته شده بود:

```text
THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG
```

و سرنخ نیز تأکید می‌کرد که برای حل چالش لازم نیست این تابع را Reverse Engineer کنیم.

قسمت مهم برنامه تابع زیر بود:

```python
def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")

    if user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return

    print("That password is incorrect")
```

شرط اصلی:

```python
if user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36):
```

یعنی رمز صحیح برابر است با کنار هم قرارگرفتن چهار کاراکتری که کدهای آن‌ها به‌صورت Hexadecimal نوشته شده‌اند.

برای جلوگیری از خطا، عبارت شرط را مستقیماً با Python اجرا کردیم:

<img width="734" height="77" alt="image" src="https://github.com/user-attachments/assets/3a8355d6-ce3c-423f-820f-5119759280f5" />

و رمز صحیح برابر است با:

```text
de76
```
`نکته: دستور python3 برای اجرای مفسر زبان برنامه‌نویسی Python 3 و اجرای فایل‌های پایتون در ترمینال استفاده می‌شود.`

`نکته: گزینه -c در دستور python3 برای اجرای مستقیم یک قطعه کد پایتون داخل ترمینال استفاده می‌شود؛ یعنی بدون ساختن فایل .py.`

`نکته: تابع chr() در پایتون یک عدد را به کاراکتر Unicode متناظر آن تبدیل می‌کند. این عدد می‌تواند به‌صورت ده‌دهی یا هگزادسیمال نوشته شود.`

پس از پیدا‌کردن رمز، اسکریپت را اجرا کردیم:

<img width="474" height="129" alt="image" src="https://github.com/user-attachments/assets/3571aea2-bbe6-454d-b16a-318afc7b4bcd" />

برنامه فایل رمزگذاری‌شده را با استفاده از رمز ورودی Decode کرد و فلگ را چاپ کرد.

فلگ نهایی:

```text
picoCTF{tr45h_51ng1ng_489dea9a}
```

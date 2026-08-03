<img width="659" height="645" alt="image" src="https://github.com/user-attachments/assets/9d744526-71c3-44f5-97a9-54af26cd2e4d" />

#### متن سؤال:
آیا می‌توانید رمز عبور را پیدا کنید و فلگ را به‌دست آورید؟

برای حل چالش باید دو فایل زیر را دانلود کرده و داخل یک پوشه قرار دهیم:

```text
level1.py
level1.flag.txt.enc
```

#### سرنخ‌ها:
برای مشاهده فایل در Webshell می‌توان از ویرایشگر Nano استفاده کرد:

```bash
nano level1.py
```

برای خروج از Nano کلیدهای `Ctrl + X` را فشار می‌دهیم.

برای حل این چالش نیازی نیست تابع `str_xor` را مهندسی معکوس کنیم؛ رمز عبور مستقیماً در بخش بررسی ورودی برنامه قرار گرفته است.

***

#### مراحل حل:
ابتدا فایل‌های موجود در مسیر فعلی را مشاهده کردیم؛ سپس سورس‌کد برنامه را با دستور زیر مشاهده کردیم:

<img width="1079" height="726" alt="image" src="https://github.com/user-attachments/assets/a00e4e06-cf81-4bbd-a355-6c957a3162ef" />

بخش ابتدایی فایل شامل تابع زیر بود:

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

بالای تابع نوشته شده بود:

```text
THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG
```

یعنی برای پیدا‌کردن رمز لازم نیست جزئیات الگوریتم XOR را تحلیل کنیم.

قسمت مهم برنامه تابع بررسی رمز بود:

```python
def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")

    if user_pw == "691d":
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return

    print("That password is incorrect")
```

شرط برنامه به‌طور مستقیم نشان می‌دهد رمز صحیح چیست:

```python
if user_pw == "691d":
```

بنابراین رمز صحیح:

```text
691d
```

است.

پس از پیدا‌کردن رمز، اسکریپت را اجرا کردیم:

<img width="463" height="121" alt="image" src="https://github.com/user-attachments/assets/ba99809f-70a9-444e-98f5-a86455b87c20" />

`نکته: دستور python3 برای اجرای مفسر زبان برنامه‌نویسی Python 3 و اجرای فایل‌های پایتون در ترمینال استفاده می‌شود.`

فلگ نهایی:

```text
picoCTF{545h_r1ng1ng_56891419}
```

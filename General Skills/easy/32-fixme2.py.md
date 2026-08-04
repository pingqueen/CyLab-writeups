<img width="661" height="665" alt="image" src="https://github.com/user-attachments/assets/cd9c02dc-6608-490a-8f56-447c6a675663" />

#### متن سؤال:
خطای نحوی موجود در اسکریپت Python را اصلاح کنید تا برنامه بتواند فلگ را چاپ کند.

فایل دانلودشده:

```text
fixme2.py
```

#### سرنخ‌ها:
آیا عملگر مقداردهی و عملگر مقایسه برابری در Python یکسان هستند؟

برای مشاهده و ویرایش فایل در Webshell می‌توان از Nano استفاده کرد:

```bash
nano fixme2.py
```

برای خروج از Nano:

```text
Ctrl + X
```

همچنین نیازی نیست تابع `str_xor` را Reverse Engineer کنیم.

***

#### مراحل حل:
ابتدا محتوای فایل را با دستور زیر مشاهده کردیم و برای مشاهده پیام دقیق خطا، فایل را اجرا کردیم:

<img width="1280" height="550" alt="image" src="https://github.com/user-attachments/assets/99c082ec-faa0-431a-b463-c1d30c5c5ed7" />

بخش ابتدایی برنامه شامل تابع زیر بود:

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

سپس داده رمزگذاری‌شده در متغیر `flag_enc` ساخته می‌شود و با کلید زیر رمزگشایی می‌شود:

```python
flag = str_xor(flag_enc, 'enkidu')
```

بخش مشکل‌دار برنامه:

```python
# Check that flag is not empty
if flag = "":
    print("String XOR encountered a problem, quitting.")
else:
    print("That is correct! Here's your flag: " + flag)
```

در شرط `if` از یک علامت مساوی استفاده شده است:

```python
=
```

علامت = برای مقداردهی است و نمی‌توان از آن برای مقایسه داخل شرط if استفاده کرد؛ به همین دلیل پایتون خطای SyntaxError نمایش می‌دهد.

برای ویرایش فایل از دستور زیر استفاده کردیم:

<img width="1280" height="466" alt="image" src="https://github.com/user-attachments/assets/27a49cc4-f360-43f8-8387-b3f8e3f45689" />

علامت == بررسی می‌کند که مقدار متغیر flag با رشته خالی "" برابر است یا نه:

اگر flag خالی باشد، شرط True می‌شود و پیام خطا چاپ می‌شود.
اگر flag خالی نباشد، بخش else اجرا شده و فلگ نمایش داده می‌شود.

`نکته: در پایتون علامت = برای مقداردهی و علامت == برای مقایسه برابری استفاده می‌شود.`

فلگ نهایی:

```text
picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
```

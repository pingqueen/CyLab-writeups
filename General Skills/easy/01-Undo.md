<img width="662" height="573" alt="photo_2026-07-26_00-55-13" src="https://github.com/user-attachments/assets/1e38d875-5274-4a53-8404-6ab76f006212" />

#### متن سوال :
آیا می‌توانید مجموعه‌ای از تبدیل‌های متنی لینوکس را معکوس کنید تا فلگ اصلی را بازیابی کنید؟
برای جست‌وجوی فلگ، به این سرویس متصل شوید:
```text
nc foggy-cliff.picoctf.net 61232
```
#### سرنخ:
برای تبدیل متن و جایگزینی کاراکترها، مستندات دستور `tr` را مشاهده کنید.
* * *
#### مراحل حل:
در ترمینال لینوکس،یا محیط Workspace دستور زیر را اجرا کن:
```bash
nc foggy-cliff.picoctf.net 61232
```
`نکته:nc مخفف Netcat است. از آن برای برقراری ارتباط مستقیم با یک سرویس شبکه استفاده می‌شود.`

<img width="700" height="113" alt="image" src="https://github.com/user-attachments/assets/e6ddd16c-358f-47fc-b2cf-c3c7589e23fe" />


به چالش تبدیل‌های متنی خوش آمدید.
هدف شما این است که مرحله‌به‌مرحله فلگ اصلی را بازیابی کنید.
در هر مرحله، فلگ تغییریافته و یک راهنما نمایش داده می‌شود.
دستور صحیح لینوکس را وارد کنید تا آخرین تبدیلی که روی متن انجام شده است، خنثی شود.

<img width="817" height="110" alt="image" src="https://github.com/user-attachments/assets/c06a8ebd-ce80-4396-824a-232ea87b316c" />

رشته با Base64 کدگذاری شده است.

`نکته: base64 برنامه‌ای برای کدگذاری و رمزگشایی Base64 است.`

`نکته: گزینه d- مخفف decode است؛ یعنی داده را رمزگشایی کن.`

<img width="654" height="108" alt="image" src="https://github.com/user-attachments/assets/e610def4-5c9c-4e58-9735-c187bf36bd96" />

ترتیب کاراکترهای متن برعکس شده است.

`نکته: دستور rev کاراکترهای هر خط را از آخر به اول می‌چیند.`

<img width="648" height="110" alt="image" src="https://github.com/user-attachments/assets/0172d3fb-3e26-4957-a3fd-edfa5bdd2207" />

زیرخط‌ها یا underscoreها با خط تیره جایگزین شده‌اند.

` نکته: tr مخفف translate است و برای تبدیل کاراکترها استفاده می‌شود.`

<img width="654" height="108" alt="image" src="https://github.com/user-attachments/assets/9e1400f4-91c9-4113-b322-e2680528c5b2" />

آکولادها با پرانتز جایگزین شده‌اند.

<img width="681" height="105" alt="image" src="https://github.com/user-attachments/assets/d1bc3634-8868-4fd9-8c12-5bd3c06ecfb9" />

عملیات ROT13 روی حروف انجام شده است.

`نکته: در ROT13 هر حرف انگلیسی ۱۳ خانه در الفبا جابه‌جا می‌شود. برای مثال:`
```text
a → n
b → o
c → p
d → q
...
m → z
n → a
o → b
...
z → m
```

<img width="533" height="55" alt="image" src="https://github.com/user-attachments/assets/7c298e46-e124-4632-b17e-214910ee34ad" />

فلگ نهایی:
```text
picoCTF{Revers1ng_t3xt_Tr4nsf0rm@t10ns_a12e8886}
```




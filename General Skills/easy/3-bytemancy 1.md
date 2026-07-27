<img width="659" height="608" alt="image" src="https://github.com/user-attachments/assets/9abed54a-18a5-4eab-a221-9cac1a908d6f" />

#### متن سؤال:
آیا می‌توانی بایت‌های درست را تولید کنی؟
سورس‌کد برنامه از لینک موجود در صفحه قابل دانلود است.
```text
nc foggy-cliff.picoctf.net 58278
```
#### سرنخ:
از Copy/Paste استفاده نکن؛ برای تولید ورودی از Python استفاده کن.
***
#### مراحل حل:
ابتدا با دستور زیر به برنامه چالش متصل شدیم:
```text
nc foggy-cliff.picoctf.net 58278
```
`نکته: nc مخفف Netcat است. Netcat ابزاری برای برقراری ارتباط شبکه‌ای با یک سرور از طریق یک پورت مشخص است.`

بعد از اتصال، برنامه این پیام را نمایش داد:

<img width="652" height="240" alt="image" src="https://github.com/user-attachments/assets/54dc8d21-56b6-4803-96e2-8c2dcedcced6" />


کاراکتری را که مقدار ASCII ده‌دهی آن ۱۰۱ است، ۱۷۵۱ بار پشت سر هم و بدون فاصله برای من ارسال کن.

مقدار Decimal یا ده‌دهی 101 در جدول ASCII برابر کاراکتر زیر است:

<img width="363" height="75" alt="image" src="https://github.com/user-attachments/assets/dcd995b9-b720-4077-b1a0-f346e2859ff5" />

`نکته: در Python تابع chr() یک عدد را می‌گیرد و کاراکتر متناظر آن را برمی‌گرداند`

در Python می‌توان یک رشته را در یک عدد ضرب کرد تا آن رشته به همان تعداد تکرار شود. اما فقط تولیدکردن رشته کافی نبود؛ باید خروجی Python را برای برنامه روی سرور ارسال می‌کردیم.
برای این کار از دستور نهایی زیر استفاده کردیم:

<img width="722" height="220" alt="image" src="https://github.com/user-attachments/assets/2c1a619a-afd5-43e5-9603-14a7e496db80" />

فلگ نهایی:
```text
picoCTF{h0w_m4ny_e's???_706320e0}
```

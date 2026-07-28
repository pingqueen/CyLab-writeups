<img width="658" height="597" alt="image" src="https://github.com/user-attachments/assets/f858634a-4204-4232-847e-404cf728d1c5" />

#### متن سؤال:
آیا می‌توانی بایت‌های درست را تولید کنی؟

برای اتصال به برنامه از Netcat استفاده می‌کنیم:
```text
nc candy-mountain.picoctf.net 64065
```
#### سرنخ:
حل این چالش با یک دستور یک‌خطی، برای چالش بعدی این مجموعه مفید خواهد بود.
***
#### مراحل حل:
ابتدا با دستور زیر به سرویس متصل شدیم:

<img width="618" height="230" alt="image" src="https://github.com/user-attachments/assets/c6c1d707-f6c7-42e4-88b1-94f42ab019fe" />

کاراکترهای متناظر با کدهای ASCII ده‌دهی 101، 101 و 101 را پشت سر هم و بدون فاصله ارسال کن.

`نکته: ASCII روشی برای نمایش کاراکترها به کمک اعداد است.`

برای اینکه مطمئن شویم عدد 101 برابر چه کاراکتری است، این دستور را اجرا کردیم:

<img width="372" height="80" alt="image" src="https://github.com/user-attachments/assets/e85b1975-9b0a-4026-bda8-4b359ca0672f" />

`نکته: تابع chr() یک عدد را به کاراکتر متناظر آن تبدیل می‌کند.`

<img width="613" height="247" alt="image" src="https://github.com/user-attachments/assets/5999bc95-734c-442e-9686-caa48df03a21" />

فلگ نهایی:
```text
picoCTF{pr1n74813_ch4r5_4daf27d8}
```

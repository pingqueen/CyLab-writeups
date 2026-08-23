<p align="center">
<img width="658" height="597" alt="image" src="https://github.com/user-attachments/assets/f858634a-4204-4232-847e-404cf728d1c5" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

آیا می‌توانی بایت‌های درست را تولید کنی؟

برای اتصال به برنامه از Netcat استفاده می‌کنیم:

</div>

```text
nc candy-mountain.picoctf.net 64065
```

</details>

<br>

<details>
<summary dir="rtl"><strong>💡 سرنخ</strong></summary>

<br>

<div dir="rtl">

حل این چالش با یک دستور یک‌خطی، برای چالش بعدی این مجموعه مفید خواهد بود.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

ابتدا با دستور زیر به سرویس متصل شدیم:

</div>

<p align="center">
<img width="618" height="230" alt="image" src="https://github.com/user-attachments/assets/c6c1d707-f6c7-42e4-88b1-94f42ab019fe" />
</p>

<div dir="rtl">

کاراکترهای متناظر با کدهای ASCII ده‌دهی 101، 101 و 101 را پشت سر هم و بدون فاصله ارسال کن.

</div>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
ASCII روشی برای نمایش کاراکترها به کمک اعداد است.
</blockquote>

<div dir="rtl">

برای اینکه مطمئن شویم عدد 101 برابر چه کاراکتری است، این دستور را اجرا کردیم:

</div>

<p align="center">
<img width="372" height="80" alt="image" src="https://github.com/user-attachments/assets/e85b1975-9b0a-4026-bda8-4b359ca0672f" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
تابع <code>chr()</code> یک عدد را به کاراکتر متناظر آن تبدیل می‌کند.
</blockquote>

<p align="center">
<img width="613" height="247" alt="image" src="https://github.com/user-attachments/assets/5999bc95-734c-442e-9686-caa48df03a21" />
</p>

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{pr1n74813_ch4r5_4daf27d8}
```

</details>

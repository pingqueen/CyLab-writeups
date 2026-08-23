<p align="center">
<img width="659" height="608" alt="image" src="https://github.com/user-attachments/assets/9abed54a-18a5-4eab-a221-9cac1a908d6f" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

آیا می‌توانی بایت‌های درست را تولید کنی؟  
سورس‌کد برنامه از لینک موجود در صفحه قابل دانلود است.

</div>

```text
nc foggy-cliff.picoctf.net 58278
```

</details>

<br>

<details>
<summary dir="rtl"><strong>💡 سرنخ</strong></summary>

<br>

<div dir="rtl">

از Copy/Paste استفاده نکن؛ برای تولید ورودی از Python استفاده کن.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

ابتدا با دستور زیر به برنامه چالش متصل شدیم:

</div>

```text
nc foggy-cliff.picoctf.net 58278
```

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
<code>nc</code> مخفف <code>Netcat</code> است. Netcat ابزاری برای برقراری ارتباط شبکه‌ای با یک سرور از طریق یک پورت مشخص است.
</blockquote>

<div dir="rtl">

بعد از اتصال، برنامه این پیام را نمایش داد:

</div>

<p align="center">
<img width="652" height="240" alt="image" src="https://github.com/user-attachments/assets/54dc8d21-56b6-4803-96e2-8c2dcedcced6" />
</p>

<div dir="rtl">

کاراکتری را که مقدار ASCII ده‌دهی آن ۱۰۱ است، ۱۷۵۱ بار پشت سر هم و بدون فاصله برای من ارسال کن.

مقدار Decimal یا ده‌دهی 101 در جدول ASCII برابر کاراکتر زیر است:

</div>

<p align="center">
<img width="363" height="75" alt="image" src="https://github.com/user-attachments/assets/dcd995b9-b720-4077-b1a0-f346e2859ff5" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
در Python تابع <code>chr()</code> یک عدد را می‌گیرد و کاراکتر متناظر آن را برمی‌گرداند.
</blockquote>

<div dir="rtl">

در Python می‌توان یک رشته را در یک عدد ضرب کرد تا آن رشته به همان تعداد تکرار شود. اما فقط تولیدکردن رشته کافی نبود؛ باید خروجی Python را برای برنامه روی سرور ارسال می‌کردیم.  
برای این کار از دستور نهایی زیر استفاده کردیم:

</div>

<p align="center">
<img width="722" height="220" alt="image" src="https://github.com/user-attachments/assets/2c1a619a-afd5-43e5-9603-14a7e496db80" />
</p>

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{h0w_m4ny_e's???_706320e0}
```

</details>

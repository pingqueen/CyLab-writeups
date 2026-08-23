<p align="center">
<img width="666" height="611" alt="image" src="https://github.com/user-attachments/assets/8d9a42a6-4580-4b23-90e6-6867b60916f0" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

آیا می‌توانی فلگ را بخوانی؟ فکر می‌کنم بتوانی!  
برای اتصال به سرور از SSH استفاده کردیم:

</div>

```text
ssh -p 57134 ctf-player@green-hill.picoctf.net
```

<div dir="rtl">

رمز عبور:

</div>

```text
8b23dc85
```

</details>

<br>

<details>
<summary dir="rtl"><strong>💡 سرنخ</strong></summary>

<br>

<div dir="rtl">

دستور sudo چیست؟

چگونه متوجه می‌شوی چه مجوزهایی داری؟

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

دستور زیر را اجرا کردیم:

</div>

<p align="center">
<img width="1023" height="528" alt="image" src="https://github.com/user-attachments/assets/1d434945-ecce-430f-8dde-16c2649d333a" />
</p>

<div dir="rtl">

بعد از ورود اجرا کردیم:

</div>

<p align="center">
<img width="732" height="228" alt="image" src="https://github.com/user-attachments/assets/22ad2f67-c761-416e-aa90-e3cae0b38cb2" />
</p>

<div dir="rtl">

این خروجی تأیید کرد که کاربر فعلی root نیست و با حساب معمولی ctf-player وارد شده‌ایم. بنابراین فقط کاربر root می‌توانست فایل را بخواند، درحالی‌که ما ctf-player بودیم.

</div>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور <code>whoami</code> نام کاربر فعلی را نمایش می‌دهد.
</blockquote>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
Permission فایل مشخص می‌کند مالک، گروه و سایر کاربران چه دسترسی‌هایی دارند.
</blockquote>

<div dir="rtl">

برای مشاهده مجوزهای واقعی کاربر، اجرا کردیم:

</div>

<p align="center">
<img width="1208" height="122" alt="image" src="https://github.com/user-attachments/assets/784f0da9-9f75-4df9-bcd2-13abe49d2a15" />
</p>

<div dir="rtl">

اجرای یک ویرایشگر قدرتمند مانند Emacs با sudo می‌تواند امکان خواندن و تغییر فایل‌های متعلق به root را فراهم کند.

</div>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
sudo فقط دستورهایی را اجرا می‌کند که در تنظیمات sudoers برای کاربر مجاز شده باشند.
</blockquote>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور <code>sudo -l</code> فهرست مجوزهای sudo کاربر فعلی را نمایش می‌دهد.
</blockquote>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
NOPASSWD یعنی دستور مجاز بدون درخواست رمز sudo اجرا می‌شود.
</blockquote>

<p align="center">
<img width="529" height="35" alt="image" src="https://github.com/user-attachments/assets/76c977e8-0848-459f-885f-754eaf885a80" />
</p>

<div dir="rtl">

چون Emacs با هویت root اجرا شده بود، Permission فایل دیگر مانع خواندن آن نشد و محتوای فایل داخل Emacs نمایش داده شد:

</div>

<p align="center">
<img width="734" height="857" alt="image" src="https://github.com/user-attachments/assets/f2ff4a21-9fba-4d67-bfaa-bdb7d3a5d1d9" />
</p>

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{ju57_5ud0_17_9a782247}
```

</details>

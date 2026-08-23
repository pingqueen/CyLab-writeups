<p align="center">
<img width="656" height="639" alt="image" src="https://github.com/user-attachments/assets/1692dd0c-7168-4394-ba34-92977f23405f" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

آیا می‌توانی سرور را وادار کنی رازهایش را فاش کند؟  
به نظر می‌رسد برنامه فقط می‌تواند Google DNS را Ping کند؛ اما اگر ورودی خلاقانه‌تری به آن بدهیم چه اتفاقی می‌افتد؟  
برای اتصال به سرویس از Netcat استفاده می‌کنیم:

</div>

```text
nc mysterious-sea.picoctf.net 55223
```

</details>

<br>

<details>
<summary dir="rtl"><strong>💡 سرنخ</strong></summary>

<br>

<div dir="rtl">

برنامه در پشت صحنه از یک دستور Shell استفاده می‌کند.

گاهی می‌توان چند دستور را پشت سر هم اجرا کرد.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

ابتدا با دستور زیر به سرویس متصل شدیم:  
بعد از اتصال، برنامه از ما درخواست کرد یک IP وارد کنیم و ادعا می‌کرد فقط IP 8.8.8.8 را قبول می‌کند.

</div>

<p align="center">
<img width="981" height="139" alt="image" src="https://github.com/user-attachments/assets/bfe9c90c-16b9-40f4-b26b-abc3d75ef3e6" />
</p>

<div dir="rtl">

ابتدا همان IP مجاز را وارد کردیم و برنامه در پشت صحنه احتمالاً دستوری شبیه این را اجرا کرد: <code>ping -c 2 8.8.8.8</code>

</div>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
<code>nc</code> مخفف <code>Netcat</code> است و برای برقراری ارتباط مستقیم با سرویس‌های شبکه‌ای روی یک Host و Port مشخص استفاده می‌شود.
</blockquote>

<div dir="rtl">

می‌توانیم بعد از IP یک دستور دیگر اضافه کنیم:

</div>

<p align="center">
<img width="1013" height="267" alt="image" src="https://github.com/user-attachments/assets/47d73dbc-80b1-43db-bdbc-2f0a33e6b7f5" />
</p>

<div dir="rtl">

از این خروجی فهمیدیم دو فایل روی سرور وجود دارد.

</div>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
علامت <code>;</code> در Shell یک جداکننده دستور است یعنی اول دستور سمت چپ را اجرا کن و پس از پایان آن، دستور سمت راست را نیز اجرا کن.
</blockquote>

<p align="center">
<img width="1114" height="243" alt="image" src="https://github.com/user-attachments/assets/da1f7fb2-b32d-4ee7-9b12-51610c481c25" />
</p>

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{p1nG_c0mm@nd_3xpL0it_su33essFuL_e003709d}
```

</details>

<br>

<details>
<summary dir="rtl"><strong>🛡️ آسیب‌پذیری OS Command Injection & Shell Command Injection</strong></summary>

<br>

<div dir="rtl">

در این آسیب پذیری کاربر می‌تواند از طریق ورودی برنامه، ساختار دستور سیستم‌عامل را تغییر دهد و دستورهای دیگری اجرا کند.

این مشکل زمانی ایجاد می‌شود که برنامه:

ورودی کاربر را دریافت کند.  
آن را بدون بررسی مناسب به یک رشته دستوری اضافه کند.  
رشته را برای اجرا به Shell بدهد.

</div>

</details>

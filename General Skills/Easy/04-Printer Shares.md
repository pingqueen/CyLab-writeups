<p align="center">
<img width="652" height="665" alt="image" src="https://github.com/user-attachments/assets/6d388fde-6a91-4749-819a-413b03d58843" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

اوه! یک نفر به‌طور اتفاقی یک فایل مهم را برای یک پرینتر شبکه‌ای ارسال کرده است.  
آیا می‌توانی آن فایل را از سرور چاپ بازیابی کنی؟

پرینتر روی پورت 53772 قرار دارد.

می‌توانی برای آزمایش اتصال از دستور زیر استفاده کنی:

</div>

```text
nc -vz mysterious-sea.picoctf.net 53772
```

</details>

<br>

<details>
<summary dir="rtl"><strong>💡 سرنخ</strong></summary>

<br>

<div dir="rtl">

آشنایی با نحوه کار پروتکل SMB مفید خواهد بود.

ابزارهای smbclient و smbutil ابزارهای مناسبی هستند.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

ابتدا بازبودن پورت را بررسی کردیم:

</div>

<p align="center">
<img width="1057" height="94" alt="image" src="https://github.com/user-attachments/assets/646c72b6-e510-4038-b081-70c5da72f961" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
گزینه <code>-v</code> اطلاعات بیشتری نمایش می‌دهد و گزینه <code>-z</code> فقط باز یا بسته بودن پورت را آزمایش می‌کند؛ بدون اینکه وارد ارتباط تعاملی شود.
</blockquote>

<div dir="rtl">

سپس Shareهای SMB سرور را فهرست کردیم:

</div>

<p align="center">
<img width="997" height="212" alt="image" src="https://github.com/user-attachments/assets/d922d979-05fc-4ab0-8d5e-877248789f1a" />
</p>

<div dir="rtl">

از این خروجی فهمیدیم Shareای به نام shares وجود دارد که نوع آن Disk بود؛ یعنی یک پوشه اشتراکی شبکه‌ای که می‌تواند حاوی فایل باشد. وتوضیح آن نیز مشخص می‌کرد Guestها به آن دسترسی دارند.

سپس مستقیماً به Share پیدا‌شده متصل شدیم:

</div>

<p align="center">
<img width="968" height="272" alt="image" src="https://github.com/user-attachments/assets/7bf20e6d-e0ad-4257-bcca-500e11f5a8bd" />
</p>

<div dir="rtl">

دستور ls را داخل محیط smbclient زدیم تا فایل‌ها و پوشه‌های موجود در Share شبکه‌ای را مشاهده کنیم. خروجی نشان داد فایلی به نام flag.txt روی سرور وجود دارد؛ بنابراین در مرحله بعد با دستور get flag.txt آن را از سرور SMB روی سیستم Kali دانلود می‌کنیم.

</div>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور <code>get</code> در <code>smbclient</code> یک فایل راه‌دور را از Share شبکه‌ای روی سیستم محلی دانلود می‌کند.
</blockquote>

<div dir="rtl">

در نهایت محتوای فایل را خواندیم:

</div>

<p align="center">
<img width="432" height="156" alt="image" src="https://github.com/user-attachments/assets/53af2c51-ec0b-48d5-998a-a9195d6c7f24" />
</p>

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{5mb_pr1nter_5h4re5_9fc5e085}
```

</details>

<p align="center">
<img width="663" height="773" alt="image" src="https://github.com/user-attachments/assets/e58b82d2-9328-4c5f-a9ee-5d6ea7bc6c77" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

استفاده از `Secure Shell` یا `SSH` در بسیاری از چالش‌ها و کارهای مرتبط با سیستم‌عامل لینوکس اهمیت زیادی دارد.

در این چالش باید با نام کاربری `ctf-player` از طریق SSH به سرور زیر متصل شویم:

</div>

```text
titan.picoctf.net
```

<div dir="rtl">

سرویس SSH روی Port زیر اجرا می‌شود:

</div>

```text
54330
```

<div dir="rtl">

رمز عبور:

</div>

```text
6dd28e9b
```

<div dir="rtl">

اگر هنگام اتصال درباره Fingerprint سرور از ما سؤال شد، باید با واردکردن `yes` اتصال را تأیید کنیم.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>💡 سرنخ</strong></summary>

<br>

<div dir="rtl">

ساختار کلی اتصال SSH به یک سیستم راه دور به‌صورت زیر است:

</div>

```text
ssh username@hostname
```

<div dir="rtl">

اگر سرویس روی Port پیش‌فرض اجرا نشود، باید Port را نیز با گزینه `-p` مشخص کنیم.

همچنین هنگام تایپ رمز عبور در Shell، هیچ کاراکتر یا علامتی روی صفحه نمایش داده نمی‌شود.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

برای اتصال به سرویس، دستور زیر را در ترمینال اجرا کردیم:

</div>

<p align="center">
<img width="808" height="172" alt="image" src="https://github.com/user-attachments/assets/333158fe-1344-4d3f-b89b-e380b4a63829" />
</p>

<div dir="rtl">

پس از ورود موفق، سرور فلگ را نمایش داد.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{s3cur3_c0nn3ct10n_5d09a462}
```

</details>

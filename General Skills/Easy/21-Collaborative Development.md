<p align="center">
<img width="662" height="691" alt="image" src="https://github.com/user-attachments/assets/713cfb98-2cb0-4f80-a652-4469acdb5e15" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

اعضای تیم من برای اضافه‌کردن قابلیت‌های جدید به برنامه چاپ فلگ بسیار تلاش کرده‌اند. حالا باید بررسی کنیم تغییرات آن‌ها چگونه می‌توانند در کنار یکدیگر کار کنند.

فایل‌های چالش داخل آرشیو زیر قرار دارند:

</div>

```text
challenge.zip
```

</details>

<br>

<details>
<summary dir="rtl"><strong>💡 سرنخ</strong></summary>

<br>

<div dir="rtl">

برای مشاهده Branchهای موجود می‌توان از دستور زیر استفاده کرد:

</div>

```bash
git branch -a
```

<div dir="rtl">

تغییرات Branchهای مختلف باید به Branch اصلی منتقل شوند. برای ثبت Merge Commit نیز ممکن است لازم باشد نام و ایمیل Git را تنظیم کنیم.

هنگام ادغام Branchها ممکن است `Merge Conflict` ایجاد شود. برای رفع آن می‌توان فایل را با ویرایشگری مانند `nano`، `vim` یا `emacs` باز کرد.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

ابتدا فایل موجود در مسیر فعلی را مشاهده کردیم و برای استخراج آن از دستور زیر استفاده کردیم:

</div>

<p align="center">
<img width="469" height="821" alt="image" src="https://github.com/user-attachments/assets/e65e3aed-b860-44a6-b2da-e1305ed066d2" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور unzip فایل‌ها و پوشه‌های موجود در یک آرشیو ZIP را استخراج می‌کند.
</blockquote>

<div dir="rtl">

وارد پوشه استخراج‌شده شدیم:

</div>

<p align="center">
<img width="528" height="215" alt="image" src="https://github.com/user-attachments/assets/20b63975-04af-4049-98c5-8c256e251dfe" />
</p>

<div dir="rtl">

برای مشاهده تمام Branchها دستور زیر را اجرا کردیم:

</div>

<p align="center">
<img width="359" height="140" alt="image" src="https://github.com/user-attachments/assets/a0a884eb-13c2-4b5b-b84f-d0d7e66518cf" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور git branch برای مشاهده و مدیریت شاخه‌های یک مخزن Git استفاده می‌شود. هر Branch مسیر مستقلی از تغییرات و Commitهای پروژه را نشان می‌دهد. گزینه -a تمام شاخه‌ها، شامل شاخه‌های محلی و Remote را نمایش می‌دهد.
</blockquote>

<div dir="rtl">

برای مشاهده تاریخچه همه Branchها به‌شکل گرافیکی از دستور زیر استفاده کردیم:

</div>

<p align="center">
<img width="484" height="182" alt="image" src="https://github.com/user-attachments/assets/fe7f7ae8-6f05-4a0e-a8d6-6694118c325a" />
</p>

<div dir="rtl">

خروجی نشان داد هر Feature Branch از Commit اصلی جدا شده است و هر سه Branch از Commit پایه Branch اصلی ساخته شده‌اند و تغییرات مستقلی روی فایل `flag.py` دارند.

پیش از Merge کردن Branchها، نسخه فایل `flag.py` در هر Branch را بررسی کردیم.

</div>

<p align="center">
<img width="425" height="427" alt="image" src="https://github.com/user-attachments/assets/92796e71-b172-4ac7-9ffd-06891d104701" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور git show برای مشاهده جزئیات یک Commit یا نمایش محتوای یک فایل در یک Commit یا Branch مشخص استفاده می‌شود. این دستور فقط اطلاعات را نمایش می‌دهد و فایل‌های فعلی پروژه را تغییر نمی‌دهد.
</blockquote>

<div dir="rtl">

بدون انجام Merge نیز از همین خروجی‌ها می‌توانستیم سه بخش فلگ را کنار هم قرار دهیم اما هدف آموزشی چالش، ادغام Branchها و رفع تعارض‌های Git است؛ بنابراین تغییرات را به Branch اصلی Merge کردیم.

</div>

```text
picoCTF{t3@mw0rk_
m@k3s_th3_dr3@m_
w0rk_7ffa0077}
```

<div dir="rtl">

برای ساخت Merge Commit، Git باید هویت نویسنده Commit را بداند.

</div>

<p align="center">
<img width="605" height="111" alt="image" src="https://github.com/user-attachments/assets/27b74299-27d4-4472-a3ea-5caf37cdf458" />
</p>

<div dir="rtl">

نام و ایمیل ثبت‌کننده Commitها فقط برای همین مخزن تنظیم می‌شوند.

</div>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور git config --local برای تنظیم مشخصات و تنظیمات Git فقط در Repository فعلی استفاده می‌شود و روی پروژه‌های دیگر تأثیری ندارد.
</blockquote>

<div dir="rtl">

ابتدا Branch اول را با Branch فعلی یعنی `main` ادغام کردیم:

</div>

<p align="center">
<img width="353" height="132" alt="image" src="https://github.com/user-attachments/assets/5c44ba8b-ddfc-4e4d-9945-faeb0a7caa58" />
</p>

<div dir="rtl">

این Merge از نوع Fast-forward بود. در Fast-forward، Branch اصلی از زمان ساخته‌شدن Feature Branch تغییر نکرده است. بنابراین Git فقط اشاره‌گر Branch اصلی را به Commit جدید جلو می‌برد و نیازی به ساخت Merge Commit جداگانه ندارد.

سپس دستور زیر را اجرا کردیم:

</div>

<p align="center">
<img width="698" height="121" alt="image" src="https://github.com/user-attachments/assets/616705ef-dcf5-4ac0-a654-21f3ca2a6644" />
</p>

<div dir="rtl">

این بار Git نتوانست تغییرات را به‌صورت خودکار ادغام کند علت این بود که Branch اول و Branch دوم هر دو بخش مشابهی از فایل `flag.py` را نسبت به Commit پایه تغییر داده بودند.

</div>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور git merge برای ادغام تغییرات یک Branch با Branch فعلی استفاده می‌شود. اگر دو Branch بخش یکسانی از یک فایل را تغییر داده باشند، ممکن است Merge Conflict ایجاد شود و فایل نیاز به اصلاح دستی داشته باشد.
</blockquote>

<div dir="rtl">

تمام Conflict Markerها را حذف و هر دو خط را به‌ترتیب صحیح نگه داشتیم:

</div>

<p align="center">
<img width="401" height="369" alt="image" src="https://github.com/user-attachments/assets/75e91a4a-262e-4a40-bcbd-5045d9636aad" />
</p>

<div dir="rtl">

پس از اصلاح فایل، آن را به Staging Area اضافه کردیم:

</div>

<p align="center">
<img width="325" height="52" alt="image" src="https://github.com/user-attachments/assets/83f8e32d-2fd8-4379-af08-1518249cfdac" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور git add تغییرات فایل‌ها را به Staging Area اضافه می‌کند تا برای Commit آماده شوند. بعد از رفع Merge Conflict نیز با این دستور به Git اعلام می‌کنیم که فایل اصلاح شده است.
</blockquote>

<div dir="rtl">

سپس Merge Commit را ایجاد کردیم:

</div>

<p align="center">
<img width="441" height="75" alt="image" src="https://github.com/user-attachments/assets/e86b1291-d4b4-4b9c-a8b7-7dcd578532c3" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور git commit -m تغییرات موجود در Staging Area را همراه با یک پیام توضیحی در تاریخچه Git ثبت می‌کند. گزینه -m اجازه می‌دهد پیام Commit را مستقیماً در همان دستور وارد کنیم.
</blockquote>

<div dir="rtl">

و Branch سوم را نیز به همین ترتیب Merge کردیم:

</div>

<p align="center">
<img width="672" height="118" alt="image" src="https://github.com/user-attachments/assets/4db4e67b-1132-47c0-a01e-ae7be8da0be1" />
</p><p align="center">
<img width="376" height="415" alt="image" src="https://github.com/user-attachments/assets/50e774fa-15a4-47a5-a4f4-1fb17972eada" />
</p><p align="center">
<img width="425" height="134" alt="image" src="https://github.com/user-attachments/assets/ae2f219f-00b4-4582-8cce-cfdfc6a5d5c1" />
</p>

<div dir="rtl">

در این مرحله تمام تغییرات سه Feature Branch در Branch اصلی قرار داشتند.

برنامه را با Python اجرا کردیم:

</div>

<p align="center">
<img width="505" height="96" alt="image" src="https://github.com/user-attachments/assets/210e5878-0589-43b7-96a2-3d572861af0b" />
</p>

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_7ffa0077}
```

</details>

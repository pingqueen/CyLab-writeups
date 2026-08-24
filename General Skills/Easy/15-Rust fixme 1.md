<p align="center">
<img width="660" height="595" alt="image" src="https://github.com/user-attachments/assets/09008c60-72d5-43ae-b1c7-272e187d6fbd" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

آیا درباره زبان برنامه‌نویسی Rust شنیده‌اید؟

خطاهای نحوی موجود در فایل Rust را اصلاح کنید تا برنامه با موفقیت کامپایل شود و فلگ را نمایش دهد.

فایل کد Rust از صفحه چالش قابل دانلود است.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>💡 سرنخ</strong></summary>

<br>

<div dir="rtl">

ابزار `Cargo` مدیر بسته و  Build زبان Rust است و کار با پروژه را ساده‌تر می‌کند.

برای چاپ خروجی و مقدار متغیرها، مستندات ماکروی زیر را بررسی کنید:

</div>

```rust
println!
```

<div dir="rtl">

کامپایلر Rust معمولاً پیام‌های خطای دقیق و راهنمای مفیدی ارائه می‌دهد؛ بنابراین باید آن‌ها را با دقت بخوانیم.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

پس از دانلود فایل چالش، ابتدا محتویات مسیر فعلی را مشاهده کردیم:

این فایل یک پروژه Rust است که داخل یک Archive فشرده قرار گرفته است. برای استخراج آن، دستور زیر را اجرا کردیم:

</div>

<p align="center">
<img width="566" height="379" alt="image" src="https://github.com/user-attachments/assets/84156c14-f019-4a3a-9a37-c51043338dee" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور tar برای ساخت، مشاهده یا استخراج فایل‌های Archive در لینوکس استفاده می‌شود.
</blockquote>

<p align="center">
<img width="1280" height="627" alt="image" src="https://github.com/user-attachments/assets/81d929f0-c205-4c5b-bc23-bfe07bb09046" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
Cargo مدیر بسته و سیستم ساخت رسمی زبان Rust است و وظیفه‌ای مشابه pip در پایتون و npm در جاوااسکریپت دارد. با Cargo می‌توان پروژه Rust ایجاد کرد، وابستگی‌ها را مدیریت نمود، کد را با کامپایلر rustc کامپایل و اجرا کرد، تست‌ها و مستندات را ساخت و ابزارهای نوشته‌شده با Rust را نصب کرد.
</blockquote>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
زبان برنامه‌نویسی Rust یک زبان مدرن، کامپایل‌شونده، سریع و سطح‌پایین است که برای تولید نرم‌افزارهای پرسرعت، پایدار و کم‌مصرف با کنترل دقیق بر حافظه و سخت‌افزار طراحی شده است. Rust با هدف حفظ سرعت و قدرت زبان‌های C و C++ و در عین حال جلوگیری از خطاهای رایج و خطرناک حافظه مانند Buffer Overflow، Use After Free، Double Free و Data Race ساخته شد. این زبان بدون استفاده از Garbage Collector و با کمک سیستم Ownership و Borrowing، بسیاری از خطاهای حافظه را هنگام کامپایل شناسایی می‌کند. Rust در ساخت سیستم‌عامل‌ها، ابزارهای خط فرمان، سرورها، برنامه‌های شبکه، نرم‌افزارهای امنیتی، بازی‌ها، WebAssembly و ابزارهای CTF کاربرد دارد.
</blockquote>

<div dir="rtl">

برای مشاهده فایل اصلی برنامه دستور زیر را اجرا کردیم و کنار بخش‌های مشکل‌دار کد کامنت‌هایی وجود داشت که ، سؤال‌هایی درباره روش صحیح نوشتن کد مطرح می‌کردند :

</div>

<p align="center">
<img width="1280" height="352" alt="image" src="https://github.com/user-attachments/assets/58b128f3-834f-4729-acae-5ea492a60c9d" />
</p>

<div dir="rtl">

کد اولیه با راهنمایی کامنت‌ها در سه قسمت اصلاح شد:

</div>

<p align="center">
<img width="1280" height="354" alt="image" src="https://github.com/user-attachments/assets/8cef4bed-6467-46ef-bec7-9f34aac72926" />
</p>

<div dir="rtl">

در پایان دستور ساخت متغیر key علامت ; قرار گرفت، زیرا در Rust بیشتر دستورها با سمی‌کالن پایان می‌یابند.

تابع XORCryptor::new(&key) یک مقدار از نوع Result برمی‌گرداند. اگر ساخت رمزگشا با خطا مواجه شود، دستور return; اجرای تابع main را متوقف می‌کند؛ در غیر این صورت با unwrap() مقدار موفق استخراج می‌شود.

برای نمایش مقدار رمزگشایی‌شده، جای‌نگهدار {:?} به println! اضافه شد و داده‌های بایتی با String::from_utf8_lossy به متن قابل‌نمایش تبدیل شدند.

</div>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
Semicolon پایان یک Statement را مشخص می‌کند. نبودن آن می‌تواند باعث شود کامپایلر خط بعدی را بخشی از عبارت قبلی در نظر بگیرد.
</blockquote>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
در تابعی که مقدار بازگشتی آن واحد یا () است، می‌توان از return; بدون مقدار استفاده کرد.
</blockquote>

<div dir="rtl">

پس از ذخیره تغییرات، دوباره دستور زیر را اجرا کردیم:

</div>

<p align="center">
<img width="607" height="108" alt="image" src="https://github.com/user-attachments/assets/8781f70e-3f0c-4088-9a57-2fc955916918" />
</p>

<div dir="rtl">

این بار برنامه با موفقیت کامپایل شد سپس خروجی رمزگشایی‌شده نمایش داده شد.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}
```

</details>

<p align="center">
<img width="659" height="493" alt="image" src="https://github.com/user-attachments/assets/262e6edc-c3c8-466b-bbd7-7fc34762122a" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

ماجرای Rust ادامه دارد!

در این چالش باید مفهوم Borrowing یا قرض‌گرفتن در Rust را بررسی کنیم و خطاهای موجود در کد را اصلاح کنیم تا برنامه بتواند یک رشته را تغییر دهد و فلگ را نمایش دهد.

فایل کد Rust از صفحه چالش قابل دانلود است.

#### سرنخ:
مستندات فصل References and Borrowing در کتاب رسمی Rust می‌تواند برای حل چالش مفید باشد.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

پس از دانلود فایل چالش، ابتدا فایل موجود در مسیر فعلی را مشاهده کردیم:

</div>

<p align="center">
<img width="553" height="372" alt="image" src="https://github.com/user-attachments/assets/e15e8348-1f2a-4d5b-8c98-5e5cdf88b891" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور tar برای ایجاد یا استخراج فایل‌های Archive در لینوکس استفاده می‌شود.
</blockquote>

```text
-x → فایل‌ها را استخراج کن.
-z → فایل با Gzip فشرده شده است.
-f → نام فایل Archive پس از این گزینه قرار می‌گیرد.
```

<div dir="rtl">

برای کامپایل و اجرای پروژه، دستور زیر را اجرا کردیم:

</div>

<p align="center">
<img width="1280" height="648" alt="image" src="https://github.com/user-attachments/assets/91518064-e158-484e-b95d-d3d5b01dd2d2" />
</p>

<div dir="rtl">

کامپایلر Rust دو خطای مشابه نمایش داد:

</div>

```text
نمی‌توان borrowed_string را به‌صورت قابل‌تغییر قرض گرفت،
زیرا پشت یک Reference معمولی از نوع & قرار دارد.
```

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

برای مشاهده کد برنامه دستور زیر را اجرا کردیم:

</div>

<p align="center">
<img width="1280" height="528" alt="image" src="https://github.com/user-attachments/assets/40d04ef6-4d80-4180-b7df-111d9a0f684a" />
</p>

<div dir="rtl">

پس از اعمال تغییرات، بخش‌های مهم برنامه به‌صورت زیر شدند:

</div>

<p align="center">
<img width="1280" height="534" alt="image" src="https://github.com/user-attachments/assets/66ee1762-2f19-4d1a-93f8-28bbf13d48cd" />
</p>

<div dir="rtl">

پس از ذخیره تغییرات، دوباره دستور زیر را اجرا کردیم این بار پروژه بدون خطا کامپایل شد سپس برنامه متن نهایی و فلگ را نمایش داد:

</div>

<p align="center">
<img width="1010" height="143" alt="image" src="https://github.com/user-attachments/assets/4c081f5a-845e-4087-9fe8-031fefc2eba1" />
</p>

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{4r3_y0u_h4v1n5_fun_y31?}
```

</details>

<br>

<details>
<summary dir="rtl"><strong>📚 مفهوم Borrowing و References</strong></summary>

<br>

<div dir="rtl">

مفهوم Borrowing در Rust یعنی دسترسی موقت به یک مقدار بدون انتقال مالکیت آن و Reference ابزاری است که این دسترسی را فراهم می‌کند. Reference معمولی با &T فقط اجازه خواندن می‌دهد، درحالی‌که &mut T اجازه تغییر مقدار را نیز دارد. Rust در هر لحظه یا چند Reference تغییرناپذیر و یا فقط یک Reference تغییرپذیر را مجاز می‌داند و ترکیب هم‌زمان آن‌ها را ممنوع می‌کند. این قوانین باعث جلوگیری از Dangling Reference، تغییر هم‌زمان داده و بسیاری از خطاهای حافظه و Data Raceها می‌شوند.

در این کد متغیر party_foul یک دفترچه است و مالک اصلی آن تابع main است:

</div>

```text
let party_foul = String::from("...");
```

<div dir="rtl">

حالا تابع decrypt می‌خواهد این دفترچه را بگیرد و چیزی به متنش اضافه کند.

حالت اول: &String

</div>

```text
fn decrypt(borrowed_string: &String)
```

<div dir="rtl">

این یعنی:

«دفترچه را فقط برای خواندن به تابع قرض می‌دهم؛ حق نوشتن داخلش را نداری.»

پس این دستور خطا می‌دهد:

</div>

```text
borrowed_string.push_str("...");
```

<div dir="rtl">

چون push_str می‌خواهد متن رشته را تغییر دهد، اما تابع فقط اجازه خواندن دارد.

حالت دوم: &mut String

برای اینکه تابع اجازه تغییر رشته را داشته باشد، باید بنویسیم:

</div>

```text
fn decrypt(borrowed_string: &mut String)
```

<div dir="rtl">

این یعنی:

«دفترچه را موقتاً به تو قرض می‌دهم و اجازه داری داخلش چیزی بنویسی، ولی مالک آن نمی‌شوی.»

متغیر اصلی نیز باید تغییرپذیر باشد:

</div>

```text
let mut party_foul = String::from(
    "Using memory unsafe languages is a: "
);
```

<div dir="rtl">

و هنگام فرستادن به تابع باید بنویسیم:

</div>

```text
decrypt(encrypted_buffer, &mut party_foul);
```

<div dir="rtl">

در نتیجه تابع می‌تواند این کار را انجام دهد:

</div>

```text
borrowed_string.push_str("PARTY FOUL! Here is your flag: ");
```

<div dir="rtl">

و فلگ رمزگشایی‌شده را هم به انتهای همان رشته اضافه کند.

معنی علامت‌ها

</div>

```text
mut party_foul
```

<div dir="rtl">

یعنی خود متغیر قابلیت تغییر دارد.

</div>

```text
&mut party_foul
```

<div dir="rtl">

یعنی متغیر را به‌صورت تغییرپذیر به تابع قرض می‌دهیم.

</div>

```text
borrowed_string: &mut String
```

<div dir="rtl">

یعنی تابع یک رشته قرضی دریافت می‌کند که اجازه تغییرش را دارد.

کل ماجرا در یک جمله:

تابع decrypt نمی‌خواهد مالک party_foul شود؛ فقط می‌خواهد آن را موقتاً قرض بگیرد و متن فلگ را به آن اضافه کند، بنابراین باید از &mut String استفاده کنیم.

</div>

</details>

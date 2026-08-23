<p align="center">
<img width="655" height="656" alt="image" src="https://github.com/user-attachments/assets/ae99c00e-8997-472d-99eb-02b0d19a9591" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

ما یک فایل مشکوک را از یک سیستم رهگیری کرده‌ایم، اما این فایل به‌جای خود رمز عبور، فقط هش <code>SHA-1</code> آن را در اختیار ما قرار می‌دهد.

با استفاده از تکنیک‌های <code>OSINT</code>، اطلاعات شخصی هدف در اختیار ما قرار گرفته است. وظیفه ما این است که با استفاده از این اطلاعات، یک فهرست رمز عبور اختصاصی یا <strong>Custom Wordlist</strong> بسازیم و رمز اصلی را با مقایسه هش آن بازیابی کنیم.

فایل‌های زیر برای حل چالش در اختیار ما قرار دارند:

</div>

```text
userinfo.txt
hash.txt
check_password.py
```

<div dir="rtl">

- فایل <code>userinfo.txt</code> شامل اطلاعات شخصی هدف است.
- فایل <code>hash.txt</code> شامل هش <code>SHA-1</code> رمز عبور است.
- فایل <code>check_password.py</code> رمزهای موجود در Wordlist را آزمایش می‌کند.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>💡 سرنخ</strong></summary>

<br>

<div dir="rtl">

ابزار <code>CUPP</code> یک ابزار پایتونی برای تولید Wordlist اختصاصی با استفاده از اطلاعات شخصی افراد است.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

ابتدا با دستور زیر فایل‌های موجود در مسیر فعلی را مشاهده کردیم:

</div>

<p align="center">
<img width="393" height="77" alt="image" src="https://github.com/user-attachments/assets/b13cf0a4-a63d-4a53-bfe2-69e40fa64ab6" />
</p>

<div dir="rtl">

سپس برای بررسی نحوه کار اسکریپت، محتوای فایل <code>check_password.py</code> را مشاهده کردیم:

</div>

<p align="center">
<img width="747" height="529" alt="image" src="https://github.com/user-attachments/assets/66a3adf6-c453-4352-ad08-9889b0803a10" />
</p>

<div dir="rtl">

کد اسکریپت به‌صورت زیر عمل می‌کند:

در ابتدای برنامه، کتابخانه <code>hashlib</code> وارد شده است:

</div>

```python
import hashlib
```

<div dir="rtl">

این کتابخانه امکان محاسبه هش‌هایی مانند <code>SHA-1</code>، <code>SHA-256</code> و <code>MD5</code> را در Python فراهم می‌کند.

در ادامه، نام فایل هش و Wordlist مشخص شده است:

</div>

```python
HASH_FILE = "hash.txt"
WORDLIST_FILE = "passwords.txt"
```

<div dir="rtl">

بنابراین اسکریپت انتظار دارد:

- هش هدف داخل فایل <code>hash.txt</code> باشد.
- رمزهای احتمالی داخل فایل <code>passwords.txt</code> قرار داشته باشند.

تابع <code>load_hash()</code> فایل هش را باز می‌کند:

</div>

```python
with open(HASH_FILE, "r") as f:
    return f.read().strip()
```

<div dir="rtl">

حالت <code>"r"</code> یعنی فایل فقط برای خواندن باز می‌شود. متد <code>strip()</code> نیز فاصله‌ها و کاراکتر خط جدید ابتدا و انتهای متن را حذف می‌کند.

تابع <code>crack_password()</code> فایل Wordlist را خط‌به‌خط بررسی می‌کند:

</div>

```python
for password in f:
```

<div dir="rtl">

هر خط به‌عنوان یک رمز احتمالی در نظر گرفته می‌شود. سپس رمز به بایت تبدیل شده و هش <code>SHA-1</code> آن محاسبه می‌شود:

</div>

```python
hashlib.sha1(password.encode()).hexdigest()
```

<div dir="rtl">

- متد <code>encode()</code> رشته را به بایت تبدیل می‌کند.
- تابع <code>sha1()</code> هش SHA-1 داده را محاسبه می‌کند.
- متد <code>hexdigest()</code> نتیجه را به‌صورت یک رشته هگزادسیمال نمایش می‌دهد.

اگر هش رمز احتمالی با هش هدف برابر باشد، همان رمز بازگردانده می‌شود:

</div>

```python
if hashlib.sha1(password.encode()).hexdigest() == target_hash:
    return password
```

<div dir="rtl">

در نهایت، اسکریپت رمز پیدا‌شده را داخل قالب فلگ قرار می‌دهد:

</div>

```python
print(f"Password found: picoCTF{{{result}}}")
```

<div dir="rtl">

برای مشاهده هش هدف و اطلاعات شخصی کاربر، دستورهای زیر را اجرا کردیم:

</div>

<p align="center">
<img width="380" height="73" alt="image" src="https://github.com/user-attachments/assets/6ac513f8-7c73-44cf-8481-63f4d5118b96" />
</p>

<p align="center">
<img width="241" height="175" alt="image" src="https://github.com/user-attachments/assets/40c2a687-81cd-4311-8a68-6558592d6715" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
SHA-1 یک تابع هش است که ورودی را به یک مقدار هگزادسیمال 160 بیتی تبدیل می‌کند. هش‌کردن با رمزگذاری متفاوت است؛ برای SHA-1 کلید رمزگشایی مستقیمی وجود ندارد و برای یافتن ورودی معمولاً باید رمزهای احتمالی را هش و با مقدار هدف مقایسه کرد.
</blockquote>

<div dir="rtl">

برای تولید Wordlist اختصاصی از ابزار <code>CUPP</code> استفاده کردیم:

</div>

<p align="center">
<img width="775" height="831" alt="image" src="https://github.com/user-attachments/assets/894c531f-a02d-47b9-ae99-5cc07ae66d48" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
CUPP مخفف Common User Passwords Profiler است. این ابزار با دریافت اطلاعات شخصی هدف، ترکیب‌های رایج رمز عبور را تولید می‌کند. گزینه <code>-i</code> حالت تعاملی یا Interactive Mode را فعال می‌کند.
</blockquote>

<div dir="rtl">

اطلاعات موجود در فایل <code>userinfo.txt</code> را در قسمت‌های مربوط وارد کردیم و برای اطلاعاتی که در اختیار نداشتیم، مانند تاریخ تولد همسر، نام حیوان خانگی یا نام شرکت، کلید Enter را زدیم تا خالی باقی بمانند.

در پایان، CUPP عملیات ساخت Wordlist را آغاز کرد و فایل زیر را ایجاد کرد:

</div>

<p align="center">
<img width="917" height="261" alt="image" src="https://github.com/user-attachments/assets/389fe61c-3cf3-4233-b411-ede4db59da71" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
گزینه <code>-l</code> اطلاعات کامل فایل مانند سطح دسترسی، مالک، اندازه و تاریخ را نمایش می‌دهد. گزینه <code>-a</code> فایل‌های مخفی را نیز نشان می‌دهد و گزینه <code>-h</code> اندازه فایل را به‌صورت خوانا مانند KB و MB نمایش می‌دهد.
</blockquote>

<div dir="rtl">

اسکریپت <code>check_password.py</code> به‌دنبال فایلی با نام زیر می‌گردد:

</div>

```text
passwords.txt
```

<div dir="rtl">

اما CUPP فایل را با نام <code>alice.txt</code> ساخته بود. بنابراین فایل تولیدشده را با نام مورد انتظار اسکریپت کپی کردیم:

</div>

<p align="center">
<img width="369" height="133" alt="image" src="https://github.com/user-attachments/assets/546435ab-5c4d-461d-83d6-7c8f1d45d227" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور <code>cp</code> برای کپی‌کردن فایل‌ها و پوشه‌ها استفاده می‌شود.
</blockquote>

<div dir="rtl">

اسکریپت رمزهای موجود در <code>passwords.txt</code> را یکی‌یکی خواند، هش <code>SHA-1</code> هر رمز را محاسبه کرد و آن را با هش موجود در <code>hash.txt</code> مقایسه کرد.

رمزی که هش آن با مقدار هدف یکسان بود، به‌صورت زیر پیدا شد:

</div>

```text
Aj_15901990
```

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{Aj_15901990}
```

</details>

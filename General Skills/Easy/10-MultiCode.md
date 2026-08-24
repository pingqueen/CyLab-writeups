<p align="center">
<img width="663" height="572" alt="image" src="https://github.com/user-attachments/assets/a56bfc7d-3903-4a0c-8ed4-bb409f5180f9" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

ما یک پیام را رهگیری کرده‌ایم که به‌شکل مشکوکی کدگذاری شده است و مشخص است که یک فلگ را مخفی می‌کند.

در این چالش با رمزنگاری روبه‌رو نیستیم؛ بلکه چندین لایه کدگذاری و مبهم‌سازی روی پیام اعمال شده است. باید این لایه‌ها را به‌ترتیب معکوس کنیم تا به فلگ اصلی برسیم.

فایل زیر برای حل چالش در اختیار ما قرار دارد:

</div>

```text
message.txt
```

</details>

<br>

<details>
<summary dir="rtl"><strong>💡 سرنخ</strong></summary>

<br>

<div dir="rtl">

فلگ در چند لایه از کدگذاری‌های رایج مانند موارد زیر پیچیده شده است:

</div>

```text
ROT13
URL Encoding
Hex
Base64
```

<div dir="rtl">

باید ترتیب این لایه‌ها را تشخیص دهیم و آن‌ها را از بیرونی‌ترین لایه به درونی‌ترین لایه باز کنیم.

همچنین می‌توان از ابزاری مانند <code>CyberChef</code> برای بررسی و رمزگشایی مرحله‌ای استفاده کرد.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

ابتدا محتوای فایل <code>message.txt</code> را با دستور زیر مشاهده کردیم:

</div>

<p align="center">
<img width="920" height="71" alt="image" src="https://github.com/user-attachments/assets/60f543a7-5a13-4b7e-9320-4908d1ace731" />
</p>

<div dir="rtl">

از وجود کاراکتر <code>=</code> در انتهای رشته و ساختار حروف و اعداد آن می‌توان حدس زد که اولین لایه، <code>Base64</code> است.

</div>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
وجود <code>=</code> در انتهای یک رشته الزاماً Base64 بودن آن را ثابت نمی‌کند، اما یکی از نشانه‌های رایج Padding در Base64 است.
</blockquote>

<div dir="rtl">

برای بازکردن لایه Base64 از دستور زیر استفاده کردیم:

</div>

<p align="center">
<img width="1204" height="74" alt="image" src="https://github.com/user-attachments/assets/0c3ddb4e-31cc-4e13-92a7-66e0c7359ab3" />
</p>

<div dir="rtl">

این خروجی فقط از رقم‌های <code>0</code> تا <code>9</code> و حروف <code>a</code> تا <code>f</code> تشکیل شده و طول آن نیز زوج است؛ بنابراین احتمال می‌دهیم رشته به‌صورت Hexadecimal نمایش داده شده باشد.

</div>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور <code>printf</code> متن مشخص‌شده را در خروجی چاپ می‌کند. گزینه یا قالب <code>%s</code> باعث می‌شود مقدار به‌عنوان یک رشته چاپ شود. برخلاف استفاده معمول از echo، دستور printf به‌صورت خودکار کاراکتر خط جدید به انتهای داده اضافه نمی‌کند.
</blockquote>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور <code>base64 -d</code> برای رمزگشایی Base64 استفاده می‌شود. گزینه <code>-d</code> مخفف decode است؛ یعنی داده Base64 را رمزگشایی کن.
</blockquote>

<div dir="rtl">

برای تبدیل رشته Hex به متن اصلی از دستور زیر استفاده کردیم:

</div>

<p align="center">
<img width="950" height="68" alt="image" src="https://github.com/user-attachments/assets/6f0ab9e8-3af0-4dcf-8e25-255f40cc66bf" />
</p>

<div dir="rtl">

در رشته به‌دست‌آمده، مقادیری مانند <code>%7B</code> و <code>%7D</code> دیده می‌شوند. این ساختار مربوط به <code>URL Encoding</code> یا <code>Percent Encoding</code> است.

</div>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
دستور <code>xxd</code> معمولاً داده را به شکل Hexadecimal نمایش می‌دهد، اما با گزینه <code>-r</code> عملیات برعکس انجام می‌شود: یعنی نمایش Hex را دوباره به بایت‌ها و متن اصلی تبدیل کن و گزینه <code>-p</code> نیز حالت Plain Hexdump را مشخص می‌کند؛ یعنی ورودی فقط شامل رقم‌های Hex است و آدرس حافظه یا ستون‌های اضافی ندارد.
</blockquote>

<div dir="rtl">

برای رمزگشایی این لایه از ماژول <code>urllib.parse</code> در Python استفاده کردیم:

</div>

<p align="center">
<img width="969" height="76" alt="image" src="https://github.com/user-attachments/assets/963441f2-551d-4c6b-ad5c-92b0873433f5" />
</p>

<div dir="rtl">

گزینه <code>-c</code> در Python به ما اجازه می‌دهد یک قطعه کد کوتاه را مستقیماً از خط فرمان اجرا کنیم:

</div>

```text
-c → command
```

<div dir="rtl">

در این دستور ابتدا ماژول زیر وارد می‌شود:

</div>

```python
import urllib.parse
```

<div dir="rtl">

سپس تابع <code>unquote()</code> کاراکترهای URL-encoded را به حالت عادی بازمی‌گرداند:

</div>

```python
urllib.parse.unquote(...)
```

<div dir="rtl">

برای مثال:

</div>

```text
%7B → {
%7D → }
```

<div dir="rtl">

ساختار آکولادها اکنون شبیه قالب فلگ picoCTF است، اما حروف همچنان معنی درستی ندارند. با توجه به سرنخ چالش، آخرین لایه <code>ROT13</code> است.

برای اعمال ROT13 از ماژول <code>codecs</code> در Python استفاده کردیم:

</div>

<p align="center">
<img width="900" height="70" alt="image" src="https://github.com/user-attachments/assets/d1697a18-32ae-495a-b8a1-95e1dd19b04a" />
</p>

<div dir="rtl">

در این دستور ماژول زیر وارد می‌شود:

</div>

```python
import codecs
```

<div dir="rtl">

سپس تابع <code>decode()</code> با روش <code>rot_13</code> روی رشته اجرا می‌شود:

</div>

```python
codecs.decode(text, 'rot_13')
```

<div dir="rtl">

روش <code>ROT13</code> هر حرف انگلیسی را ۱۳ خانه در الفبا جابه‌جا می‌کند. برای مثال:

</div>

```text
a → n
b → o
c → p
...
n → a
o → b
p → c
```

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{nested_enc0ding_481f064c}
```

</details>

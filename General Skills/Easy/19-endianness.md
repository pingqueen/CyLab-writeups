<p align="center">
<img width="659" height="720" alt="image" src="https://github.com/user-attachments/assets/8e4457a5-7a4f-41ee-a9a8-109ebf5fd4d0" />
</p>

<br>

<details>
<summary dir="rtl"><strong>❓ متن سؤال</strong></summary>

<br>

<div dir="rtl">

آیا با مفاهیم `Little Endian` و `Big Endian` آشنایی دارید؟

برای حل چالش باید به سرویس زیر متصل شویم:

</div>

```text
nc titan.picoctf.net 63230
```

</details>

<br>

<details>
<summary dir="rtl"><strong>💡 سرنخ</strong></summary>

<br>

<div dir="rtl">

ابتدا می‌توانیم با استفاده از جدول ASCII، مقدار هگزادسیمال هر کاراکتر را پیدا کنیم.

سپس باید ترتیب بایت‌ها را براساس نوع Endianness مشخص کنیم.

</div>

</details>

<br>

<details>
<summary dir="rtl"><strong>🛠️ راه حل</strong></summary>

<br>

<div dir="rtl">

ابتدا با دستور زیر به سرویس چالش متصل شدیم:

</div>

<p align="center">
<img width="673" height="206" alt="image" src="https://github.com/user-attachments/assets/58dc3e0b-3948-441f-9dc2-4d91e845bfde" />
</p>

<blockquote dir="rtl">
<strong>📝 نکته</strong>
<br><br>
nc مخفف Netcat است. این ابزار برای برقراری ارتباط مستقیم با یک سرویس شبکه‌ای روی یک Host و Port مشخص استفاده می‌شود.
</blockquote>

<div dir="rtl">

در این چالش باید نمایش Big Endian و Little Endian یک کلمه را بر اساس کدهای هگزادسیمال ASCII به‌دست آوریم. برنامه پس از اتصال، کلمه زیر را نمایش داد:

</div>

```text
ntzpd
```

<div dir="rtl">

هر حرف کلمه را با استفاده از جدول ASCII به مقدار Hex تبدیل می‌کنیم:
| حرف | ASCII Hex |
| --: | :-------- |
| `n` | `6E`      |
| `t` | `74`      |
| `z` | `7A`      |
| `p` | `70`      |
| `d` | `64`      |

در Big Endian بایت‌ها با همان ترتیب اصلی نوشته می‌شوند:

</div>

```text
6E 74 7A 70 64
```

<div dir="rtl">

در Little Endian ترتیب بایت‌ها برعکس می‌شود:

</div>

```text
64 70 7A 74 6E
```

</details>

<br>

<details>
<summary dir="rtl"><strong>🚩 فلگ نهایی ✅</strong></summary>

<br>

```text
picoCTF{3ndi4n_sw4p_su33ess_25c5f083}
```

</details>

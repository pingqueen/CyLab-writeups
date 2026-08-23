<img width="659" height="720" alt="image" src="https://github.com/user-attachments/assets/8e4457a5-7a4f-41ee-a9a8-109ebf5fd4d0" />

#### متن سؤال:
آیا با مفاهیم `Little Endian` و `Big Endian` آشنایی دارید؟

برای حل چالش باید به سرویس زیر متصل شویم:

```text
nc titan.picoctf.net 63230
```

#### سرنخ‌ها:
ابتدا می‌توانیم با استفاده از جدول ASCII، مقدار هگزادسیمال هر کاراکتر را پیدا کنیم.

سپس باید ترتیب بایت‌ها را براساس نوع Endianness مشخص کنیم.

***

#### مراحل حل:
ابتدا با دستور زیر به سرویس چالش متصل شدیم:

<img width="673" height="206" alt="image" src="https://github.com/user-attachments/assets/58dc3e0b-3948-441f-9dc2-4d91e845bfde" />

`نکته: nc مخفف Netcat است. این ابزار برای برقراری ارتباط مستقیم با یک سرویس شبکه‌ای روی یک Host و Port مشخص استفاده می‌شود.`

در این چالش باید نمایش Big Endian و Little Endian یک کلمه را بر اساس کدهای هگزادسیمال ASCII به‌دست آوریم. برنامه پس از اتصال، کلمه زیر را نمایش داد:
```text
ntzpd
```
هر حرف کلمه را با استفاده از جدول ASCII به مقدار Hex تبدیل می‌کنیم:
| حرف | ASCII Hex |
| --: | :-------- |
| `n` | `6E`      |
| `t` | `74`      |
| `z` | `7A`      |
| `p` | `70`      |
| `d` | `64`      |

در Big Endian بایت‌ها با همان ترتیب اصلی نوشته می‌شوند:
```text
6E 74 7A 70 64
```
در Little Endian ترتیب بایت‌ها برعکس می‌شود:
```text
64 70 7A 74 6E
```

فلگ نهایی:

```text
picoCTF{3ndi4n_sw4p_su33ess_25c5f083}
```

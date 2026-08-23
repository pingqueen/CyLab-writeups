<img width="670" height="531" alt="image" src="https://github.com/user-attachments/assets/129a4e16-63c9-4678-8999-291afb76c26c" />

#### متن سؤال:
آیا می‌توانید محتوای این فایل را درک کنید؟
فایل دانلودشده:

```text
enc_flag
```

#### سرنخ:
چند بار Decode کردن همیشه می‌تواند مفید باشد.

این سرنخ نشان می‌دهد که فایل فقط یک بار کدگذاری نشده و پس از هر مرحله رمزگشایی، احتمالاً دوباره یک رشته کدگذاری‌شده به‌دست می‌آید.

***

#### مراحل حل:
ابتدا فایل‌های موجود در مسیر فعلی را با دستور زیر مشاهده کردیم:

<img width="701" height="227" alt="image" src="https://github.com/user-attachments/assets/7ed19f15-12ff-4d89-9751-3986355e86f6" />

محتوای فایل یک رشته طولانی شامل حروف انگلیسی، اعداد و علامت `=` بود.

این ساختار یکی از نشانه‌های رایج Base64 است:

```text
حروف بزرگ و کوچک انگلیسی
اعداد
کاراکترهای + و /
علامت = در انتهای داده برای Padding
```

بنابراین اولین حدس ما این بود که فایل با Base64 کدگذاری شده است.

`نکته: وجود علامت = به‌تنهایی Base64 بودن داده را قطعی نمی‌کند، اما همراه با ساختار مناسب رشته، نشانه مهمی محسوب می‌شود.`

برای رمزگشایی اولین لایه از دستور زیر استفاده کردیم:

<img width="714" height="185" alt="image" src="https://github.com/user-attachments/assets/1388eaf9-12a2-44ed-9986-40deab4171fa" />

بعد از مشاهده فایل، متوجه شدیم خروجی همچنان شبیه Base64 است؛ بنابراین باید رمزگشایی را ادامه دهیم.

<img width="713" height="167" alt="image" src="https://github.com/user-attachments/assets/f42691f8-9f29-4cdd-89ca-ec44b6bb03ed" />

رمزگشایی را تا زمانی که دیگر خروجی یک رشته Base64 نباشد به همین ترتیب ادامه میدهیم:

3- <img width="712" height="146" alt="image" src="https://github.com/user-attachments/assets/ccf8823a-4dc0-4803-98c4-fdcaa717bbf6" />

4-<img width="733" height="145" alt="image" src="https://github.com/user-attachments/assets/0b702b77-9f98-4bed-a5dd-933a10529f58" />

5- <img width="733" height="145" alt="image" src="https://github.com/user-attachments/assets/407f7ce6-ace0-4ece-b549-b15afe487392" />

6- <img width="686" height="132" alt="image" src="https://github.com/user-attachments/assets/2d94ed5f-f13c-4075-b05b-ead66cb9af44" />

7- <img width="489" height="132" alt="image" src="https://github.com/user-attachments/assets/683f9eb6-8c1c-4748-ba0b-2fcc1a0401f5" />

دستورات اجراشده نشان می‌دهند که فایل شش بار با Base64 کدگذاری شده بود.

فلگ نهایی:

```text
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_4557ec3e}
```

# بررسی اجمالی

این برنامه میاد روی سرور خارجتون نه لزوما سرور اصلی نصب میشه بعد میاد  آیپی سرور های ایرانتون رو با دامه هایی که با این آیپی ها ست شده  برسی میکنه بعد هر 120 ثانیه وضعیت اتصال tcp سرورها رو چک میکنه ،   هر کدوم از سرورها به مشکل بخوره و  پینگی دریافت نشه ، به صورت رندوم آیپی اون ساب دامنه رو تغییر میده و   هر 20 ثانیه اون سروری که  مشکل اتصال داره  چک میکنه  زمانی که اتصال سرور دوباره برقرار شد  ساب دامین رو به حالت اول برمیگردونه . .

# توجه
- همه سرورهای ایرانتون باید  تانل شده  باشن 

- برای مثال اگه شما یک سرور خارج دارید حتما باید روی تمام سرور های ایران تانل شده باشه و با هر ایپی ایران بشه متصل شد

-  سروری که این برنامه روش نصب هستش نباید ریست بشه با هر ریستارت باید دوباره برنامه رو ران کنید


# راهنمای نصب
برای نصب کافیه دستور زیر رو اجرا کنید

```bash
curl -Ls https://raw.githubusercontent.com/Free-Guy-IR/cloudflareAuto_change_ip/main/install.sh | bash

```


وقتی نصب تمام شد:
باید دستورات زیر رو بزنید 

```bash
cd cloudflareAuto_change_ip

nano cloudflareAuto_change_ip.py
```
وقتی فایل  باز شد باید بخش های زیر رو جایگزین کنید 

در قسمت ** api_cloudflare ** باید  Global API Key	 اکانت کلودفلرتون رو قرار بدید.


```
API_TOKEN = 'api_cloudflare' 
```
در  domain_zone_id  هم وقتی وارد دامنه میشید در بخش  Overview
 قسمت api نوشته Zone ID
  باید Zone ID هر دامنه  رو جایگزین کنیدش .

```
ZONE_IDS = [
    'ZONE_IDS1',
    'ZONE_IDS2'
]'
```



------

در بخش :
```
ADDRESSES = [
    (8587, 'ip_server_iran1'),
    (8586, 'ip_server_iran2'),
    (8585, 'ip_server_iran3'),
    (8584, 'ip_server_iran4'),
    (8583, 'ip_server_iran5'),
    (8582, 'ip_server_iran6'),
    (8581, 'ip_server_iran7'),
]
```
 باید آیپی سرور های ایرانتون رو همراه با پورت های تانلتون رو 
 قرار بدید 

 ** پورت ها حتما باید روی سرورها باز باشن **


------

در بخش :
```
TELEGRAM_TOKEN = 'token_telegram'
CHAT_ID = 'admin_id'
```

باید اطلاعات ربات تلگرام و آیدی عددی اکانت تلگرامتون که  ربات لاگ هارو براتون بفرسته رو باید قرار بدید 

داخل فایل 
```
time.sleep(120)
```
زمان هر برسیو نشون میده که اینجا 120 ثانیه هستش میتونید هر بخش کد این مورد رو دید تغییر بدید البته من پیشنهاد نمیکنم .


---------

وقتی  تغییرات انجام دادید فایل رو ذخیره کنید و دستورات زیر رو وارد کنید

```
screen

python3 cloudflareAuto_change_ip.py

```


 [لینک کانال تلگرام اطلاع رسانی بروزرسانی های من](https://t.me/Freeguy_IR)


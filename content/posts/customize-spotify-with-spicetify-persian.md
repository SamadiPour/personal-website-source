+++
draft = false
title= "Customize Spotify With Spicetify | Persian"
date= 2020-07-06T14:56:44+04:30
description = "نحوه شخصی سازی و نصب تم برای اسپاتیفای"
images = ["/images/customize-spotify-with-spicetify/1.png"]
slug = "" 
tags = ["Tutorial","Persian","Customization"]
[ author ]
  name = "Amir Hossein SamadiPour"
+++

{{< single-image "/images/customize-spotify-with-spicetify/1.png" >}}

<br>

<div class="persian">
میلیون ها نفر از برنامه فوق العاده Spotify برای گوش دادن به موسیقی به صورت آنلاین گوش میدهند. تا حالا شده به این فکر کنید که چی میشد اگر این برنامه کمی قشنگ تر میشد؟
خب لازم نیست دیگه بیشتر فکر کنید😅 تو این مطلب بهتون یاد میدم که چطوری اونو شخصی سازی کنید.

# نصب برنامه

## ویندوز
برای نصب روی ویندوز ابتدا `PowerShell` رو اجرا کنید و دستور زیر را در آن اجرا کنید:

```powershell
Invoke-WebRequest -UseBasicParsing "https://raw.githubusercontent.com/khanhas/spicetify-cli/master/install.ps1" | Invoke-Expression
```

## لینوکس و مک
خودتون بلدید دیگه😁

```shell script
curl -fsSL https://raw.githubusercontent.com/khanhas/spicetify-cli/master/install.sh | sh
```

<br>

برای اطمینان از نصب برنامه میتوانید دستور زیر را اجرا کنید:

```powershell
spicetify -v
```


اگر در نصب به مشکلی خوردید یا علاقه داشتید که روش های دیگر را ببینید، به
 [صفحه نصب برنامه](https://github.com/khanhas/spicetify-cli/wiki/Installation)
 مراجعه کنید.


# آماده سازی اولیه
اگر تا الان هیچ دستوری از برنامه رو نزدید، یک بار دستور `spicetify` را در هر محیطی که هستید اجرا کنید تا فایل Config ساخته بشه.   
سپس برای گرفتن بکاپ از تم اصلی اسپاتیفای و اعمال تم پیش‌فرض Spicetify، دستور زیر را اجرا کنید:

```shell script
spicetify backup apply enable-devtool
```
{{< gallery "/images/customize-spotify-with-spicetify/2.png" "/images/customize-spotify-with-spicetify/3.png" >}}

<br>

در هر زمانی که خواستید، می توانید با دستور زیر به تم اصلی اسپاتیفای برگردید


```shell script
spicetify restore
```


# شخصی سازی
تمام تم های این برنامه از دو فایل مهم `color.ini` و `user.css` استفاده میکنند. ولی قبل از که با این دو فایل آشنا بشید باید درمورد فایل کانفیگ بدونید.
آدرس این فایل رو میتونید به شکل زیر پیدا کنید:
</div>

**Windows**: `%userprofile%\.spicetify\config.ini`   
**MacOS**: `~/spicetify_data/config.ini`   
**Linux**: 
- `$XDG_CONFIG_HOME/.config/spicetify/config.ini` 
- `~/.config/spicetify/config.ini`   

<div class="persian">

اگر بازم پیداش نکردید، دستور `spicetify -c` رو بزنید تا آدرس کامل رو بهتون بگه.

## فایل Config.ini
در اینجا توضیح چند تا از پارامتر هارو میدم.

{{< single-image "/images/customize-spotify-with-spicetify/4.png" >}}

`current_theme`: اسم پوشه تم فعلی. معمولا اسم تم پیش‌فرض خود برنامه است که در مراحل بعد قراره اونو عوض کنیم.   
`color_scheme`: به کانفیگ استفاده شده از فایل `color.ini` اشاره میکند. درصورتی که خالی باشد، از اولین کانفیگ استفاده می کند.   
`inject_css`: درصورت داشتن مقدار `1` به این معنی است که فایل `user.css` بر روی اسپاتیفای اعمال می شود.   
`replace_colors`: درصورت داشتن مقدار `1` به این معنی است که فایل `color.ini` بر روی اسپاتیفای اعمال می شود.   
`spotify_path`: مسیر برنامه اسپاتیفای. درصورتی که برنامه رو تو یه مسیر دیگه نصب کردید باید اینو تغییر بدید.   

درصورتی که علاقه دارید بدونید تمام پارامتر ها چه فایده ای دارند، دستور زیر رو بزنید.
```shell script
spicetify --help config
```

## فایل color.ini
خب با یک شخصی سازی خیلی ساده شروع میکنیم.   
اول از همه دستور `spicetify path color` رو بزنید تا آدرس فایل رنگی که در حال حاضر اعمال شده رو بهتون بگه.
سپس اون فایل رو باز کنید. اگر با این آموزش پیش رفته باشید در ابتدای کار که تم پیش‌فرض هستش، دوتا کانفیگ رنگی مختلف در فایل مشاهده میکنید.
اولی `Base` و دومی `Dark` هستش.

خب برای اولین تغییر بیاین اسپاتیفای رو Dark کنیم. به فایل `config.ini` برید و فیلد `color_scheme` به شکل زیر عوض کنید:

```shell script
color_scheme = Dark
```

و سپس دستور زیر را اجرا کنید:
```shell script
spicetify apply
```

{{< single-image "/images/customize-spotify-with-spicetify/5.png" >}}

<br>

حالا بیاین یه خورده رنگ کانفیگ Dark رو عوض کنیم. برای مثال من دوتا فیلد رو به رنگ `212121` تغییر میدم
```shell script
main_bg = 212121
sidebar_and_player_bg = 212121
```

و سپس برای اعمال تغییرات، دستور زیر را اجرا میکنم:
```shell script
spicetify apply
```

{{< single-image "/images/customize-spotify-with-spicetify/6.png" >}}

## فایل user.css

از اسم فایل هم معلوم هست که قراره یه خورده کار با css داشته باشیم😍😋   
دستور `spicetify path css` رو بزنید تا آدرس فایل css که در حال حاضر اعمال شده رو بهتون بگه.      
اول از هم اینو بگم که برنامه Spotify کاملا با HTML CSS JS هستش و با استفاده از Chromium Embedded Framework اجرا میشه.
 پس این یعنی ما میتونیم با ابزار Spicetify در این فایل ها تغییراتی را انجام بدهیم.
 
 اگر یادتون باشه
در آخر دستور فعال سازی `enable-devtool` داشتیم که باعث میشه ابزار Developer برنامه قابل مشاهده باشه.

{{< gallery "/images/customize-spotify-with-spicetify/7.png" "/images/customize-spotify-with-spicetify/8.png" >}}

قبل از همه چیز باید class بخشی رو که میخوایم پیدا کنیم. میتونید سرچ کنید و دنبال بگردید یا گاها اطراف اون Element ای رو که میخواین راستی کلیک کنید و Inspect Element رو بزنید.   
برای مثال من اینجا HOME رو پیدا کردم و میخوام یه تغییر کوچیکی بهش بدم.

{{< single-image "/images/customize-spotify-with-spicetify/9.png" >}}

فایل `user.css` رو باز میکنم و `Header__title-text-inner` رو سرچ میکنم. از اونجایی که این فایل برای تم پیش‌فرض هستش، یک سری تغییرات و کلاس هارو از قبل
داخل خودش داره و این ممکنه توی هر تم متفاوت باشه.   
اینجا فقط برای دمو، Padding و border-radius رو تغییر میدم. بعد از تغییرات دستور زیر را اجرا میکنم:
```shell script
spicetify apply
``` 

{{< single-image "/images/customize-spotify-with-spicetify/10.png" >}}

# نصب تم

خب حالا که با پایه کار این برنامه رو یاد گرفتید، نوبت نصب تم هایی هست که بقیه درست کردند.   
در ابتدا باید به 
 [صفحه ریپازتوری تم ها](https://github.com/morpheusthewhite/spicetify-themes)
 برید و تمام تم هارو دانلود کنید.

{{< single-image "/images/customize-spotify-with-spicetify/11.png" >}}

پس از دانلود تمام تم ها را استخراج کنید و به پوشه Theme برنامه انتقال دهید. (البته لازم نیست همه رو انتقال بدید. اگر فقط یک تم رو نیاز دارید، میتوانید فقط همونو انتقال بدید.)

**نکته**: اگر نمیدونید آدرس پوشه رو نمیدونید دستور `spicetify path` رو بزنید. بخش اول آن نشان دهنده آدرس پوشه تم هست.
{{< single-image "/images/customize-spotify-with-spicetify/12.png" >}}

اول از همه بگم که میتونید پوشه هر تم رو باز کنید و عکس پیش نمایش هر تم رو ببینید.
دقت داشته باشید که اسم هر تم، در واقع همان اسم پوشه است.
برای نصب باید به صورت زیر عمل کنیم:
```shell script
< spicetify config current_theme THEME_NAME >
```
برای نمونه در این مرحله تم `CherryBlossom` رو نصب میکنیم:
```shell script
spicetify config current_theme CherryBlossom
```
و برای اعمال تغییرات، دستور زیر را میزنیم:
```shell script
spicetify apply
```
{{< single-image "/images/customize-spotify-with-spicetify/13.png" >}}

<br>

اگر یادتون باشه گفتم هر تم ممکن هست چند تا کانفیگ داشته باشه. خب این تم هم یکی از همون تم ها هستش! بذارید فایل `color.ini` رو باز کنیم تا متوجه شوید.
{{< single-image "/images/customize-spotify-with-spicetify/14.png" >}}

همون طور که در بالاتر هم گفتم اگر فیلد `color_scheme` رو معلوم نکنیم، اولین کانفیگ انتخاب می شود. برای این که در اینجا کانفیگ `Coral` رو انتخاب کنیم، دو راه داریم.
یا فایل `config.ini` رو ویرایش کنیم و آن را تغییر بدیم یا دستور زیر را بزنیم:
```shell script
spicetify config color_scheme Coral
```
و سپس برای اعمال تغییرات، دستور زیر را میزنیم:
```shell script
spicetify apply
```
{{< single-image "/images/customize-spotify-with-spicetify/15.png" >}}

# نصب افزونه
خب تا اینجا با نحوه ادیت کردن فایل های css و color و نصب تم آشنا شدید. حالا وقتش هست بریم سراغ JS و افزونه 🙄   
خود این برنامه شامل چند تا افزونه میشه که توی هر فایل یک توضیحات خلاصه و مشخصات برنامه نویس هستش. اگر شما هم دوست داشتید، میتونید برای اسپاتیفای افزونه درست کنید و به من بگید تا
به این متن اضافه ش کنم😁

اسم تمام افزونه ها در پوشه `spicetify-cli\Extensions` قابل مشاهده هستش. نحوه افزودن افزونه ها مشابه هم هستش.

## افزونه fullAppDisplay.js

بعد از فعال کردن این افزونه، برای شما یک آپشن اضافه میشود که میتوانید آهنگ رو در حالت Full Screen مشاهده کنید. ابتدا با دستور زیر افزونه را فعال کنید:
```shell script
spicetify config extensions fullAppDisplay.js
spicetify apply
```
برای رفتن به حالت Full Screen بر روی آیکون اشاره شده بزنید.

{{< single-image "/images/customize-spotify-with-spicetify/17.png" >}}


در این مرحله حالت زیر رو مشاهده میکنید.

{{< single-image "/images/customize-spotify-with-spicetify/18.png" >}}

البته میتونید با راست کلیک در صفحه آپشن های دیگه رو هم ببینید و حالتش رو تغییر بدید.

{{< single-image "/images/customize-spotify-with-spicetify/19.png" >}}

و در نهایت با دوبار کلیک کردن روی صفحه از این حالت خارج بشید.

# دستورات مهم
بازگرداندن به حالت اولیه:
```shell script
spicetify restore
```

اعمال تغییرات انجام شده:
```shell script
spicetify apply
```

مسیر فایل های مهم:
```shell script
spicetify path
```

تمام رنگ های مورد استفاده در تم فعلی:
```shell script
spicetify color
```
{{< single-image "/images/customize-spotify-with-spicetify/20.png" >}}
</div>
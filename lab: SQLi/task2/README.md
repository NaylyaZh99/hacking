## Lab: Lab: SQL injection UNION attack, determining the number of columns returned by the query
1) Переходим на сайт задания и заходим в раздел Gifts
2) Изменяем запрос на category=Gifts'+UNION+SELECT+NULL--
3) Увидили ошибку, значит добавим еще NULL в запрос. Добавляем пока не выйдет нужный результат.
4) Подходит category=Gifts'+UNION+SELECT+NULL,NULL,NULL-- 

Готово!

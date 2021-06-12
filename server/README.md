# Пошаговое создание проекта
https://www.youtube.com/watch?v=H2GCkRF9eko&t=2085s

## Server

1. Инициализируем проект
npm init
   
2. Установим зависимости
npm install express pg pg-hstore cors dotenv sequelize
npm install -D nodemon   
   
3. В файле .env установим значения переменных для подключения к БД

4. В файле db.js объявим объект класса Sequelize (модуль sequelize) и через него подключимся к БД

5. В файле models.js объявим объект класса DataTypes (модуль sequelize) и через него опишем столбцы БД.
Установим связи между таблицами. Через module.exports экспортируем таблицы, 
чтобы работать с ними в других файлах.
   
6. Подключим модули в index.js. С помощью метода sequelize.authenticate() подключимся к БД

7. Создаем директорию routes для обеспечения маршрутизации в приложении
Создаем файлы в соответствии с таблицами из БД, часть логики перенесем в controllers
Для объединения всех маршрутов создаем routes/index.js, в который импортируем все созданные роутеры
routes/index.js импортируем в основной файл  
   
8. В папке error создадим класс для обработки ошибок
   
9. В папке middleware создадим связующие обработчики

10. Для работы с файлами 
Установим пакет npm install express-fileupload
Используем в deviceController.js (строка 10 - req.files)
Установим пакет npm install uuid чтобы формировать уникальное имя для файла
Используем в deviceController.js (строка 11 - uuid.v4())
    
11. Создадим папку static. 
Перемещаем в нее все файлы, которые получаем с клиента (deviceController.js - строка 12 - img.mv)
Отдаем эти файлы через статику (deviceController.js - строка 13 - await Device.create)

12. Работа с пользователем
Установим пакет npm install jsonwebtoken для генерации токена
Установим пакет npm install bcrypt для хеширования паролей
Применяем в userController.js
Токен пользователя можно декодировать на сайте https://jwt.io/    
В authMiddleware.js проверяем токен на валидность
В checkRoleMiddleware.js проверяем роль пользователя

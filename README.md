## Лабораторная работа №31-32. Введение в SQLite и Entity Framework Core
### Краткое описание работы
Работа с Sql. Знакосмтво с QLite. Подключение Entity Framework Core к проекту ASP.NET Core
### Структура проекта 
- [img](img)
- [TaskDb](TaskDb)
- [README](README.md)
---
### Таблица  LINQ vs SQL
|Концепция|Хранение в памяти |EF Core + SQLite|
|---|---|---|
|Хранение данных| static List<T> в RAM| Файл .db на диске|
|После перезапуска |Данные пропадают| Данные сохраняются|
|Поиск по условию| LINQ to Objects| LINQ to Entities → SQL|
|Создание структуры| Не нужно |Миграции (dotnet ef)|
|Начальные данные| Хардкод в коде| HasData() в миграции|
|Получение данных| list.FirstOrDefault(...) |await db.Table.FindAsync(id)|
|Добавление |list.Add(item)| db.Table.Add(item) + SaveChangesAsync()|
|Удаление| list.Remove(item)|db.Table.Remove(item) + SaveChangesAsync()|
|Масштабируемость |Ограничена RAM |Гигабайты данных|
|Транзакции| Нет|Встроены в EF Core|
---
### Вывод 
В ходе этой работы я научился работать с Swagger и смотреть, какие SQL-запросы генерирует Entity Framework. Я выполнил разные запросы к API: получал все задачи, фильтровал по статусу и приоритету. 
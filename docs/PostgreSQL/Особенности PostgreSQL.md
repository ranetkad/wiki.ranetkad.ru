
База данных относится к типу объектно-реляционных и часто используется как основная в проектах самых разных масштабов. Коротко работу с данными можно описать так: данные записываются в таблицы, индексируются для быстрого поиска и обрастают сложными зависимостями. Индексы помогают разметить данные в логике оглавления книги, чтобы не тратить время на полный просмотр базы данных. Зависимости нужны для реализации гибкой системы триггеров записи и чтения данных. Например, сотрудник банка с их помощью может выгрузить информацию по всем клиентам ипотекой, оформленной в понедельник.


###### Асинхронная репликация

PostgreSQL сначала применит изменения на master-ноде, а потом отправит записи из WAL на реплики. Преимущество такого способа — быстрое подтверждение транзакции, поскольку не нужно ждать, пока все реплики применят изменения.


##### Синхронная репликация

Изменения сначала записываются в WAL хотя бы одной реплики и только после этого фиксируются на основном сервере. Преимущество — более надежный способ, при котором сложнее потерять данные.


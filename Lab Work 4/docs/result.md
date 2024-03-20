# Лабораторная работа №4

Тема: Проектирование REST API

Цель работы: Получить опыт проектирования программного интерфейса


## Документация по API

### Контроллер Management

![Alt text](../pictures/management.png)

Контроллер включает в себя методы для реализации CRUD-операций по тарифам, которые включают в себя id, product, period и price.

- HttpGet: на вход не имеет параметров, на выход отдаёт список tariffs, который включает в себя объекты из четырёх полей, указанных ранее.
- HttpPost: на вход получает параметры Product, Period, Price. На выход отдаёт полность заполненный созданный объект с теми же параметрами и дополнительным Id
- HttpPut: На вход получает все 4 поля тарифа, ищет тариф в системе с таким же Id, после чего заменяет все поля найденного объекта на параметры из запроса.
- HttpDelete: Получает Id объекта, удаляет его из системы и на выход отдаёт все параметры удалённого объекта.

### Контроллер Refund

![Alt text](../pictures/refund.png)

Контроллер включает в себя 2 метода на получение списка возвратов денежных средств и на создание объекта возврата

- HttpGet: не имеет параметров на вход, на выходе даёт список их обхектов с полями Id и Price
- HttpPost: Получает на вход UserId и SumOfMoney, создаёт обхект в системе и вовзвращает созданный объект в качестве ответа.

### Контроллер Statistics

У контроллера есть 2 метода: Get и Post на получение списка всех сессий аренды и добавление новой сессии.

![Alt text](../pictures/Statistics1.png)
![Alt text](../pictures/Statistics2.png)

- HttpGet: Не имеет параметров на вход, на выход отдаёт список объектов с параметрами UserId, Price, StartTime, EndTime
- HttpPost: На вход получает все 4 поля, создаёт объект в системе и возвращает этот объект в ответе.

### Контроллер Payment

У контроллера есть 2 метода: Запуск процесса сессии аренды и получение списка таких запусков. На скрине можно заметить третий метод, однако он не описан, поэтому в отчёте не будет учитываться.

![Alt text](../pictures/Payment.png)

- HttpGet: Не имеет входных параметров, на выходе отдаёт список из объектов сессий, включающих Id, UserId, Period, Price, Status
- HttpPost: На вход получает UserId, Period, Price. На выход отдаёт созданный объект запущенной сессии.


## Тестирование API

### Management.Get

![Alt text](../pictures/manag_get_body.png)
![Alt text](../pictures/manag_get_head.png)
![alt text](../pictures/manag_get_test.png)

### Management.Post

![Alt text](../pictures/manag_post.png)
![alt text](../pictures/manag_post_test.png)

### Management.Put

![Alt text](../pictures/manag_put.png)
![alt text](../pictures/manag_put_test.png)

### Management.Delete

![Alt text](../pictures/manag_delete.png)
![alt text](../pictures/manag_delete_test.png)


### Refund.Post

![Alt text](../pictures/refund_post.png)
![alt text](../pictures/ref_post_test.png)

### Refund.Get

![Alt text](../pictures/refund_get.png)
![alt text](../pictures/refund_get_test.png)

### Statistics.Post

![Alt text](../pictures/stat_post.png)
![alt text](../pictures/stat_post_test.png)

### Statistics.Get

![Alt text](../pictures/stat_get.png)
![alt text](../pictures/stat_get_test.png)

### Payment.Post

![Alt text](../pictures/pay_post.png)
![alt text](../pictures/pay_post_test.png)

### Payment.Get

![Alt text](../pictures/pay_get.png)
![alt text](../pictures/pay_get_test.png)
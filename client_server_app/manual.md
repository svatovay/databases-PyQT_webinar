# Консольный мессенджер #

## Общее описание модулей: ##
1. common - пакет с утилитами приёма передачи данных и глобальными переменными, используемыми в проекте.
2. logs - пакет с конфигурацией логирования и сами логи работы.
3. unit_tests - автотесты для проверки работоспособности функций проекта
4. client.py - основной клиентский модуль.
5. decos.py - функция декоратор для логирования вызовов функций.
6. errors.py - описание классов исключений, используемые в проекте.
7. launcher.py - вспомогательная утилита для одновременного запуска сервера и нескольких клиентов.
8. server.py - основной серверный модуль.

## Клиентский модуль - client.py ##
Модуль поддерживает отправку сообщений адресатам, одновременно с этим приём новых сообщений.
Поддерживаются опции командной строки:
1. Адрес сервера. Позволяет указать адрес сервера для подключения. По умолчанию **Localhost**.
2. Порт сервера. Позволяет указать порт, по которому будет производиться подключение. По умолчанию **7777**
3. **-n** или **--name**. Имя пользователя в системе. По умолчанию не задан. Если не указать данный параметр, программа
    при запуске запросит имя пользователя для авторизации в системе.

После запуска приложения будет произведена попытка установить соединение с сервером.
В случае удачи будет выведена справка по внутренним командам приложения:
1. **message**. Отправить сообщение. После ввода команды приложение запросит имя получателя и само сообщение.
2. **help**. Повторно выводит справку о командах приложения.
3. **exit**. Завершает работы приложения.

## Серверный модуль - server.py ##
Модуль обеспечивает пересылку сообщений поступаемых от клиентов адресатам. Сообщения обрабатываются на сервере
и отправляются только адресату.
Поддерживаются опции командной строки:
1. Номер порта. Номер порта на котором сервер будет принимать входящие подключения. По умолчанию **7777**
2. Адрес. Адрес с которого сервер будет принимать подключения. По умолчанию слушаются **все адреса**.
После запуска сервера никакие дополнительные действия не требуются.
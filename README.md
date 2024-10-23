Сервис уведомлений с использованием Telegram API
==============

Для реализации используется библиотека [TDlib](https://core.telegram.org/tdlib) - для костомизации клиента Telegram.

Программа создана для автоматического мониторинга и управления ссылками, содержащимися в постах и комментариях на Telegram-канале.
Основная цель — отслеживание наличия ссылок в постах и комментированиях, а также синхронизация данных с базой данных (БД).


*Функционал:*

1. ***Периодический парсинг постов и комментариев.*** Программа через регулярные интервалы времени получает историю сообщений с Telegram-канала и проверяет их на наличие ссылок. В случае изменения постов (например, удаления ссылок), база данных обновляется соответственно.

2. ***Обработка сообщений.*** Программа обрабатывает каждое сообщение в канале, а также комментарии под ним. Из каждого поста извлекаются все ссылки определенного типа, которые затем сохраняются в базе данных.

3. ***Работа с изменениями.*** Если в Telegram-канале изменяется сообщение (например, удаляется или добавляется новая ссылка), программа обновляет базу данных, чтобы поддерживать актуальность информации.

4. ***Уведомления.*** В случае, если какой-либо пост или комментарий не содержит ссылок, Telegram-бот отправляет уведомление в специальный чат, указывая на проблему. Это помогает оперативно реагировать на отсутствие ссылок, которые могут быть важны для отслеживания задач или других процессов.
При возникновении ошибок, таких как сбои при получении истории чата, программа записывает предупреждения в журнал.



*Программа была создана с целью контроля заведения задач на приходяшие баги. Баги описываюся в сообщениях чата телеграм - ссылка на заведеную задачу в трекере задач находится в комментариях к сообщению.*

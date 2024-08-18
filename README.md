# reminger-tg-bot# PHP_About



**П.2 СОДЕРЖИМОЕ CRONTAB:**
- Ввод комманды: crontab -l
- Выводит результат: no crontab for root



**П.3 SYSTEMCTL**

В Systemctl очень много процессов, легко запутаться с непривычки.
В Crontab намного проще найти интересующий процесс.

- sudo supervisorctl reread - чтение изменений в файлах
- sudo supervisorctl update - перезапуск службы
- sudo supervisorctl status - проверка работоспособности


**П.4**

Чтобы запустить демон с помощью systemd, нужно создать файл службы (service file). Вот пример файла worker.service:


[Unit]
Description=My Worker Service
After=network.target
[Service]
ExecStart=/usr/bin/php /path/to/your/script.php
Restart=always
User=your_username
Group=your_groupname
[Install]
WantedBy=multi-user.target


**Description**: Описание службы.
**After**: Указывает, что служба должна запускаться после других служб.
**ExecStart**: Команда для запуска демона.
**Restart**: Опция для перезапуска службы в случае сбоя.
**User и Group**: Пользователь и группа, от имени которых будет работать служба.
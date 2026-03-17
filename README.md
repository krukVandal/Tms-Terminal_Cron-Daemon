# Задача: Запуск и логирование демона
# Роман Салий

1. Установил `node`

<img src="https://github.com/krukVandal/Tms-Terminal_Cron-Daemon/blob/main/Daemon/1.png?raw=true" />

2. Создал файл в директории `/home/vandal/temp/app.js` и добавил в него приведенный код

<img src="https://github.com/krukVandal/Tms-Terminal_Cron-Daemon/blob/main/Daemon/2.png?raw=true" />

3. Создал сервисный файл в директории `/etc/systemd/system/nodeapp.service` и добавил в него начальные данные

<img src="https://github.com/krukVandal/Tms-Terminal_Cron-Daemon/blob/main/Daemon/3.png?raw=true" />

4. Создал лог файлы `/var/log/nodeapp/info.log, error.log` и выдал доступ для `syslog`

<img src="https://github.com/krukVandal/Tms-Terminal_Cron-Daemon/blob/main/Daemon/4.png?raw=true" />

5. Запустил демона и убедился в его состоянии `running`

<img src="https://github.com/krukVandal/Tms-Terminal_Cron-Daemon/blob/main/Daemon/5.png?raw=true" />

6. Курлыкнул службу через `loopback получил 200 OK` и убил для демонстрации автозапуска

<img src="https://github.com/krukVandal/Tms-Terminal_Cron-Daemon/blob/main/Daemon/6.png?raw=true" />

7. Создал файл `/etc/rsyslog.d/100-nodeapp.conf` для перехвата логов через `syslog`

<img src="https://github.com/krukVandal/Tms-Terminal_Cron-Daemon/blob/main/Daemon/7.png?raw=true" />

8. Создал файл `/etc/logrotate.d/nodeapp` для адекватного хранения логов чтоб исключить возможность бесконечно плодиться

<img src="https://github.com/krukVandal/Tms-Terminal_Cron-Daemon/blob/main/Daemon/8.png?raw=true" />

9. Изменил сервисный файл для использования `syslog` и добавил `logger`

<img src="https://github.com/krukVandal/Tms-Terminal_Cron-Daemon/blob/main/Daemon/9.png?raw=true" />

10. Первый лог `123` отправил ручками напрямую в logger, второй лог получил при убийстве службы

<img src="https://github.com/krukVandal/Tms-Terminal_Cron-Daemon/blob/main/Daemon/10.png?raw=true" />



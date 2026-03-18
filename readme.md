Тестовый проект по настройке HAProxy

1. Запуск проекта:
```bash
docker compose up -d
```

1.а. Просмотр логов:
```bash
docker compose logs -f frontend01
docker compose logs -f frontend02
docker compose logs -f haproxy01
docker compose logs -f haproxy02
docker compose logs -f keepalived01
docker compose logs -f keepalived02
```

2. Проверка работоспособности:

```bash
# HAProxy (запросы через балансирощик нагрузки)
http://10.10.40.20 # запрос к HAProxy 01
http://10.10.40.21 # запрос к HAProxy 02

http://10.10.40.20:7000/stats # dashboard HAProxy 01
http://10.10.40.21:7000/stats # dashboard HAProxy 02

# Nginx (запросы напрямую к веб серверу)
http://10.10.40.30 # запрос к nginx fe01
http://10.10.40.31 # запрос к nginx fe02

http://10.10.40.40 # запрос к keepalived который переадресует на 
```
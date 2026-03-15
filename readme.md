Тестовый проект по настройке HAProxy

1. Запуск проекта:
```bash
docker compose up -d
```

1.а. Просмотр логов:
```bash
docker compose logs -f f01 
docker compose logs -f f02 
docker compose logs -f h01 
docker compose logs -f h02 
```

2. Проверка работоспособности:

```bash
# HAProxy (запросы через балансирощик нагрузки)
http://localhost # запрос к HAProxy 01
http://localhost:81 # запрос к HAProxy 02

http://localhost:7000/stats # dashboard HAProxy 01
http://localhost:7001/stats # dashboard HAProxy 02

# Nginx (запросы напрямую к веб серверу)
http://localhost:82 # запрос к nginx fe01
http://localhost:83 # запрос к nginx fe02
```
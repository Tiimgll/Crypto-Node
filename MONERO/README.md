# Настройка Docker и запуск сервисов Monero

## Настройка и запуск сервисов Monero

### Создание структуры директорий
Создайте необходимые директории для данных Monero:
``` 
mkdir -p /rpool/monero/mainnet/bitmonero
mkdir -p /rpool/monero/mainnet/wallet
mkdir -p /rpool/monero/mainnet/config
``` 

### Деплой стеков сервисов Monero
Запустите стек сервисов для Monero:
``` 
docker-compose up -d --build
``` 

### Проверка запущенных сервисов

Проверка состояния сервисов Monero:
``` 
docker ps -a
``` 

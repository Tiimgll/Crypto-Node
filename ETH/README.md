# Настройка Docker, Docker Swarm и запуск сервисов Ethereum

## Настройка и запуск сервисов Ethereum

### Создание структуры директорий
Создайте необходимые директории для данных Ethereum:
``` 
mkdir -p /rpool/eth/mainnet/data/ethereum
mkdir -p /rpool/eth/mainnet/data/lighthouse
openssl rand -hex 32 > /rpool/eth/mainnet/jwtsecret
``` 

### Деплой стеков сервисов Ethereum
Запустите стек сервисов для Ethereum:
``` 
docker-compose up -d --build
``` 

### Проверка запущенных сервисов

Проверка состояния сервисов Ethereum:
``` 
docker ps -a
``` 

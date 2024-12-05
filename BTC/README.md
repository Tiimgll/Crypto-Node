# Настройка Docker, Docker Swarm и запуск сервисов Bitcoin

## Настройка и запуск сервисов Bitcoin

### Создание структуры директорий
Создайте необходимые директории для данных Bitcoin:
``` 
mkdir -p /rpool/bitcoin/mainnet/bitcoind-data
mkdir -p /rpool/bitcoin/electrumx
``` 

### Деплой стеков сервисов Bitcoin
Запустите стек сервисов для Bitcoin:
``` 
docker-compose up -d --build
``` 

### Проверка запущенных сервисов

Проверка состояния сервисов Bitcoin:
``` 
docker ps -a
``` 

### Добавление `txindex` в bitcoin.conf
Откройте файл конфигурации для редактирования:
``` 
nano /rpool/bitcoin/mainnet/bitcoind-data/bitcoin.conf
``` 

Добавьте следующую строку:
``` 
txindex=1
``` 

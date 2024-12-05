# Настройка Docker, Docker Swarm и запуск сервисов Tron

## Настройка и запуск сервисов Tron

### Создание структуры директорий
Создайте необходимые директории для данных Tron:
``` 
mkdir -p /rpool/tron/mainnet/output-directory
mkdir -p /rpool/tron/mainnet/logs
mkdir -p /rpool/tron/mainnet/config/
``` 

Скопируйте файл конфигурации:
``` 
cp tron/main_net_config.conf /rpool/tron/mainnet/config/main_net_config.conf
``` 

### Установка Main Net Database Snapshots
TRON предоставляет официальные снимки базы данных для быстрой настройки узлов. Это архивы данных сети TRON, позволяющие ускорить синхронизацию узлов.

#### Скачивание снимков базы данных
Выберите подходящий снимок из списка (Лучше проверить более актуальные версии):

Например:
Полноценный Fullnode:
``` 
wget -b http://34.143.247.77/backup20241120/FullNode_output-directory.tgz
``` 

Легковесный Lite Fullnode:
``` 
wget -b http://34.143.247.77/backup20241120/LiteFullNode_output-directory.tgz 
``` 

#### Распаковка и копирование данных
Распакуйте архив:
``` 
tar -xvzf название-архива.tar.gz
``` 

Скопируйте содержимое папки `output-directory` в директорию `/rpool/tron/mainnet/output-directory`:
``` 
cp -r output-directory/* /rpool/tron/mainnet/output-directory/
``` 

### Деплой стеков сервисов Tron
Запустите стек сервисов для Tron:
``` 
docker-compose up -d --build
``` 

### Проверка запущенных сервисов

Проверка состояния сервисов Tron:
``` 
docker ps -a
``` 

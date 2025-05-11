# SnakeGuardX
Вы нашли самый простой способ установить AmneziaWG и управлять им на любом хосте Linux.

Основан на [данном](https://github.com/w0rng/amnezia-wg-easy) проекте <br>
Скришоты панели в директории проекта

## Функционал

* Интуитивно понятный интерфейс
* Возможность создавать, редактировать, удалять, а также отключать и включать клиентов
* Автоматическое создание конфигурационных файлов с возможностью их загрузки через веб-интерфейс
* Генерация QR-кода прямо в панели для удобного подключения
* Telegram бот для управления пользователями

## Зависимости

* Ubuntu 24.04 или Debian 12
* Установленный Docker

## Установка

### 1. Установка Docker

Для установки используйте данный код:
```bash
curl -sSL https://get.docker.com | sh
```

### 2. Установка SnakeGuard

1. Скопируйте проект на ваш сервер:
```bash
git clone https://github.com/JoriandRooil/SnakeGuardX
```

2. Перейдите в директорию проекта:
```bash
cd SnakeGuardX
```

3. Измените переменные в файле .env
```
WG_HOST=127.0.0.1 # Укажите IP адрес сервер
PASSWORD_HASH='' # Захешированный пароль
PORT=35955 # Порт панели
WG_PORT=12593 # Порт AmneziaWG
WG_DEFAULT_DNS=94.140.14.14 # DNS сервер
```
> Параметры `WG_HOST` и `PASSWORD_HASH` обязательны к изменению
> Параметры `PORT` и `WG_PORT` рекомендуется изменить

4. Запустите сборку проекта
```bash
docker compose up -d
```

## Обновление проекта
```bash
cd SnakeGuardX
docker compose down
docker pull joriandro/snakex:latest
docker compose up -d
```


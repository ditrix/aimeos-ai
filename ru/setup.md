# Установка

## Требования

- Linux/Unix, WAMP/XAMP или MacOS
- PHP >= 7.2
- MySQL >= 5.7.8, MariaDB >= 10.2.2
- Веб-сервер (Apache, Nginx или встроенный PHP сервер для тестирования)

## Поддерживаемые версии

Список поддерживаемых версий Laravel для пакета Aimeos можно найти в [репозитории](https://github.com/aimeos/aimeos-laravel#supported-versions).

## Использование Composer

**Пакет Laravel**: может быть интегрирован в собственное приложение Laravel. Инструкция по установке:

- <https://github.com/aimeos/aimeos-laravel#installation>

**Автономный магазин**: можно установить через Composer за пять минут, чтобы получить готовую систему магазина:

- <https://github.com/aimeos/aimeos#installation>

# Обновление

## Руководство

Процесс обновления зависит от версии, на которую вы хотите перейти.

Существуют три типа релизов:
- **Минорные релизы** (исправления ошибок)
- **Стабильные релизы** (новые функции)
- **Мажорные релизы** (разрушительные изменения)

### Рекомендации
1. Обновляйтесь до последней минорной версии, например, с 2022.04.1 до 2022.04.2.
2. Обновляйтесь до последней стабильной версии, например, с 2022.07 до 2022.10 для получения долгосрочной поддержки.
3. Переходите на новую мажорную версию, например, с 2021.10 до 2022.10, если закончилась поддержка текущей версии.

Для получения **расширенной долгосрочной поддержки** (до 5 лет) можно приобрести услугу от компании Aimeos. Подробнее на странице [дорожной карты](https://aimeos.org/roadmap).

### Процесс

Для обновления приложения Laravel выполните следующие шаги:
- Следуйте [руководству по установке](https://github.com/aimeos/aimeos-laravel#installation).
- Скопируйте `vendor/aimeos/aimeos-laravel/src/config/shop.php` в `config/shop.php`.
- Настройте файл `shop.php` под свои нужды.
- Скопируйте папку `./vendor/aimeos/aimeos-laravel/src/views/` в `./resources/views/vendor/shop/`.
- Обновите базу данных и очистите кэш:
  ```bash
  php ./artisan aimeos:setup
  php ./artisan route:clear
  php ./artisan view:clear
  php ./artisan aimeos:clear
  ```

### Обновление до 2021.07+

С версии 2021.07 установка через Composer требует версии Composer 2.1+. Официальные расширения Aimeos с префиксом `ai-` должны быть удалены из папки `./ext/`:
```bash
rm -rf ./ext/ai-*
```

Файлы теперь сохраняются в новых подкаталогах, например:
- `./public/aimeos/1.d/files/`
- `./public/aimeos/2.d/previews/`

Старые пути можно перенести:
```bash
mv ./public/files/ ./public/aimeos/files
mv ./public/previews/ ./public/aimeos/previews
```

# Задачи Cron

Для выполнения задач, таких как отправка писем, требуется регулярный запуск команд artisan:
```bash
php artisan aimeos:jobs "<jobs>" "<sites>"
```

### Ежеминутно
```bash
* * * * * php /path/to/artisan aimeos:jobs "order/email/delivery order/email/payment"
```

### Ежечасно
```bash
30 * * * * php /path/to/artisan aimeos:jobs "order/cleanup/unfinished"
```

### Ежедневно
```bash
0 1 * * * php /path/to/artisan aimeos:jobs "admin/cache order/cleanup/unpaid"
```

# Политика безопасности контента (CSP)

С версии 2021.07 Aimeos использует строгую политику CSP для предотвращения XSS-атак. Чтобы настроить CSP, скопируйте `base.blade.php` из `./vendor/aimeos/aimeos-laravel/src/views/` в `./resources/views/vendor/shop/` и измените настройки. Например:
```html
default-src 'self' https://cdn.jsdelivr.net https://youtube.com;
```
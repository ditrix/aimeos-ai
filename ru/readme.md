Aimeos Laravel — это расширение для фреймворка веб-приложений Laravel, основанное на Composer. Оно интегрирует основную библиотеку компонентов интернет-магазина в любое приложение на базе Laravel и позволяет размещать компоненты на любых страницах с использованием шаблонов Blade. Для быстрого старта уже включены стандартные шаблоны.

Если вам нравится Aimeos: [Поставьте звезду](https://github.com/aimeos/aimeos-laravel)

Пакет Aimeos также включает адаптеры для базовых компонентов, используемых в любых приложениях Laravel, таких как логирование, конфигурация или генерация URL. Таким образом, он нативно интегрируется в любое приложение, основанное на Laravel, и использует все его возможности.

1. [Установить Aimeos](setup.md)  
2. [Прочитать руководство](../manual/index.md)  
3. [Создать расширение](../developer/extensions.md)  
4. [Настроить Aimeos](customize.md)  
5. [Адаптировать интерфейс](#html-frontend)  
6. [Расширить Aimeos](extend.md)  
7. [Импортировать данные](#import-data)  
8. [Оптимизировать Aimeos](optimize.md)  

# HTML-интерфейс

* [Переопределение существующих шаблонов](../frontend/html/overwrite-templates.md)  
* [Синтаксис шаблонов и вспомогательные функции представления](../infrastructure/view.md)  
* [Использование шаблонов Blade](customize.md#blade-templates)  

* [Создание новых подпунктов для существующих компонентов](../frontend/html/create-subparts.md)  
* [Реализация новых компонентов магазина](../frontend/html/implement-components.md)  
* [Расширение существующих компонентов](../frontend/html/extend-components.md)  

## Каталог

* [Настройка поведения каталога и его шаблонов](../frontend/html/catalog-components.md)  

## Корзина

* [Настройка поведения корзины и её шаблонов](../frontend/html/basket-components.md)  
* [Реализация плагинов корзины](../providers/basket-plugins.md)  

## Оформление заказа

* [Настройка поведения и шаблонов оформления заказа](../frontend/html/checkout-components.md)  
* [Настройка стран, регионов и штатов](customize.md#countries-regions-and-states)  
* [Изменение вариантов доставки и оплаты](../manual/services.md)  
* [Создание собственных провайдеров услуг доставки и оплаты](../providers/service/index.md)  

## Личный кабинет

* [Настройка поведения профиля и его шаблонов](../frontend/html/account-components.md)  

# Импорт данных

* [Импорт продуктов из CSV](../cronjobs/product-csv-import.md)  
* [Импорт категорий из CSV](../cronjobs/catalog-csv-import.md)  
* [Реализация периодических задач](../cronjobs/create-job-controller.md)  
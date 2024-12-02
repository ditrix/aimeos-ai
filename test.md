# **Настроить**

## **Изменить конфигурацию[\#](https://aimeos-org.translate.goog/docs/latest/laravel/customize/?_x_tr_sl=en&_x_tr_tl=ru&_x_tr_hl=ru&_x_tr_pto=wapp#change-configuration)**

Основная библиотека содержит множество параметров конфигурации, описанных в разделе «Конфигурация», которые можно изменить в `config/shop.php`файле. В документации они отображаются следующим образом:

client/html/catalog/filter/button \= 1

Laravel использует обычные массивы PHP для конфигурации. Как правило, заменяйте каждую часть, разделенную слешем (/), на `'..' => ['...'],`:

'client' \=\> \[  
    'html' \=\> \[  
        'catalog' \=\> \[  
            'filter' \=\> \[  
                'button' \=\> 1,  
            \],  
        \],  
    \],  
\],

### Списки значений[\#](https://aimeos-org.translate.goog/docs/latest/laravel/customize/?_x_tr_sl=en&_x_tr_tl=ru&_x_tr_hl=ru&_x_tr_pto=wapp#value-lists)

То же самое работает и с массивами значений:


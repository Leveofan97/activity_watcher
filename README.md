# Activity Checker
Этот проект - пример использования node модуля основанного на логике C++ кода.
По сути это дополнение написанное С++ для использования в node js.

У браузера, как и у electron приложения нет доступа к api на уровне операционной системы. 
В частности нет доступа к отслеживанию движений мыши и нажатий клавиатуры вне окна браузера/electron приложения.

Используя node модуль реализованный на С++ с доступом к win API у нас появляется отслеживать изменение активности пользователя.
В частности под признаком активности подразумевается наличие движений мыши или нажатий клавиш.

Кроме этого в модуле реализована возможность настройки времени бездействия и времени периода проверки.

## Установка

Данная версия была собрана на [Node.js](https://nodejs.org/) v18.0.0 .

Установка зависимостей.

```sh
npm install

npm install node-addon-api
```

## Сборка модуля локально (из файлов проекта с помощью node-gyp)
```sh
npm node-gyp configure

npm node-gyp build
```

Обратите внимание на файл binding.gyp в котором прописана конфигурация (пути) собираемых файлов.

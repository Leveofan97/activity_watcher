<details>

<summary>RU</summary>
# Activity Watcher (Only Windows)
Этот проект - пример использования node модуля основанного на логике C++ кода.
По сути это дополнение написанное С++ для использования в node js.

У браузера, как и у electron приложения нет доступа к api на уровне операционной системы. 
В частности нет доступа к отслеживанию движений мыши и нажатий клавиатуры вне окна браузера/electron приложения.

Используя node модуль реализованный на С++ с доступом к win API у нас появляется возможность отслеживать изменение активности пользователя.
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

## Установка пакета из репозитория NPM

[activity_watcher](https://www.npmjs.com/package/activity_watcher)

```sh
npm i activity_watcher
```

## Использование
```
const activityChecker = require('activity_watcher');

    ...
    сonst inactivityThreshold = 10000; // Порог бездействия в миллисекундах
    const checkInterval = 2000; // Период проверки в миллисекундах
    
    //Запускает отслеживание  
    activityChecker.startTracking((state) => {
        console.log("Состояние: ", state);    // вернет active/inactive при смене статуса (если пользователь активен, двигает мышью или нажимает клавиатуру, статус active будет неизменен.
                                            // Состояние измениться при истечении inactivityThreshold если пользователь прекратил активность
    }, inactivityThreshold, checkInterval);
    ...
    
    //Останавливает отслеживание
    activityChecker.stopTracking();
```

</details>

<details>

<summary>EN</summary>

# Activity Watcher (Only Windows)
This project is an example of using a node module based on C++ code logic. In fact, this is an add-on written in C++ for use in node js.
The browser, like the electron application, does not have access to the API at the operating system level. In particular, there is no access to tracking mouse movements and keyboard presses outside the browser/electron application window.

Using a node module implemented in C++ with access to the win API, we have the ability to track changes in user activity. In particular, the presence of mouse movements or keystrokes is implied by the activity indicator.
In addition, the module has the ability to configure the inactivity time and the verification period time.

## Install

This version was built on [Node.js](https://nodejs.org/) v18.0.0 .

Installing dependencies.

```sh
npm install

npm install node-addon-api
```

## Building the module locally (from project files using node-gyp)
```sh
npm node-gyp configure

npm node-gyp build
```

## Usage

```
const activityChecker = require('activity_watcher');

    ...
    сonst inactivityThreshold = 10000; // Порог бездействия в миллисекундах
    const checkInterval = 2000; // Период проверки в миллисекундах
    
    //Запускает отслеживание  
    activityChecker.startTracking((state) => {
        console.log("Состояние: ", state);    // вернет active/inactive при смене статуса (если пользователь активен, двигает мышью или нажимает клавиатуру, статус active будет неизменен.
                                            // Состояние измениться при истечении inactivityThreshold если пользователь прекратил активность
    }, inactivityThreshold, checkInterval);
    ...
    
    //Останавливает отслеживание
    activityChecker.stopTracking();
```


</details>

## ToDo

- Поддержка Linux

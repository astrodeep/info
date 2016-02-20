# Grunt - сборщик проектов

**Статус:** черновик.

## Ссылки

* [gruntjs.com](https://gruntjs.com/) - официальный сайт Grunt.
* [Grunt для тех, кто считает штуки вроде него странными и сложными](http://frontender.info/grunt-is-not-weird-and-hard/).
* [Сборка сайтов на независимых блоках из Jade и Stylus с использованием Grunt.js](http://oleggromov.com/slides/independent-blocks-assemble/).
* [Grunt: система сборки для фронтенд-разработчиков](http://sapegin.ru/pres/grunt/).

## Установка

1. Устанавливаем [Node.js](http://nodejs.org/download/), включающий в себя NPM (Node Packet Manager).
2. `npm i -g grunt-cli` - устанавливаем Grunt CLI (интерфейс командной строки).<br>
После этого следует закрыть и заново открыть окно терминала (Bash/Git-Bash).<br>
Если при вызове команды `grunt` пишет ошибку `Command Not Found`, то нужно перезагрузиться или выйти из системы и зайти снова.
3. Устанавливаем [Git](http://git-scm.com/book/ru/Введение-Установка-Git) под Вашу ОС, если ещё не установлен.

Эти 3 шага выполняются один раз.

## Команды для работы с NPM

- `npm i` - установка пакетов, заданных в `package.json` в секции `devDependecies` (устанавленные в текущей папке) и `dependecies` (используются глобально установленные пакеты). Обычно установка выполняется один раз, если пакеты не изменяются.
- `npm i -D package-name` - установка пакета `package-name`, добавляя его в `package.json`.
- `npm un -D package-name` - удаление пакета `package-name`, удаляя его из `package.json`.
- `npm up -D` - обновление версий пакетов и их зависимостей, обновляя версии в `package.json`.

## Пакеты NPM

Для повседневных задач нам достаточно:
* [`bump`](https://www.npmjs.org/package/grunt-bump) - обновление версии проекта.
* [`clean`](https://www.npmjs.org/package/grunt-contrib-clean) - очистка папки от файлов.
* [`spritesmith`](https://www.npmjs.org/package/grunt-spritesmith) - генератор спрайтов и CSS переменных.
* [`imagemin`](https://www.npmjs.org/package/grunt-contrib-imagemin) - сжатие картинок.
* [`stylus`](https://www.npmjs.org/package/grunt-contrib-stylus) - препроцессор CSS.
* [`autoprefixer`](https://www.npmjs.org/package/grunt-autoprefixer) - подстановка префиксов для заданных браузеров.
* [`combine-media-queries`](https://www.npmjs.org/package/grunt-combine-media-queries) - комбинирование медиа-запросов в CSS.
* [`csscomb`](https://www.npmjs.org/package/grunt-csscomb) - форматирование CSS.
* [`jade`](https://www.npmjs.org/package/grunt-contrib-jade) - препроцессор HTML.
* [`prettify`](https://www.npmjs.org/package/grunt-prettify) - форматирование HTML.
* [`jshint`](https://www.npmjs.org/package/grunt-contrib-jshint) - проверка JavaScript на качество кода с подсказками.
* [`copy`](https://www.npmjs.org/package/grunt-contrib-copy) - создание копий файлов.
* [`uglify`](https://www.npmjs.org/package/grunt-contrib-uglify) - минифицирование и обфускация скриптов.
* [`replace`](https://www.npmjs.org/package/grunt-replace) автозамена паттернов на заданные значения.
* [`newer`](https://www.npmjs.org/package/grunt-newer) - выполнение задач только с новыми файлами.
* [`browser-sync`](https://www.npmjs.org/package/grunt-browser-sync) - локальный сервер и автоперезагрузка страницы с уведомлениями.
* [`watch`](https://www.npmjs.org/package/grunt-contrib-watch) - отслеживание изменений файлов и их компиляция.

В зависимости от проекта дополнительно могут пригодиться такие пакеты:
* Для объединения и минификации:
    * [`cssmin`](https://www.npmjs.org/package/grunt-contrib-cssmin) - минификация CSS.
    * [`concat`](https://www.npmjs.org/package/grunt-contrib-concat) - объединение скриптов в один файл.<br>
      *Если возникают ошибки при конкатенации скриптов, то нужно установить порядку их зависисмости*.
    * [`uglify`](https://www.npmjs.org/package/grunt-contrib-uglify) - обфускация скриптов.

* Препроцессоры:
    * [`coffee`](https://www.npmjs.org/package/grunt-contrib-coffee) - CoffeeScript препроцессор JavaScript.
    * [`less`](https://www.npmjs.org/package/grunt-contrib-less) - Less препроцессор CSS.
    * [`sass`](https://www.npmjs.org/package/grunt-contrib-sass)/[`compass`](https://www.npmjs.org/package/grunt-contrib-compass) - Sass препроцессор CSS.


* Если этого будет недостаточно, можно поискать подходящие по ссылкам:
    * [gruntjs.com/plugins](https://gruntjs.com/plugins)
    * [npmjs.org](https://www.npmjs.org/)


## 3. Autoprefixer - автоподстановка префиксов для стилей

Для автоматической подстановки префиксов в зависимости от заданных минимальных версий браузеров используется [grunt-autoprefixer](https://www.npmjs.org/package/grunt-autoprefixer), при этом самим указывать префиксы в стилях, делать для них миксины или использовать готовые не нужно.

Версии браузеров указываются в [`package.json`](https://github.com/CSSSR/csssr-project-template/blob/master/package.json#L55-L63).

```javascript
"browsers": {
    "android": 4,
    "chrome": 36,
    "firefox": 31,
    "ie": 10,
    "ios": 6,
    "opera": 12,
    "safari": 6
}
```


## 4. BrowserSync - автоперезагрузка страницы и оповещения

Каждый раз, когда изменяются и компилируются исходники происходит автоперезагрузка страницы с помощью [`grunt-browser-sync`](https://www.npmjs.org/package/grunt-browser-sync), при этом в окне браузера наверху справа будет появляться уведомление.


## 5. Список страниц

Если на проекте страниц больше одной, то необходимо сделать список со страницами.

В качестве списка используется индексная страница `index.jade` (`index.html`).

Список страниц должен быть оформлен в соответсвии с дизайном сайта:
* Логотип сайта.
* Ссылки по цветовой гамме сайта.
* Список и логотип должны быть отцентрированы.
* **Стили должны быть встроены в страницу, подключать внешний стилевой файл или использовать стили сайта не нужно**.
* Страница должна быть валидной и корректно отображаться на мобильных устройствах.

## Установка

[Node.js](http://nodejs.org/download/), включающий в себя NPM (Node Packet Manager).

## Обновление npm

### Windows
* Зайти в папку с установленной nodejs и обновить npm до последней версии

	```bash
	cd "C:\Program Files\nodejs"
	```

	или

	```bash
	cd "C:\Program Files (x86)\nodejs"
	```

	в зависимости от того где у вас установленна nodejs, и выполнить

	```bash
	npm install npm@latest
	```

## Команды для работы с NPM

- `npm i` - установка пакетов, заданных в `package.json`. Обычно установка выполняется один раз, если пакеты не изменяются.
- `npm i -D package-name` - установка пакета `package-name`, добавляя его в `package.json` в секцию `devDependencies`.
- `npm un -D package-name` - удаление пакета `package-name`, удаляя его из `package.json`.
- `npm up -D` - обновление версий пакетов и их зависимостей, обновляя версии в `package.json`.

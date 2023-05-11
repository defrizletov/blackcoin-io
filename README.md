<p align="center"><img src="https://raw.githubusercontent.com/defrizletov/blackcoin-io/main/docs/logo.svg?sanitize=true"></p>
<p align="center">
<a href="https://www.npmjs.com/package/blackcoin-io"><img src="https://img.shields.io/npm/v/blackcoin-io.svg?style=flat-square" alt="NPM version"></a>
<a href="https://www.npmjs.com/package/blackcoin-io"><img src="https://img.shields.io/npm/dt/blackcoin-io.svg?style=flat-square" alt="NPM downloads"></a>
</p>

<div align="center">

**Модуль** для удобного использования **[BlackCoin API](https://vk.com/@black_coin_roulette-api)**.
  
От **[AdepT-Hub](https://adept-hub.ru)** с ❤.

</div>

## 📦 Установка

```sh
npm i blackcoin-io
```

<br/>

## 🚀 Использование

```js
const { BlackCoin, BlackCoinCallback } = require('blackcoin-io');

// token - ваш ключ авторизации, полученный в приложении.
const blackCoin = new BlackCoin({ token: process.env.TOKEN });

// Запрос для примера, получение баланса нашего аккаунта.
// Потом вывод ответа или ошибки в консоль.
blackCoin.getBalance().then(console.log).catch(console.error);

// Подключение callback.

// Создаем сервер с нашим callback_secret.
const blackCoinCallback = new BlackCoinCallback(process.env.CALLBACK_SECRET);

// Устанавливаем обработчик, который выполнится, когда придёт пополнение.
// Эта функция выведет объект события в консоль.
blackCoinCallback.on(event => console.log(event));

// Запуск сервера на порт 3000 и хост localhost (порт 3000 стоит по умолчанию).
// Потом, если все успешно, пишем в консоль, что сервер запустился, в противном случае выводим ошибку в консоль.
blackCoinCallback.start(3000, 'localhost').then(console.log('BlackCoin Callback has been started.')).catch(console.error);
```
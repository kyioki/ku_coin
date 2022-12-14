# Использование KuCoin

Дано: криптовалютная биржа с поддержкой спотовой, маржинальной и фьючерсной торговли. На ней представлено 440 криптовалют в 830 парах.
Документация: https://docs.kucoin.com/#general
## Протоколы
KuCoin использует:
1. REST API
2. WebSocket
###### REST API - технология позволяет получать и модифицировать данные и состояния удаленных приложений, передавая HTTP-вызовы через интернет или любую другую сеть.
###### WebSocket - это передовая технология, которая позволяет создавать интерактивное соединение между клиентом (браузером) и сервером для обмена сообщениями в режиме реального времени. Веб-сокеты, в отличие от HTTP, позволяют работать с двунаправленным потоком данных, что делает эту технологию совершенно уникальной.

### Order book
Беру в пример: https://www.kucoin.cloud/trade/BTC-USDT
![img.png](img.png)
Используя документацию, открываю консоль, где ввожу запрос 'order-book' выдается данный запрос с параметром GET, который читает данные с сайта.
![img_1.png](img_1.png)
Переходя по данному запросу https://www.kucoin.com/_api/order-book/orderbook/level2?symbol=BTC-USDT&limit=500&c=e667ef0837074beba45e6ac0a6cf7de7&lang=en_US
![img_2.png](img_2.png)
Level 2 включает все заявки и запросы (агрегированные по цене). Этот уровень возвращает только один агрегированный размер для каждой цены (как если бы был только один заказ по этой цене).

### Лента сделок
![img_3.png](img_3.png)
![img_4.png](img_4.png)
https://www.kucoin.com/_api/order-book/histories?symbol=BTC-USDT&c=e667ef0837074beba45e6ac0a6cf7de7&lang=en_US
![img_5.png](img_5.png)
Запрос идет через эту конечную точку, где мы получаем ленту сделок данной валюты.
![img_6.png](img_6.png)

### График цены (snapshot + обновления)
https://www.kucoin.com/_api/trade-front/market/getSymbol/noSerialize/BTC?lang=en_US
![img_7.png](img_7.png)
Запрос представляет собой график цены на рынке, которая указана или была указана в тот или иной момент по рыночному показателю.
![img_8.png](img_8.png)

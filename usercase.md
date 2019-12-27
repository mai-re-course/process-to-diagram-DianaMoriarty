# Сценарий "Загрузка веб-страницы в браузере"

**Акторы:**
- Пользователь
- Браузер
- Сервер
- DNS-сервер

**Цель:** пользователь хочет получить контент с веб-страницы.

**Предусловия:** у пользователя открыт браузер.

**Сценарий:**

1. Пользователь вбивает в строку браузера google.com
2. Браузер парсит URL. 
3. Браузер проверяет список «предзагруженных HSTS.
4. Браузер проверяет наличие домена в своём кэше. Если его нет - переход к альтернативному сценарию 4.1.
5. Браузер осуществляет вызов функции socket системной библиотеки и запрашивает поток TCP сокета.
6. TLS handshake 
7. Браузер отправляет HTTP-запрос на сервер
8. Сервер обрабатывает HTTP-запрос и отправляет ответ.
9. Браузер парсит HTML.
10. Браузер интерпретирует CSS.
11. Браузер рендерит страницу.
12. Браузер исполняет JavaScript-код 
13. Браузер отображает контент пользователю.

Результат:
- Пользователь получил содержимое веб-страницы google.com

Исключения:
- отсутствует интернет-соединение
- введен неверный URL

Альтернативные сценарии:   
4.1 Если домена в кэше нет, то браузер отправляет запрос к сетевому DNS-серверу. Возврат на шаг 5.

**Sequence diagram**  

![sequence](https://www.plantuml.com/plantuml/img/VP9DJiCm48NtESLSe7JF0XMf2rO84IxWEaDiwjZ6CoxgxHcdIHkBqDt8xyqtVzuHgyHvS8tI719amjGSGlQTIcSufF1J7j2pvJDqdkPGNayY53jidcOZF8Bec0Zw47g73peC1MnFYl5AcyrLNbI9479owx8sg8_mqdwqu2mntNFjNrlGYWmsoZ7imw2i1qlW0uD4R72I5mmPJVAVtzyWuNT6ublRPUeYRwfI5ol5u0cR3Yit-cx9lknASa943nJq4HVuQPEJgIx2EjwAh177wm4x0gDyHqOTSPtqQRqbit2jqGnplCu_OnPwJ44ZaVNz7rTLREAKlglTJAFUkR_XmMqrqVRhdmidsQq4vOPHzTKOUG99OVc4eqN2xBZqEveNhSn_SISy-Vs_)

**Activity diagram**  

![activity](https://www.plantuml.com/plantuml/img/PL91KiCm3Bpx5Jes5nwGNCh00IuTXl01uoY9IMePIIamayTZfwJDq8l7Nkr6cvNsefPrEevcdWHvDilRb1WKMQ0ZwaQyStIiZ6zXTo1upfM02ev2GAUUGW7QOu3T3qfXoiW-A20pSPK-Hz7WA0YxG8MPtvc-bZvbj9pGYSVAO6XyQqhNenlWgNwhOVIYKgtGuw46PwN7iuc6ZjO7y0BfNF1YPVwnSaDJth--0EFdXAALcPiWyuf9f22uDjwOefZ-GyWDc2K9EosmkhXHRVXBMg2ZG6z38xqTSAjhVV3ItzIl-burRZnUX979eOWFtRMwaczjjCG3h8dsUaoHBf3jSawcVAZh55KQMsHKcoVsZu3Vw2P5-B0dAuvzpDDjpW51PfgIqnKv3ngYxL8fUKH9Qx90wJgDcksUYvTbIjFV9sLQi5y0)

**Component Diagram**  

![component](https://www.plantuml.com/plantuml/img/PL7B3e8m4Bpp5Hlk_88X-3WP3n9Fn906LY1AYzkY1yE_knOgHNiWdPbbPtORQoF8zEqjw4Hn5HL2k2Cb3Mnb6S8h03wdunwYQ0LPGkgfaSwMBLJRAObSEj4_x5eKDLgkaGRf8We4GbaYOPbtx1GCisV25nmTlouGKLFLXerhOxgSyDwZDhRZH6YsqWX_qVnwgwP83oSwO4TQD0e6c1Dj3gcRtql4lx2moEBXZvun1ktxUOJNOBASExXX5jDmekbkXN6dzcknsxnViznnp8XVzmq0)

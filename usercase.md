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

![sequence](https://www.plantuml.com/plantuml/img/TL91KiCm3Bpd5Ve0zDu3KsPwuCGmb0-uZeXD7SjOSfd-7hbDqcG8DrcxMgqaxrXCbjA7nbYX38KnDqSgiJNv0iTCFpM1KRnSe8qyXfezAr3fyF0q4c4BYcDcw8YwW8-M-YhipqPmKeka3zBoCRE5P38Zb1pMGElGdk3by760u5duVyx-zG3MiCF6184zzSP7y0nQ01g9mm4U_Qfr7KfjFx-_GSRlWYntmtNU2Zyi9hnHEL5aR5fSi36sS-tRbhI64aPWiYUSoGyx74ZB9cBJlScQulLk8871cTYoCoTSL_hqqRERiTRKd4YQvh-lTy9J9elCFdOJQxNPe5DzBtOpZFhdS32UtaaVDfPvyxLoNcLbtQm6zOB9T8iXog2ZRVNpNIaQbY3LxPKyCpB-mPtgwQ__1G00)

**Activity diagram**  

![activity](https://www.plantuml.com/plantuml/img/PL91KiCm3Bpx5Jes5nwGNCh00IuTXl01uoY9IMePIIamayTZfwJDq8l7Nkr6cvNsefPrEevcdWHvDilRb1WKMQ0ZwaQyStIiZ6zXTo1upfM02ev2GAUUGW7QOu3T3qfXoiW-A20pSPK-Hz7WA0YxG8MPtvc-bZvbj9pGYSVAO6XyQqhNenlWgNwhOVIYKgtGuw46PwN7iuc6ZjO7y0BfNF1YPVwnSaDJth--0EFdXAALcPiWyuf9f22uDjwOefZ-GyWDc2K9EosmkhXHRVXBMg2ZG6z38xqTSAjhVV3ItzIl-burRZnUX979eOWFtRMwaczjjCG3h8dsUaoHBf3jSawcVAZh55KQMsHKcoVsZu3Vw2P5-B0dAuvzpDDjpW51PfgIqnKv3ngYxL8fUKH9Qx90wJgDcksUYvTbIjFV9sLQi5y0)

**Component Diagram**  

![component](https://www.plantuml.com/plantuml/img/NL7B3e8m4BptApRS-GL3y74o7YIUY24Dh42KWjkY1yE_knOgXHwQpipkxAEHDf9Ctpo4w6H-boL2SA1M6TYh8e2F03vvstIjGYPZQjyQQSLkPLwXvMfba6uoHo1K1H8MMSUUOfZTOtxWw9rETbS8gIuh4swWCgRB29yzQcCT9q9pAOt04VyaNxRnLasGNavq0CBPUJGI0ymTxKw9czJhY5DOMFJYuP-UCWRjr_C8ps0gEJkuOHRJS4UNyt55JW_BZbksjyNkB_oOvTOZHlorNm00)

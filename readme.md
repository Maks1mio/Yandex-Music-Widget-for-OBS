[![Русский](https://img.shields.io/badge/Русский-white?style=for-the-badge)](https://github.com/Maks1mio/Yandex-Music-Widget-for-OBS)
[![English](https://img.shields.io/badge/English-white?style=for-the-badge)](https://github.com/Maks1mio/Yandex-Music-Widget-for-OBS/blob/main/other/en.md)
[![Українська](https://img.shields.io/badge/Українська-white?style=for-the-badge)](https://github.com/Maks1mio/Yandex-Music-Widget-for-OBS/blob/main/other/ua.md)
[![Беларуская](https://img.shields.io/badge/Беларуская-white?style=for-the-badge)](https://github.com/Maks1mio/Yandex-Music-Widget-for-OBS/blob/main/other/by.md)
[![Қазақша](https://img.shields.io/badge/Қазақша-white?style=for-the-badge)](https://github.com/Maks1mio/Yandex-Music-Widget-for-OBS/blob/main/other/kz.md)

# Яндекс Музыка виджет для OBS
[![Join our Discord](https://img.shields.io/discord/1227552882744754267?label=Discord&logo=discord&logoColor=white&style=for-the-badge)](https://discord.com/invite/pulsesync)
[![Subscribe on Boosty](https://img.shields.io/badge/Boosty-Subscribe-orange?style=for-the-badge)](https://boosty.to/evt)

![safsa](https://repository-images.githubusercontent.com/915801533/829d6f0f-0207-4eda-b064-a3362d28ad2c)

## Инструкция по установке и использованию

Привет! Ниже описано, как запустить виджет.  
Это обычный HTML/JS-проект без использования Node.js или других сборщиков — можно открыть в OBS как «Browser Source» или на любом локальном/внешнем сервере.

## Что делает проект?

1. **Подключается** к нашему публичному API ([pulsesync.dev/api/v1/](https://ru-node-1.pulsesync.dev/api/v1/)), чтобы узнавать, какая композиция играет.  
2. **Отображает** карточку с обложкой, названием трека, исполнителем, статусом (playing и т.д.).  

![aTYB7VGE7H](https://github.com/user-attachments/assets/2e5a33ed-5e43-41d0-82e8-19b96067b79b)

## Как получить доступ к публичному API?

1. **Оформите подписку** на [Boosty.to/evt](https://boosty.to/evt) за символические 30 рублей.  
2. После покупки вам придёт **сообщение** с инструкцией:  
   ```text
   "Здравствуйте и спасибо за подписку!
    Привяжите ваш Discord аккаунт в настройках Boosty:
    https://boosty.to/app/settings/external-apps
    
    После этого зайдите на сервер:
    https://discord.com/invite/pulsesync
    и бот выдаст вам роль бета-тестера (в течение 15 минут).
    
    Если роли не появились, обратитесь к администраторам.
    Если у вас была старая версия программы, пожалуйста, сделайте репатч.
    Приятного пользования!"
   ```
3. **Получите роль** бета-тестера на сервере Discord.
4. **Зарегистрируйтесь** в приложении, затем в Discord боте используйте команду `/create-api-key` (или если забыли — `/get-api-key`).
5. **Скопируйте** свой токен и вставьте его в `api.js`, там, где переменная `API_KEY`.

## Структура файлов

```
├─ designs
│   └─ EvT (Pulsma)
│       ├─ color.js
│       ├─ default.png
│       ├─ index.html
│       ├─ main.js
│       ├─ style.css
│       └─ textAnimation.js
└─api.js
```

В качестве примера я хотел бы привести свою реализацию темы «EvT (Pulsma)».

- **`api.js`**  
  Здесь лежит функция `fetchTrackStatusFromApi()` и ваш `API_KEY`.  
- **`color.js`**  
  Код, который определяет цвет обложки (через canvas), и при необходимости притемняет его.  
- **`textAnimation.js`**  
  «Матрица»-анимация (или любая другая), которая постепенно «пропечатывает» финальный текст.  
- **`index.html`**  
  Основная страница с разметкой. В неё подключаются все скрипты и стили.  
- **`style.css`**  
  Можно вынести сюда общую стилистику карточки.  
- **`main.js`**  
  Общая логика анимации (slideOut/slideIn), работа с DOM (обложка, текст), вызов `api.js` и т.д.  
- **`default.png`**  
  «Заглушка» для обложки.

## Запуск в OBS (или где угодно)

1. Откройте **OBS** и добавьте **Browser Source**.  
2. Укажите путь к `index.html` (например, `file:///C:/Project/designs/EvT%20(Pulsma)/index.html`) или локальный/внешний сервер.  
3. Отрегулируйте размер.  
4. Готово! Карточка будет обновляться и показывать текущий трек с анимацией.

## Свой дизайн?

Мы **приветствуем** разные стили оформления!  
Если у вас есть идеи — сделайте свой вариант, создайте **Pull Request** в этот репозиторий, и мы добавим новую тему в папку `designs/`.  
Пример ветки:  
```
designs/
  EvT (Pulsma)/
    color.js
    default.png
    index.html
    main.js
    style.css
    textAnimation.js
```
Вы можете назвать свою папку как угодно, например:  
```
designs/
  MyChinazisDesign/
    color.js
    ...
```

## Контакты

- Наш [Discord-сервер](https://discord.com/invite/pulsesync).  
- [Boosty](https://boosty.to/evt) для оформления подписки.  

Если возникнут вопросы или что-то не работает — спрашивайте на Discord-сервере.

---
**Бай бай!**

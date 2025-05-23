# Yandex Music Widget для OBS

[![Приєднуйтесь до нашого Discord](https://img.shields.io/discord/1227552882744754267?label=Discord&logo=discord&logoColor=white&style=for-the-badge)](https://discord.com/invite/pulsesync)
[![Підписатися на Boosty](https://img.shields.io/badge/Boosty-Subscribe-orange?style=for-the-badge)](https://boosty.to/evt)

![safsa](https://repository-images.githubusercontent.com/915801533/829d6f0f-0207-4eda-b064-a3362d28ad2c)

## Інструкція з установки та використання

Привіт! Нижче описано, як запустити віджет.  
Це звичайний HTML/JS проект без використання Node.js або інших збірників — його можна відкрити в OBS як «Browser Source» або на будь-якому локальному/віддаленому сервері.

## Що робить проект?

1. **Підключається** до нашого публічного API ([pulsesync.dev/api/v1/](https://ru-node-1.pulsesync.dev/api/v1/)), щоб дізнатися, яка композиція зараз грає.  
2. **Відображає** картку з обкладинкою, назвою треку, виконавцем, статусом (playing тощо).

![aTYB7VGE7H](https://github.com/user-attachments/assets/2e5a33ed-5e43-41d0-82e8-19b96067b79b)

## Як отримати доступ до публічного API?

1. **Оформіть підписку** на [Boosty.to/evt](https://boosty.to/evt) за символічні 30 рублів.  
2. Після покупки вам прийде **повідомлення** з інструкцією:
   ```text
   "Вітаємо і дякуємо за підписку!
    Прив’яжіть свій Discord акаунт в налаштуваннях Boosty:
    https://boosty.to/app/settings/external-apps
    
    Після цього заходьте на сервер:
    https://discord.com/invite/pulsesync
    і бот видасть вам роль бета-тестера (протягом 15 хвилин).
    
    Якщо роль не з’явилася, зверніться до адміністраторів.
    Якщо у вас була стара версія програми, будь ласка, зробіть репатч.
    Приємного користування!"
   ```
3. **Отримайте роль** бета-тестера на сервері Discord.
4. **Зареєструйтесь** в додатку, потім використовуйте команду `/create-api-key` в Discord-боті (або `/get-api-key`, якщо забули).
5. **Скопіюйте** свій токен і вставте його в `api.js` у змінну `API_KEY`.

## Структура файлів

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

Як приклад, ось моя реалізація теми «EvT (Pulsma)».

- **`api.js`**  
  Тут знаходиться функція `fetchTrackStatusFromApi()` та ваш `API_KEY`.  
- **`color.js`**  
  Код, який визначає колір обкладинки (за допомогою canvas) і при потребі затемнює його.  
- **`textAnimation.js`**  
  Анімація в стилі «Матриця» (або інша), яка поступово «друкує» фінальний текст.  
- **`index.html`**  
  Головна сторінка з розміткою. В неї підключаються всі скрипти та стилі.  
- **`style.css`**  
  Можна винести сюди загальну стилістику картки.  
- **`main.js`**  
  Загальна логіка анімації (slideOut/slideIn), робота з DOM (обкладинка, текст), виклик `api.js` тощо.  
- **`default.png`**  
  «Заглушка» для обкладинки.

## Запуск в OBS (або де завгодно)

1. Відкрийте **OBS** та додайте **Browser Source**.  
2. Вкажіть шлях до `index.html` (наприклад, `file:///C:/Project/designs/EvT%20(Pulsma)/index.html`) або використайте локальний/віддалений сервер.  
3. Відрегулюйте розмір.  
4. Готово! Картка буде оновлюватися та показувати поточний трек з анімацією.

## Власний дизайн?

Ми дуже **привітно сприймаємо** різні стилі оформлення!  
Якщо у вас є ідеї — зробіть свій варіант, створіть **Pull Request** в цьому репозиторії, і ми додамо нову тему у папку `designs/`.  
Приклад структури папки:  
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
Ви можете назвати свою папку як завгодно, наприклад:  
```
designs/
  MyChinazisDesign/
    color.js
    ...
```

## Контакти

- Наш [Discord-сервер](https://discord.com/invite/pulsesync).  
- [Boosty](https://boosty.to/evt) для оформлення підписки (Якщо будуть проблеми з оплатою пишіть нам у дискорд).  

Якщо виникнуть питання або щось не працює — питайте на Discord-сервері.

---
**Бувайте!**

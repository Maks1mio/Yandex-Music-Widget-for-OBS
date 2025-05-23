# Yandex Music Widget для OBS

[![Далучайцеся да нашага Discord](https://img.shields.io/discord/1227552882744754267?label=Discord&logo=discord&logoColor=white&style=for-the-badge)](https://discord.com/invite/pulsesync)
[![Падпісацца на Boosty](https://img.shields.io/badge/Boosty-Subscribe-orange?style=for-the-badge)](https://boosty.to/evt)

![safsa](https://repository-images.githubusercontent.com/915801533/829d6f0f-0207-4eda-b064-a3362d28ad2c)

## Інструкцыя па ўсталёўцы і выкарыстанні

Вітаем! Ніжэй апісана, як запусціць віджэт.  
Гэта звычайны HTML/JS-праект без выкарыстання Node.js або іншых сборнікаў — яго можна адкрыць у OBS як «Browser Source» або размясціць на любым лакальным/аддаленым серверы.

## Што робіць праект?

1. **Падключаецца** да нашага публічнага API ([pulsesync.dev/api/v1/](https://ru-node-1.pulsesync.dev/api/v1/)), каб даведацца, якая кампазіцыя зараз грае.  
2. **Адлюстроўвае** картку з абкладінкай, назвай трэка, выканаўцам, статусам (playing і інш.).

![aTYB7VGE7H](https://github.com/user-attachments/assets/2e5a33ed-5e43-41d0-82e8-19b96067b79b)

## Як атрымаць доступ да публічнага API?

1. **Аформіце падпіску** на [Boosty.to/evt](https://boosty.to/evt) за сімвалічныя 30 рублёў.  
2. Пасля пакупкі вам прыйдзе **паведамленне** з інструкцыяй:
   ```text
   "Вітаем і дзякуем за падпіску!
    Прыкруціце ваш Discord акаўнт у наладках Boosty:
    https://boosty.to/app/settings/external-apps
    
    Пасля гэтага зайдзіце на сервер:
    https://discord.com/invite/pulsesync
    і бот выдасць вам ролю бэта-тэсцэра (пратрымкай 15 хвілін).
    
    Калі роля не з'явілася, звярніцеся да адміністратараў.
    Калі ў вас была старая версія праграмы, калі ласка, зрабіце рэпатч.
    Прыемнага выкарыстання!"
   ```
3. **Атрымаеце ролю** бэта-тэсцэра на Discord-серверы.
4. **Зарэгіструйцеся** у дадатку, а затым выкарыстоўвайце каманду `/create-api-key` у Discord-боте (ці `/get-api-key`, калі забылі).
5. **Скапіруйце** ваш токен і ўстаўце яго ў `api.js`, у тым месцы, дзе знаходзіцца зменная `API_KEY`.

## Структура файлаў

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

Як прыклад, прыводзім маю рэалізацыю тэмы «EvT (Pulsma)».

- **`api.js`**  
  Тут размешчана функцыя `fetchTrackStatusFromApi()` і ваш `API_KEY`.  
- **`color.js`**  
  Код, які вызначае колер абкладінкі (праз canvas) і, пры неабходнасці, прыцямняе яго.  
- **`textAnimation.js`**  
  Анімацыя ў стылі «Матрыца» (ці іншая), якая паступова «надрукоўвае» фінальны тэкст.  
- **`index.html`**  
  Галоўная старонка з разметкай. У яе падключаюцца ўсе скрыпты і стылі.  
- **`style.css`**  
  Тут можна змясціць агульную стылістыку карткі.  
- **`main.js`**  
  Агульная лагіка анімацыі (slideOut/slideIn), праца з DOM (абкладінка, тэкст), выклік `api.js` і г.д.  
- **`default.png`**  
  «Заглушка» для абкладінкі.

## Запуск у OBS (ці дзе заўгодна)

1. Адкрыйце **OBS** і дадайце **Browser Source**.  
2. Укажыце шлях да `index.html` (напрыклад, `file:///C:/Project/designs/EvT%20(Pulsma)/index.html`) або лакальны/аддалены сервер.  
3. Адрэгулюйце памер.  
4. Гатова! Картка будзе абнаўляцца і паказваць бягучы трэк з анімацыяй.

## Уласны дызайн?

Мы вельмі **прывітаем** розныя стылі афармлення!  
Калі ў вас ёсць ідэі — зрабіце свой варыянт, стварыце **Pull Request** ў гэтым рэпазіторыі, і мы дадамо новую тэму ў папку `designs/`.  
Прыклад структуры тэчкі:  
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
Вы можаце назваць сваю тэчку як заўгодна, напрыклад:  
```
designs/
  MyChinazisDesign/
    color.js
    ...
```

## Кантакты

- Наш [Discord-сервер](https://discord.com/invite/pulsesync).  
- [Boosty](https://boosty.to/evt) для афармлення падпіскі.  

Калі ўзнікнуць пытанні або нешта не працуе — пішыце на Discord-серверы.

---
**Бувайце!**

---
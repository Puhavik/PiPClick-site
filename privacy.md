---
layout: default
title: Privacy Policy / Политика конфиденциальности
permalink: /privacy
---

# Privacy Policy for PiPClick / Политика конфиденциальности PiPClick

**Effective Date / Дата вступления в силу:** 17 November 2026 / 17 ноября 2026 г.

*This document contains the Privacy Policy in English, followed by the Russian version.*  
*Этот документ содержит политику конфиденциальности на английском языке, а ниже — версию на русском языке.*

---

## English Version

### Overview
PiPClick ("the Application", "the Extension") is a minimal macOS Safari Web Extension designed to toggle Picture-in-Picture mode on HTML5 videos via a toolbar click or keyboard shortcut (`⌥⇧P` / `Alt+Shift+P`).

Your privacy is paramount. PiPClick was engineered from day one to operate locally on your device with complete transparency and zero data collection.

### 1. Zero Data Collection and Zero Telemetry
- **No Personal Data Collected:** PiPClick does not collect, record, process, store, sell, or transmit any personal data, identifiers, IP addresses, or device information.
- **No Browsing History or Page Content:** PiPClick never reads, inspects, logs, or stores your browsing history, visited URLs, page content, DOM tree elements, cookies, keystrokes, form submissions, or personal files.
- **No Analytics or Tracking:** PiPClick contains zero tracking code, zero analytical libraries, zero advertising frameworks, and zero crash-reporting SDKs.

### 2. App Sandbox and Zero Network Permissions
- **Zero Network Capabilities:** Both the native macOS host application and the Safari Web Extension operate strictly within Apple's App Sandbox without the `com.apple.security.network.client` or `com.apple.security.network.server` entitlements.
- **No Network Requests:** The application and extension make no network requests whatsoever. It is technically impossible for PiPClick to transmit data over local networks or the Internet.
- **Fully Offline:** All logic executes entirely on your local machine.

### 3. Safari Extension Permissions & Scripts

PiPClick utilizes two lightweight JavaScript files to perform its functionality:

#### A. Keyboard Shortcut Detection (`keys.js`)
- **Why it is used:** Safari resolves extension keyboard shortcuts by typed character. On non-Latin keyboard layouts (e.g. Russian, Greek, Hebrew), pressing `⌥⇧P` does not trigger the shortcut because the physical key produces a different localized character. To ensure that `⌥⇧P` works reliably across any keyboard layout, `keys.js` runs across frames.
- **Strictly Isolated Listener:** `keys.js` only listens for `keydown` events when a modifier key (Option `⌥`, Control `⌃`, or Command `⌘`) is pressed.
- **Physical Key Code Only:** It sends only the physical hardware key identifier (`event.code`, such as `"KeyP"`) and the modifier key states to the extension's local background script.
- **Zero Page Inspection:** `keys.js` **never** reads, inspects, or captures page text, DOM contents, input fields, passwords, or visited URLs. Keystrokes without modifier keys are completely ignored.
- **`<all_urls>` Host Permission:** Safari requires the `<all_urls>` host permission so that `keys.js` can catch the global shortcut on whichever webpage you are currently viewing. PiPClick does not use this permission to read page data.

#### B. Picture-in-Picture Invocation (`pip.js`)
- **On-Demand Execution:** `pip.js` is **never** permanently resident on your webpages. It is injected into the active tab **only** when you explicitly click the PiPClick toolbar button or trigger the keyboard shortcut.
- **Operation:** It inspects video elements on the current page (including inside open Shadow DOM trees), prioritizes actively playing videos or the video with the largest display area, bypasses restrictive `disablePictureInPicture` flags, and requests Picture-in-Picture mode.
- **Immediate Termination:** As soon as Picture-in-Picture is toggled, execution finishes. No page data or video information is stored or transmitted.

### 4. Third-Party Services
PiPClick does not integrate with, transmit data to, or rely on any third-party APIs, SDKs, or services.

### 5. Children's Privacy
Because PiPClick collects no information whatsoever, it does not collect or solicit personal information from anyone, including children under 13.

### 6. Changes to This Policy
If this Privacy Policy is updated, the revised policy will be posted at this URL with an updated effective date. Given PiPClick's privacy-by-design architecture, the core principle of zero data collection will never change.

### 7. Contact and Source Code
If you have questions about this policy or need help, contact us via GitHub:

- **GitHub Issues:** [https://github.com/Puhavik/PiPClick-site/issues](https://github.com/Puhavik/PiPClick-site/issues)

---

## Русская версия

### Общие сведения
PiPClick («Приложение», «Расширение») — минималистичное Safari Web Extension для macOS, предназначенное для переключения режима «Картинка в картинке» (Picture-in-Picture) на HTML5-видео по клику на иконку в панели инструментов Safari или по горячей клавише (`⌥⇧P` / `Alt+Shift+P`).

Ваша конфиденциальность является безусловным приоритетом. PiPClick спроектирован для полностью локальной работы на вашем устройстве с соблюдением полной прозрачности и абсолютного отказа от сбора данных.

### 1. Нулевой сбор данных и отсутствие телеметрии
- **Персональные данные не собираются:** PiPClick не собирает, не регистрирует, не обрабатывает, не хранит, не продаёт и не передаёт никакие персональные данные, идентификаторы, IP-адреса или информацию об устройстве.
- **Без доступа к истории и содержимому страниц:** PiPClick никогда не читает, не анализирует, не сохраняет и не передаёт историю просмотров, URL-адреса посещённых сайтов, структуру DOM, текст страниц, cookies, нажатия клавиш, введённые пароли, данные форм или локальные файлы.
- **Без аналитики и отслеживания:** В PiPClick отсутствуют трекеры, аналитические библиотеки, рекламные модули и фреймворки отчётов об ошибках.

### 2. Песочница (App Sandbox) и полное отсутствие сетевых прав
- **Отсутствие сетевых прав:** Контейнерное macOS-приложение и расширение Safari Web Extension выполняются исключительно внутри защищённой песочницы Apple (App Sandbox) без разрешений `com.apple.security.network.client` или `com.apple.security.network.server`.
- **Без сетевых запросов:** Приложение и расширение не выполняют никаких сетевых запросов. У PiPClick отсутствует техническая возможность передавать данные по сети или через Интернет.
- **Полностью автономная работа:** Все вычисления и действия производятся исключительно локально на вашем компьютере Mac.

### 3. Разрешения Safari и работа скриптов

PiPClick использует два компактных JavaScript-файла для выполнения своей функции:

#### A. Распознавание горячей клавиши (`keys.js`)
- **Зачем используется:** Safari сравнивает сочетания клавиш расширений по введённому символу. На нелатинских раскладках клавиатуры (например, на русской) нажатие `⌥⇧P` не вызывает расширение, так как физическая клавиша генерирует иной локализованный символ. Чтобы сочетание `⌥⇧P` стабильно работало на любой раскладке клавиатуры, скрипт `keys.js` выполняется на страницах.
- **Строго изолированный слушатель:** `keys.js` слушает события `keydown` исключительно тогда, когда зажата хотя бы одна клавиша-модификатор (Option `⌥`, Control `⌃` или Command `⌘`).
- **Только физический код клавиши:** Скрипт сообщает фоновому процессу только физический код аппаратной клавиши (`event.code`, например `"KeyP"`) и состояние модификаторов.
- **Никакого чтения содержимого страниц:** `keys.js` **никогда не читает**, не анализирует и не перехватывает содержимое страниц, элементы DOM, текстовые поля ввода, пароли или посещаемые URL-адреса. Обычные нажатия клавиш без модификаторов полностью игнорируются.
- **Разрешение хостов (`<all_urls>`):** Safari требует разрешение `<all_urls>` исключительно для того, чтобы `keys.js` мог зафиксировать глобальное сочетание клавиш на открытой веб-странице. PiPClick не использует это разрешение для чтения или модификации содержимого страниц.

#### B. Включение режима «Картинка в картинке» (`pip.js`)
- **Запуск только по запросу:** `pip.js` **не присутствует** на страницах на постоянной основе. Он внедряется в активную вкладку **только** в момент клика по иконке PiPClick на панели инструментов или при нажатии сочетания клавиш.
- **Принцип действия:** Скрипт находит видеоэлементы на текущей странице (включая элементы внутри открытых Shadow DOM деревьев), отдаёт приоритет воспроизводимому видео или видео с наибольшей видимой площадью, снимает ограничение `disablePictureInPicture` и активирует режим Picture-in-Picture.
- **Мгновенное завершение:** Сразу после переключения режима выполнение скрипта прекращается. Никакая информация о странице или видео не сохраняется и не передаётся.

### 4. Сторонние сервисы
PiPClick не подключает сторонние сервисы, библиотеки, фреймворки сбора метрик или внешние серверы.

### 5. Защита конфиденциальности детей
Поскольку PiPClick не осуществляет сбор каких-либо данных, приложение не собирает персональную информацию ни у кого, включая несовершеннолетних пользователей.

### 6. Изменения политики конфиденциальности
В случае обновления настоящей Политики конфиденциальности актуальная версия будет размещена по этому адресу с указанием даты обновления. Поскольку архитектура PiPClick изначально основана на отказе от сбора данных, базовый принцип нулевого сбора данных останется неизменным.

### 7. Контакты и исходный код
С вопросами об этой политике или за помощью обращайтесь через GitHub:

- **Обращения и вопросы (GitHub Issues):** [https://github.com/Puhavik/PiPClick-site/issues](https://github.com/Puhavik/PiPClick-site/issues)

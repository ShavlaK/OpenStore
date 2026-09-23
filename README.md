# ⚡ Open Store (macOS & Windows)

<p align="center">
  <img src="https://img.shields.io/badge/Платформа-macOS%2012.0%2B%20%7C%20Windows%2010%2F11-blue?style=flat-square" />
  <img src="https://img.shields.io/badge/Архитектура-Apple%20Silicon%20%7C%20Intel%20%7C%20Windows%20x64-purple?style=flat-square" />
  <img src="https://img.shields.io/badge/Стек-SwiftUI%20%7C%20.NET%208%20WPF-orange?style=flat-square" />
  <img src="https://img.shields.io/badge/Версия-v1.6.8-success?style=flat-square" />
  <img src="https://img.shields.io/badge/Лицензия-MIT-green?style=flat-square" />
</p>

---

**Open Store** — инструмент для компьютеров на macOS и Windows, позволяющий находить, скачивать и устанавливать на iPhone и iPad приложения, удалённые из российского App Store (Сбербанк, Т-Банк, Альфа-Банк, ВТБ, ВКонтакте, 2ГИС и другие).

Приложение работает напрямую с серверами Apple: находит купленные ранее приложения в истории покупок вашего Apple ID, скачивает официальный зашифрованный установочный файл с подписью FairPlay DRM и устанавливает его на устройство по кабелю.

Никаких самоподписанных сертификатов, сгорающих через 7 дней, и никакого джейлбрейка: приложения работают точно так же, как установленные из официального App Store.

---

## 🛠 Возможности

* **Прямая загрузка из App Store:** Вход по вашему Apple ID (включая двухфакторную аутентификацию 2FA), просмотр списка покупок и загрузка оригинальных `.ipa` файлов с серверов Apple.
* **Установка на устройство:** Прямая передача и установка приложений на подключенный по USB iPhone или iPad без сторонних утилит и без обязательной установки iTunes.
* **Локальная библиотека IPA:** Каталог уже загруженных приложений на вашем компьютере с возможностью импортировать внешние `.ipa`, удалять или ставить пачкой в один клик.
* **Кроссплатформенность:**
  * **macOS:** Нативное приложение на Swift 6 и SwiftUI с поддержкой Apple Silicon (M1–M4) и процессоров Intel.
  * **Windows:** Нативное приложение на C# (.NET 8 WPF) в стиле Windows 11 с автоматической настройкой служб Apple Mobile Device.
* **Очередь задач:** Фоновое выполнение загрузок и установок с отображением реального прогресса и статусов.

---

## 🖥 Системные требования

* **macOS:** 12.0 Monterey, 13 Ventura, 14 Sonoma, 15 Sequoia или новее.
* **Windows:** Windows 10 / 11 (64-бит).
* **Устройства:** iPhone, iPad или iPod touch с iOS 12.0 и новее.

---

## 📦 Быстрый старт

### macOS
1. Скачайте `.dmg` из раздела [Releases](https://github.com/ShavlaK/OpenStore/releases):
   * `OpenStore-v1.6.8-Mac-AppleSilicon.dmg` — для Mac с чипами M1, M2, M3, M4.
   * `OpenStore-v1.6.8-Mac-Intel.dmg` — для Mac с процессорами Intel.
2. Перетащите `Open Store.app` в папку «Программы» (`Applications`).
3. При первом запуске: правый клик по иконке → **«Открыть»** (для подтверждения в Gatekeeper).

### Windows
1. Скачайте архив `OpenStore-v1.6.8-Windows-x64.zip` (или установщик `OpenStore_Setup_v1.6.8.exe`) из раздела [Releases](https://github.com/ShavlaK/OpenStore/releases).
2. Распакуйте архив и запустите `OpenStore.exe`.
3. Если службы Apple не найдены в системе, приложение предложит настроить драйверы автоматически.

---

## 🏗 Архитектура проекта

```text
OpenStore/
├── native_app/                 # Клиент macOS (Swift 6 / SwiftUI)
│   ├── App.swift               # Точка входа, жизненный цикл, фоновые задачи
│   ├── ConfiguratorEngine.swift# Координация загрузок, работы с устройствами и сессиями
│   └── ContentView.swift       # Главный интерфейс, навигация, боковая панель
├── OpenStore_Windows_Native/   # Клиент Windows (C# .NET 8 WPF)
│   ├── MainWindow.xaml         # Основное окно приложения
│   ├── Views/                  # Вкладки: Покупки, Библиотека, Устройства, Настройки
│   └── Services/               # Движок устройств, загрузок и сессий
├── tools/                      # Низкоуровневые сервисные компоненты
│   ├── ipatool-core/           # Модуль работы с API App Store (на базе ipatool)
│   └── ios-scanner/            # Модуль взаимодействия с устройствами iOS (на базе go-ios)
├── build_app.sh                # Скрипт сборки macOS-бандлов
└── release_pack.sh             # Подготовка релизных архивов и DMG
```

---

## ❓ Часто задаваемые вопросы

<details>
<summary><b>Почему установленное приложение вылетает при запуске?</b></summary>
<br>
Все приложения из App Store защищены FairPlay DRM и зашифрованы ключом вашей учетной записи. На iPhone в настройках App Store должен быть выполнен вход в тот же Apple ID, с которого приложение скачивалось в Open Store.
</details>

<details>
<summary><b>Безопасно ли вводить пароль Apple ID?</b></summary>
<br>
Да. Авторизация происходит напрямую через официальные эндпоинты Apple (GrandSlam / StoreKit). Пароль и токены сессии сохраняются только локально на вашем компьютере (в Keychain на macOS или защищённом локальном хранилище на Windows). Никакие данные не передаются третьим лицам.
</details>

<details>
<summary><b>Можно ли установить приложение, если его никогда не было на моем Apple ID?</b></summary>
<br>
Если приложение уже удалено из App Store и вы никогда не скачивали его на свой текущий Apple ID, то сервер Apple не отдаст лицензию для вашего аккаунта. В этом случае приложение можно установить через другой аккаунт (например, рабочий или аккаунт знакомого), где эта покупка есть в истории.
</details>

---

## 🤝 Благодарности и Open Source компоненты

В основе низкоуровневого взаимодействия Open Store лежат замечательные проекты сообщества:

* **[ipatool](https://github.com/majd/ipatool)** (автор **Majd Alfhaily**) — инструмент для работы с API магазина Apple и скачивания IPA-пакетов.
* **[go-ios](https://github.com/danielpaulus/go-ios)** (автор **Daniel Paulus**) — набор инструментов на Go для связи с iOS-устройствами по USB через протокол usbmuxd.
* **[go-plist](https://github.com/DHowett/go-plist)** (автор **Dustin L. Howett**) — библиотека работы с форматом Apple Property List.

Полные тексты лицензий сторонних компонентов приведены в файле [THIRD_PARTY_LICENSES.md](THIRD_PARTY_LICENSES.md).

---

## 📄 Лицензия

Исходный код и интерфейс Open Store распространяются под лицензией **MIT**. Подробности в файле [LICENSE](LICENSE).

# Лицензии сторонних компонентов (Third-Party Licenses & Notices)

Проект **Open Store** использует компоненты и наработки проектов с открытым исходным кодом. Мы выражаем искреннюю благодарность их авторам и сообществу за огромный вклад в исследование протоколов Apple и разработку открытых инструментов.

В соответствии с условиями лицензий ниже приводятся сведения об используемом программном обеспечении и полные тексты их лицензий.

---

## 1. ipatool
* **Репозиторий:** [https://github.com/majd/ipatool](https://github.com/majd/ipatool)
* **Автор:** Majd Alfhaily
* **Назначение:** Взаимодействие с API Apple StoreKit и iTunes Store (поиск, авторизация учетной записи, получение официальных зашифрованных пакетов FairPlay DRM).
* **Лицензия:** MIT License

```text
MIT License

Copyright (c) 2021 Majd Alfhaily

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 2. go-ios
* **Репозиторий:** [https://github.com/danielpaulus/go-ios](https://github.com/danielpaulus/go-ios)
* **Автор:** Daniel Paulus
* **Назначение:** Низкоуровневое взаимодействие с iOS-устройствами по USB через протокол usbmuxd (обнаружение устройств, опрос сервисов lockdownd, установка IPA-пакетов через installation_proxy).
* **Лицензия:** MIT License

```text
MIT License

Copyright (c) Daniel Paulus

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 3. plist (go-plist)
* **Репозиторий:** [https://github.com/DHowett/go-plist](https://github.com/DHowett/go-plist)
* **Автор:** Dustin L. Howett
* **Назначение:** Парсинг бинарных и XML файлов свойств Apple Property List (plist).
* **Лицензия:** 2-Clause BSD License

```text
Copyright (c) 2013-2020 Dustin L. Howett

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this
  list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice,
  this list of conditions and the following disclaimer in the documentation
  and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

---

## Архитектура и лицензирование Open Store

* **Оболочка и логика Open Store:** Графические интерфейсы (macOS SwiftUI, Windows WPF .NET 8), очереди фоновых задач, кэширование каталогов и иконок, инсталлятор и логика сопряжения разработаны командой Open Store и распространяются под лицензией MIT (см. [LICENSE](LICENSE)).
* **Низкоуровневые утилиты:** Для сетевого обмена с магазином и работы с устройствами используются вышеуказанные открытые библиотеки. Лицензия MIT прямо допускает включение таких компонентов в состав других проектов при сохранении оригинальных копирайтов и текстов лицензий.

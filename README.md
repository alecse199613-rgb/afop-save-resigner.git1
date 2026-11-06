# Avatar: Frontiers of Pandora — Save Toolkit

Author: **MountainousLeif**

GUI-инструмент в стиле оригинального «Far Cry 6 — Save Toolkit» для переноса
сохранений Avatar: Frontiers of Pandora между аккаунтами Goldberg UplayEmu.

![Menu](assets/mockup_menu.png)

## Что делает
- Находит сохранения в `%APPDATA%\Goldberg UplayEmu Saves\4740`
- Заменяет UUID исходного аккаунта (`5a7f3c48-6ad0-49fc-906b-18c138c7b514`)
  на UUID вашего аккаунта во всех `.save` файлах (строковый вид, raw big-endian,
  little-endian GUID-раскладка, base64 — все известные варианты представления)
- Создает резервную копию `*.save.bak` перед каждой правкой

## Сборка
```bash
cargo build --release
# exe: target/release/avatar-fop-save-toolkit.exe
```

## Автосборка
GitHub Actions workflow `.github/workflows/build.yml` собирает exe и zip
при каждом пуше в `main`. Готовый zip лежит в **Actions → Artifacts**.

## Дисклеймер
Инструмент работает только с вашими локальными файлами сохранений.
Насколько корректно игра прочитает перезаписанный сейв — зависит от версии игры;
всегда держите резервные копии.

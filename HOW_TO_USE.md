# Как пользоваться

1. Скачайте готовый `Avatar-FoP-Save-Toolkit-win64.zip` (или соберите сами через `cargo build --release`).
2. Распакуйте и запустите `AvatarFoPSaveToolkit.exe`.
3. В поле **Save File or Folder** укажите:
   `%APPDATA%\Goldberg UplayEmu Saves\4740`
   (кнопка "Open save folder (%APPDATA%)" откроет нужную папку сразу).
4. **Source Account** уже заполнен UUID `5a7f3c48-6ad0-49fc-906b-18c138c7b514`
   — это UUID аккаунта, от которого сделано скачанное сохранение
   (источник: playground.ru, сохранение "максимальная прокачка, почти вся карта").
5. В **Target Account** вставьте UUID своего аккаунта:
   - его видно в логе Goldberg (файл `steam_settings/GLOBAL_SETTINGS_FILES/user_steam_id.txt`
     или в логах эмуляции Uplay при запуске игры), либо возьмите из вашего
     рабочего сохранения: UUID встречается в `.save` в текстовом виде;
   - UUID должен быть формата `8-4-4-4-12` hex.
6. Нажмите **Resign Save(s)**.
7. Запустите игру и проверьте загрузку сохранения.

## Если сейв не подхватился
- Убедитесь, что файлы лежат именно в `...\Goldberg UplayEmu Saves\4740`.
- Попробуйте снять галочку "Auto try known candidate IDs" — тогда меняется
  только raw big-endian вариант UUID (иногда лишние замены ломают хеш).
- Проверьте `.bak` файлы: оригинал всегда сохраняется рядом.
- Если игра сама создает новый UUID в заголовке — сравните его с вашим
  Target UUID и сообщите автору (MountainousLeif).

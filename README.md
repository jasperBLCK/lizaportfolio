# KEC — портфолио

Статичный сайт на GitHub Pages (домен kec-design.ru).

- `index.html` — сам сайт, весь контент подтягивает из `content.json`
- `content.json` — тексты, работы, услуги и цены, контакты
- `admin.html` — админка: правит `content.json` и грузит фото прямо в репозиторий через GitHub API
- `assets/works/`, `assets/uploads/` — изображения

## Как пользоваться админкой

1. Открыть `https://kec-design.ru/admin.html`
2. Вставить GitHub fine-grained токен:
   - [создать токен](https://github.com/settings/personal-access-tokens/new)
   - Repository access → Only select repositories → `lizaportfolio`
   - Permissions → Repository permissions → **Contents: Read and write**
3. Выбрать в шапке ветку — ту же, из которой публикуется сайт (Settings → Pages → Build and deployment → Branch).
4. Отредактировать контент во вкладках и нажать «Сохранить и опубликовать».
   Изменения уходят коммитом в выбранную ветку; после сохранения админка сама
   проверяет опубликованный `content.json` и пишет «Опубликовано», когда сайт обновился
   (обычно 1–2 минуты). Если ветка админки и ветка Pages разные, появится предупреждение.

Токен хранится только в localStorage браузера и отправляется исключительно на `api.github.com`.
Кнопка «Предпросмотр» открывает сайт с текущими несохранёнными правками.

Загружаемые фото автоматически сжимаются до 1800px по длинной стороне (JPEG, q=0.85).

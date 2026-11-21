# Настольные игры. Простые стратегии и их пределы

Черновик исследования в Quarto. Начальная страница — `index.qmd`. Блокноты в `chapters/` открываются в VS Code или Juno. `next-games.qmd` хранит план следующей главы. Quarto собирает меню и список глав на главной из файлов `chapters/*.ipynb`.

## Первая публикация

1. Распакуй архив и открой папку `board-game-strategies` в VS Code. Для выполнения ячеек на Mac выбери ядро Conda `base`.
2. Создай на GitHub пустой публичный репозиторий `board-game-strategies`. Оставь README, `.gitignore` и лицензию выключенными. [Создать репозиторий](https://github.com/new).
3. Открой терминал в распакованной папке проекта и выполни:

   ```bash
   git init -b main
   git add -- .gitignore README.md _quarto.yml index.qmd chapters _templates next-games.qmd
   git commit -m "Добавил заготовку исследования"
   git remote add origin git@github.com:Ivanbsp-coder/board-game-strategies.git
   git push -u origin main
   ```

   Если выбрал другое имя репозитория, возьми его SSH-адрес на GitHub через **Code → SSH**.
4. В репозитории выбери **Settings → Pages → Build and deployment → Source → GitHub Actions**. [Документация GitHub](https://docs.github.com/ru/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).
5. Отправь готовую настройку автоматической сборки:

   ```bash
   git add -- .github/workflows/publish.yml
   git commit -m "Настроил публикацию сайта"
   git push
   ```

6. На вкладке **Actions** дождись успешного запуска **Publish Quarto site** и открой сайт через **Settings → Pages → Visit site**.

## Дальнейшая работа

- Перед правками на другом Mac сделай `git pull --ff-only`, на iPhone — **Pull** в Working Copy. Затем открой нужный блокнот.
- Перед коммитом с новыми вычислениями выполни ячейки и сохрани `.ipynb`. При публикации Quarto берёт сохранённый вывод. [Документация Quarto](https://quarto.org/docs/tools/jupyter-lab.html#cell-execution).
- Для локального просмотра при установленном Quarto запусти `quarto preview` в папке проекта. На GitHub Quarto устанавливается автоматически сценарием сборки. [Предпросмотр сайта](https://quarto.org/docs/websites/#website-preview).

## Новая игра или отдельный контрпример

1. Скопируй `_templates/chapter.ipynb` в `chapters/` под новым именем. Используй латиницу и дефисы в имени файла.
2. В первой ячейке Raw измени `title`, `description` и `order`. Крестики-нолики имеют порядок `10`, шашки — `20`. Следующей главе можно дать `30`, а вставке между ними — `15`.
3. Заполни разделы блокнота. Для опровержения укажи исходное утверждение, допустимую позицию, предписанный правилом ход и ответ, который опровергает утверждение. Для сравнения по выборке опиши соперников и способ отбора позиций.
4. Когда глава готова к публикации, добавь её файл в коммит и отправь в `main`. Сборка подхватит его из `chapters/`.

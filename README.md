# NeutrinoOS — корпоративный сайт

Одностраничный сайт продукта NeutrinoOS для компании Mikelsoft Corporation INC.
Размещается на GitHub Pages.

## Состав

```

neutrino-os-site/
├── index.html          Главная страница
├── style.css           Стили
├── screenshots/        Каталог изображений (создать вручную)
│   ├── boot.png
│   ├── shell.png
│   ├── gui.png
│   ├── fetch.png
│   ├── snake.png
│   ├── tetris.png
│   ├── editor.png
│   └── matrix.png
├── .gitignore
└── README.md

```

## Размещение изображений

1. Создайте каталог:
```

mkdir screenshots

```

2. Получите снимки экрана NeutrinoOS. Предпочтительный способ — средствами QEMU:

Запустите систему:
```

./run.sh

```

Доведите интерфейс до нужного состояния. Затем нажмите `Ctrl+Alt+2`,
чтобы переключиться на консоль QEMU, и введите:
```

screendump boot.ppm

```
Вернитесь в окно системы: `Ctrl+Alt+1`.

Преобразуйте файл в PNG:
```

convert boot.ppm boot.png

```
либо
```

pnmtopng boot.ppm > boot.png

```

Допустимо использование обычных средств создания снимков экрана
операционной системы, однако в этом случае в кадр попадёт окно
эмулятора.

3. Поместите файлы в каталог `screenshots/` со следующими именами:

| Файл         | Содержание               |
|--------------|--------------------------|
| boot.png     | Экран загрузки           |
| shell.png    | Командная оболочка       |
| gui.png      | Файловый менеджер        |
| fetch.png    | Вывод команды FETCH      |
| snake.png    | Игра SNAKE               |
| tetris.png   | Игра TETRIS              |
| editor.png   | Текстовый редактор       |
| matrix.png   | Скринсейвер Matrix       |

Если файл отсутствует, на его месте отображается заглушка
с именем и назначением. Дополнительных правок не требуется.

## Публикация на GitHub Pages

### Способ 1. Через веб-интерфейс

1. Создайте репозиторий на GitHub с именем `neutrino-os`, тип — Public.
2. Откройте репозиторий, выберите «Add file» → «Upload files».
3. Перенесите `index.html`, `style.css`, `README.md`, `.gitignore`
и каталог `screenshots/` с изображениями.
4. Подтвердите изменения кнопкой «Commit changes».
5. Перейдите в «Settings» → «Pages».
6. В разделе «Source» выберите «Deploy from a branch».
7. В разделе «Branch» укажите `main` и каталог `/(root)`, нажмите «Save».
8. Через 1–2 минуты сайт будет доступен по адресу:
`https://ИМЯ_ПОЛЬЗОВАТЕЛЯ.github.io/neutrino-os/`

### Способ 2. Через систему контроля версий

```

git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/ИМЯ_ПОЛЬЗОВАТЕЛЯ/neutrino-os.git
git push -u origin main

```

Далее выполните шаги 5–8 из первого способа.

## Обновление содержимого

```

git add .
git commit -m "Update"
git push

```

GitHub Pages пересоберёт сайт автоматически в течение одной минуты.

## Правка содержимого

- Цвета интерфейса заданы переменными в начале `style.css`.
- Тексты, ссылки и структура разделов находятся в `index.html`.
- Замените `ВАШ_НИК` на имя вашей учётной записи GitHub
  в трёх местах: навигация, раздел загрузки, подвал.

## Лицензия

MIT.

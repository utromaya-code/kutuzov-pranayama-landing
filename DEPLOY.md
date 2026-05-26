# Деплой на GitHub Pages

## 1. Создать репозиторий

1. Открыть [github.com/new](https://github.com/new).
2. Имя репозитория: **`kutuzov-pranayama-landing`**.
3. Описание (по желанию): `Лендинг курса «Нейрофизиология пранаямы» — Neuro-Universe / Леонид Кутузов`.
4. Видимость: **Public** (необходимо для бесплатного GitHub Pages).
5. **Не** добавлять README, .gitignore и лицензию — они уже в папке проекта.
6. Нажать **Create repository**.

## 2. Запушить проект из локальной папки

```bash
cd "/Users/poslednijgeroj/Library/Mobile Documents/com~apple~CloudDocs/kutuzov-pranayama-landing"

git init
git add .
git commit -m "Лендинг курса «Нейрофизиология пранаямы»"
git branch -M main
git remote add origin https://github.com/utromaya-code/kutuzov-pranayama-landing.git
git push -u origin main
```

При запросе пароля используйте **Personal Access Token** (вкладка Settings → Developer settings → Personal access tokens на GitHub), а не пароль от аккаунта.

## 3. Включить GitHub Pages

В репозитории на GitHub: **Settings → Pages**.

- Source: **Deploy from a branch**
- Branch: **main**, folder **/ (root)**
- Save

Через 1–3 минуты страница будет доступна по адресу:

**https://utromaya-code.github.io/kutuzov-pranayama-landing/**

## 4. Дальнейшие обновления

```bash
cd "/Users/poslednijgeroj/Library/Mobile Documents/com~apple~CloudDocs/kutuzov-pranayama-landing"

# править файлы…

git add .
git commit -m "Краткое описание правки"
git push
```

GitHub Pages автоматически пересобирает страницу через 30–90 секунд после пуша.

## 5. Подключение собственного домена (опционально)

Если позже потребуется привязать поддомен `pranayama.neuro-universe.ru`:

1. В корне репозитория создать файл `CNAME` с одной строкой: `pranayama.neuro-universe.ru`.
2. У регистратора домена `neuro-universe.ru` добавить CNAME-запись:
   - Имя: `pranayama`
   - Значение: `utromaya-code.github.io`
3. В **Settings → Pages → Custom domain** указать `pranayama.neuro-universe.ru` и включить **Enforce HTTPS**.

После распространения DNS (от нескольких минут до 24 часов) лендинг будет доступен и по своему URL, и по адресу GitHub Pages.

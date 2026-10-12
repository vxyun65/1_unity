# 1_unity — СКВ в игровом движке Unity

![CI](https://github.com/vxyun65/1_unity/actions/workflows/main.yml/badge.svg)

Учебный проект по лабораторной работе №1 дисциплины «Основы профессиональной деятельности» (ИТМО, Школа разработки видеоигр).

Основа — шаблон **Simple 2D Template** (Indie Marc) из Unity Asset Store. В сцене TopDown добавлены пол, стены, освещение, препятствия и объекты взаимодействия. На проекте отрабатывались работа в ветках, разрешение конфликтов слияния в сценах Unity, CI/CD на GitHub Actions и учёт ошибок в Issues.

## Команда

Работа выполнена одним студентом, роли выполнялись поочерёдно.

| Роль | Аккаунт | Что сделано |
|---|---|---|
| Сеньор | @vxyun65 | правила веток и коммитов, репозиторий, игровые объекты, слияние веток и разрешение конфликта сцены |
| Джуниор | @vior843 | проект Unity, `.gitignore`, первый коммит, пол, стены и освещение |
| Девопс | @vxyun65 | GitHub Actions и секреты, Issues, README |

## Как открыть проект

1. Установите Unity Hub и Unity **2022.3.22f1** (нужна именно эта версия).
2. Клонируйте репозиторий:
   ```bash
   git clone https://github.com/vxyun65/1_unity.git
   ```
3. Unity Hub → **Add → Add project from disk** → папка репозитория. Первое открытие займёт несколько минут: Unity создаёт папку Library.
4. Откройте сцену `Assets/IndieMarc/TopDownDemo/TopDownDemo.unity` и нажмите ▶.

## Готовая сборка

**Actions** → последний успешный запуск **Test and Build Project** → раздел **Artifacts** → `Build-StandaloneWindows64`. Распакуйте архив и запустите `.exe`.

## CI/CD

Workflow `.github/workflows/main.yml` запускается вручную: **Actions → Test and Build Project → Run workflow**.

1. **Test in playmode / Test in editmode** — тесты Unity Test Framework (`game-ci/unity-test-runner`).
2. **Build for StandaloneWindows64** — сборка под Windows (`game-ci/unity-builder`), результат сохраняется как артефакт.

Для работы нужны секреты репозитория `UNITY_EMAIL`, `UNITY_PASSWORD` и `UNITY_LICENSE`.

## Правила работы с репозиторием

- Ветки тематические: `feature/…`, `fix/…`, `ci/…`, `docs/…`. В `main` изменения попадают через pull request.
- Коммиты на английском в формате Conventional Commits (`feat:`, `fix:`, `ci:`, `docs:`, `chore:`), атомарные.
- Команда работает с частью TopDown. Папка `PlatformerDemo` исключена из СКВ через `.gitignore`.

## История изменений

| № | Что сделано |
|---|---|
| #1 | Пол, стены и освещение сцены TopDown (Джуниор) |
| #2 | Препятствия и объекты взаимодействия, разрешение конфликта сцены (Сеньор) |
| #3 | Права для публикации результатов тестов в Actions |
| #4 | Баг: сборка падала из-за исключённой сцены PlatformerDemo в Build Settings |
| #5 | Сцена PlatformerDemo удалена из Build Settings, баг #4 закрыт |

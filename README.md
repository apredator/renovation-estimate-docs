# Документы приложения «Смета ремонта»

Публичный репозиторий с обязательными для App Store страницами:

- `PRIVACY_POLICY.html` — Privacy Policy URL;
- `SUPPORT.html` — Support URL.

Страницы собраны из Markdown-источников в приватном репозитории приложения
(`docs/*.md` → `scripts/build-docs-site.mjs`) и лежат здесь готовым статическим
сайтом. Никакой сборки при публикации не требуется: GitHub Pages отдаёт файлы как есть.

## Как включить

1. Создать **публичный** репозиторий, например `renovation-estimate-docs`.
2. Запушить в него ветку `main` с этими файлами.
3. GitHub → **Settings → Pages → Source: Deploy from a branch → main / (root)**.
4. Проверить адреса:

```bash
curl -sS -o /dev/null -w "%{http_code}\n" https://<логин>.github.io/renovation-estimate-docs/PRIVACY_POLICY.html
curl -sS -o /dev/null -w "%{http_code}\n" https://<логин>.github.io/renovation-estimate-docs/SUPPORT.html
```

Адреса вставляются в App Store Connect в поля **Privacy Policy URL** и **Support URL**.

> Файл `.nojekyll` отключает обработку Jekyll, чтобы страницы отдавались ровно так,
> как они собраны.

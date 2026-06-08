# samples-1c-platform

Минимальные образцы артефактов **1С:Предприятие** с **значениями по умолчанию** платформы (как у только что созданного объекта). Это **ориентир по схеме выгрузки (Designer XML) и дефолтам новых объектов**, а не готовая прикладная конфигурация. Используются как эталоны (golden) в тестах и scaffold [`md-sparrow`](https://github.com/yellow-hammer/md-sparrow).

## Структура

- **`snapshots/<версия>/`** — эталоны по версиям формата выгрузки (`2.10`…`2.21`):
  - `cf-bare-objects/` — по одному **голому** объекту каждого вида (источник для scaffold в `md-sparrow`);
  - `external-files/empty/` — голые внешний отчёт и обработка;
  - `external-files/empty-full-objects/` — образцы заполненных внешних объектов (есть не для всех версий).
- **`seed/src/cf`** — «семя» (по одному голому объекту каждого вида, формат 2.20), из которого workflow `md-sparrow` генерирует `cf-bare-objects` для всех версий.

Подробнее о роли эталонов — `md-sparrow`: [docs/scaffold-golden.md](https://github.com/yellow-hammer/md-sparrow/blob/main/docs/scaffold-golden.md).

## Для разработчиков

Если вы хотите внести вклад в проект, ознакомьтесь с [документацией для разработчиков](CONTRIBUTING.md).

## Лицензия

MIT License. Подробности см. в файле [LICENSE](LICENSE).

## Автор

Ivan Karlo (<i.karlo@outlook.com>)

При желании, отблагодарить автора можно по ссылке:

- [Boosty](https://boosty.to/1carlo/donate)
- [Чаевые](https://pay.cloudtips.ru/p/d752cb43)

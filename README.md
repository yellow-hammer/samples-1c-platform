# samples-1c-platform

Минимальные образцы артефактов **1С:Предприятие** с **значениями по умолчанию** платформы (как у только что созданного объекта). Это **ориентир по схеме выгрузки (Designer XML) и дефолтам новых объектов**, а не готовая прикладная конфигурация. Используются как эталоны (golden) в тестах и scaffold [`md-sparrow`](https://github.com/yellow-hammer/md-sparrow).

## Структура

- **`snapshots/<версия>/`** — эталоны по версиям формата выгрузки (`2.10`…`2.21`). Каждый файл записала сама платформа этой версии:
  - `cf-bare-objects/` — по одному **голому** объекту каждого вида, `Configuration.xml`, язык и права роли;
  - `cf-object-nodes/` — объект-владелец каждого вида с дочерним узлом каждого вида: реквизит, табличная часть, команда, измерение, ресурс… (эталон узлов для `md-sparrow`);
  - `cf-empty-infobase/` — конфигурация новой пустой информационной базы;
  - `cfe-empty/` — пустое расширение. С 2.13 его создаёт сама платформа (`ibcmd infobase config extension create`); у `ibcmd` 8.3.17–8.3.19 (2.10–2.12) этой команды нет, поэтому расширение загружается из минимального семени (`config import --extension`), а всё, чего в семени нет, дописывает и выгружает платформа;
  - `external-files/empty/` — голые внешний отчёт и обработка;
  - `external-files/empty-full-objects/` — внешние отчёт и обработка с формами и модулями.

Эталоны снимает с платформы нужной версии инструмент [`tools/golden-snapshots`](https://github.com/yellow-hammer/md-sparrow/tree/main/tools/golden-snapshots) из `md-sparrow` (локально или workflow `golden-snapshots` на CI) через `ibcmd`, без конфигуратора; семя — там же. Все каталоги есть у всех форматов, кроме `external-files/`: `ibcmd` платформ до 8.3.23 внешние объекты не собирает, поэтому они есть с 2.16. Перекодированных из другого формата файлов здесь нет.

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

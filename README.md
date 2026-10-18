# Аналитика каталога стримингового сервиса

Домашнее задание №1. Mushkarev, группа М26-555.

Имя репозитория: `dz-catalog-analysis_Mushkarev_M26-555`.

Все исходные данные и функции девяти этапов находятся в `catalog_analysis.py`.
Программа формирует отчет по каталогу из десяти фильмов: средний рейтинг,
средний возраст, топ-3, количество фильмов по жанрам и список уникальных жанров.
Исходные названия фильмов сохраняются; для отчета они нормализуются.

Для работы нужны Python 3.12 и uv версии 0.5 или выше.
Единственная зависимость проекта — Ruff 0.12.1 для разработки.

```bash
uv sync
uv run catalog_analysis.py
uv run ruff check .
```

`build_report(movies)` вызывается в блоке `if __name__ == "__main__":`.
При импорте файла отчет не печатается.

Дополнительные задания по циклам можно проверить в интерактивной оболочке:

```python
from catalog_analysis import (
    above_average_ratings,
    find_first_masterpiece,
    movies,
    print_high_rated_movies,
    print_non_comedy_movies,
    total_high_rated_duration,
)

print_non_comedy_movies(movies)
find_first_masterpiece(movies)
find_first_masterpiece([movie for movie in movies if movie["rating"] <= 9.0])
above_average_ratings(movies)
print_high_rated_movies(movies)
total_high_rated_duration(movies)
```

При отсутствии фильма с рейтингом выше 9.0 функция поиска печатает
`Шедевров не найдено`. Суммарная длительность фильмов с рейтингом выше 7 — 713 минут.

Для сдачи требуется ссылка на git-репозиторий с файлами `catalog_analysis.py`,
`pyproject.toml`, `uv.lock`, `README.md`, `.gitignore` и `.python-version`.
Виртуальное окружение `.venv` в репозиторий не включается.

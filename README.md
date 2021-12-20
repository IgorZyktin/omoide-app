# omoide-app

[![Build Status](https://github.com/IgorZyktin/omoide-app/workflows/test/badge.svg?branch=master&event=push)](https://github.com/IgorZyktin/omoide-app/actions?query=workflow%3Atest)
[![codecov](https://codecov.io/gh/IgorZyktin/omoide-app/branch/master/graph/badge.svg)](https://codecov.io/gh/IgorZyktin/omoide-app)
[![Python Version](https://img.shields.io/pypi/pyversions/omoide-app.svg)](https://pypi.org/project/omoide-app/)
[![wemake-python-styleguide](https://img.shields.io/badge/style-wemake-000000.svg)](https://github.com/wemake-services/wemake-python-styleguide)

Главное приложение проекта [Omoide](https://omoide.ru).

## Что делает

Выступает фасадом для пользователей, демонстрируя им картинки. Обычное web
приложение с базой данных, формами и прочими стандартными атрибутами.

## Установка и запуск

TODO - Описать как запускать контейнер.

## Как работает

В качестве web фреймворка взят `Flask`, управление процессами сервера через
`Gunicorn`. База данных `PostgreSQL` с коннектором `psycopg2` и ORM
`SQLAlchemy`. Отдача статики осуществляется через `NGINX`. Из-за скудных
вычислительных мощностей сервера системы кеширования нет, а так был бы `Redis`.
Работа протестирована `pytest`.

## Основные эндпоинты сервера

### / и /search

Исходный поиск картинок и вывод результатов.

### /login и /logout

Вход и выход пользователя с сайта.

### /show/{uuid}

Предварительный просмотр. Обычно это демонстрация контента среднего качества с
выводом всех подробностей о записи.

### /thumbnail/{filename}

Просмотр контента в минимальном качестве.

### /preview/{filename}

Просмотр контента в среднем качестве.

### /content/{filename}

Просмотр контента в оригинальном качестве.

### /browse/{uuid}

Просмотр коллекции. Если uuid принадлежит единичной записи, происходит
переадресация на /preview.

### /newest

Перечень последних добавленных и доступных для просмотра материалов.

### /feedback

Страница с формой обратной связи.

### /help

Страница с инструкцией к сайту.

### /tags

Страница с перечнем всех доступных для просмотра тегов.

### /home

Домашняя страница пользователя. Здесь можно изменить имя и отображаемый логин.

### /navigation

Здесь можно настроить отображаемые записи. Для зарегистрированных пользователей
они хранятся в базе данных, а для анонимных - в кукисах.

## License

[MIT](https://github.com/IgorZyktin/omoide-app/blob/master/LICENSE)

## Credits

This project was generated with [`wemake-python-package`](https://github.com/wemake-services/wemake-python-package). Current template version is: [ae56f52f9ddf81e9910e487ba73995ef10ba880e](https://github.com/wemake-services/wemake-python-package/tree/ae56f52f9ddf81e9910e487ba73995ef10ba880e). See what is [updated](https://github.com/wemake-services/wemake-python-package/compare/ae56f52f9ddf81e9910e487ba73995ef10ba880e...master) since then.

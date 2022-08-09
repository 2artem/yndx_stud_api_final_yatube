# API_final_yatube

Данный API предоставляет возможность получения публикаций блога в формате json c возможностью создания и редактирования собственных публикаций пользователями, а так же такой же функционал для комментариев прикрепленных к публикациям.
Публикации могут быть прикреплены к Сообществам, список которых так же можно просмотреть при помощи API.

> Регистрация пользователей для работы с API производиться через административную панель. Авторизованные пользователи имеют возможность смотреть и редактировать свои публикации, комментарии и подписки. Доступ к API производится посредством применения токена. Не авторизованные пользователи могут только просматривать контент, но не могут подписываться на авторов.

### Документация API
По адресу http://127.0.0.1:8000/redoc/ будет доступна документация для API Yatube в формате Redoc.

### Пример обработки запроса
Получение публикаций. При указании параметров limit и offset выдача работает с пагинацией.

Получить список всех публикаций. 
`GET http://127.0.0.1:8000/api/v1/posts/`

	{
		"count": 123,
		"next": "http://api.example.org/accounts/?offset=400&limit=100",
		"previous": "http://api.example.org/accounts/?offset=200&limit=100",
		"results": 
	[
			{
				"id": 0,
				"author": "string",
				"text": "string",
				"pub_date": "2021-10-14T20:41:29.648Z",
				"image": "string",
				"group": 0
			}
		]
	}

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/2artem/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv venv
```

```
source venv/bin/activate
```

Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

Примечание: 9.

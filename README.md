# Поиск фильмов на TMDb

## make_own_db.py

### load_films

На вход принимает API ключ и количество фильмов для вашей базы данных. При помощи`make_tmdb_api_request`составляет и возвращает список фильмов. 

### if __name__ == '__main__'

Запрашивает ключ `get_user_api_key` и создаёт базу данных из фильмов полученных из `load_films`. В переменной `films_amount` можно изменить число фильмов для базы данных.

## tmdb_helpers.py

### make_tmdb_api_request

На вход принимает параметры и API ключ, добавляет параметры и создаёт ссылку для запроса. На выходе вызывает функцию ` load_json_data_from_url`и аргументы созданную ссылку и параметру (API ключ и язык русский).

### load_json_data_from_url

На вход принимает ссылку из `make_tmdb_api_request`. Делает запрос на [TMDb](https://www.themoviedb.org/movie) и возвращает ответ в формате `json.loads`.

### get_user_api_key

Просит пользователя ввести ключ.

## hello_api_TMDB.py

### if __name__ == '__main__'

Запрашивает ключ `get_user_api_key` и делает запрос о бюджете фильма по его `id`. Ответь выводит в консоле.

## own_db_helpers.py

### load_data

На вход принимает путь до базы данных. Открывает возвращает её как `json.loads`.

## search_in_db.py

### search_for_film

На вход принимает название фильма для поиска и базу данных из `load_data`. Возвращает множество с найденными фильмами.

### if __name__ == '__main__'

Просит пользователя ввести путь до базы данных и название фильма для поиска. Затем выводит результат поиска.

## find_similar.py

### find_my_film

Функции ищет похожие фильмы. На вход принимает название фильма для поиска и базу данных. В случае если находит введённый фильм, возвращает этот фильм.

### get_rating

На вход принимает фильм проверенный в `find_my_film`, базу данных и количество фильмов для вывода. Подберает фильмы из базы данных по определённым параметрам (жанр, буджет, оригинальный язык и добавлин ли фильм в избранные)и возвращает список этих фильмов.

### if __name__ == '__main__'

Просит пользователя ввести путь до базы данных и название фильма для поиска. И выводит список из `get_rating`. Если введённого фильма нет в базе данных, выводит - фильм не найден.

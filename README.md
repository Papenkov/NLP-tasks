# NLP-tasks
Задание:
Представим, что Вы готовите слайд для презентации об актуальных трендах в англоязычных новостях, касающихся России.

С сайта google news (https://news.google.com) (язык и регион - English | United States) необходимо
прокачать все статьи за последний месяц (на момент прокачки) с ключевым словом Russia.
Затем для скачанных статей необходимо рассчитать топ-50 упоминаемых тем и представить их в виде word (tag) cloud.

Данное задание необходимо выполнить с помощью Python.

Решение:
Использованные библиотеки и технологии: requests, bs4 (BeautifulSoup), Google news API, nltk (для задач NLP), WordCloud.

Замечания:
1. Для решения задачи требовалось разобраться с Google News API. Получить API key. Там сразу возникли ограничения для бесплатного пользования API (можно загрузить не более 100 статей за раз). Вариант обхода ограничения: делать запросы не за целый месяц а по дням.
2. В задании указано "прокачать все статьи за последний месяц" и далее "рассчитать топ-50 упоминаемых тем". В коде выполнено скачивание статьей и рассчет самых популярных слов из этиъ статей. Т.к. 50 тем вряд ли наберется в такой выборке (100 статей, по факту 87 {некоторые ссылки битые}). Темы статей лучше определять по заголовкам. Вариант решения: брать большую выборку, как предложено в п.1. Далее искать в интернете размеченный датасет, где заголовок статьи соотносится с темой из набора тем. Обучить Machine learning модель (например: Random Forest, XGboost и т.д.) на этом датасете предсказывать тематику статьи по ее заголовку. Далее подавать этой модели на вход заголовки новостей, которые мы собрали с Google News и модель машинного обучения предскажет тему для каждой статьи. Собрать все получившиеся тематики и построить Word Cloud. 

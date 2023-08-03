Использование API и SPARQL-интерфейсов Вики-сервисов
================
Лутай А.В.
2023-08-03

-   [API и SPARQL интерфейсы](#api-и-sparql-интерфейсы)
    -   [MediaWiki Action API](#mediawiki-action-api)
    -   [MediaWiki REST API](#mediawiki-rest-api)
    -   [Wikimedia REST API](#wikimedia-rest-api)
    -   [Wikidata API](#wikidata-api)
    -   [Wikidata SPARQL](#wikidata-sparql)
-   [Материалы на русском языке](#материалы-на-русском-языке)
-   [Типовые задачи – сведения о
    статье](#типовые-задачи--сведения-о-статье)
    -   [Информация о статье в
        Wikipedia](#информация-о-статье-в-wikipedia)
    -   [Другие названия объекта
        статьи](#другие-названия-объекта-статьи)
    -   [Все языковые версии статьи в
        Wikipedia](#все-языковые-версии-статьи-в-wikipedia)
    -   [Извлечь категории статьи](#извлечь-категории-статьи)
    -   [:pushpin: Получение изображений из
        статьи](#pushpin-получение-изображений-из-статьи)
    -   [Извлечь разделы статьи в
        Wikipedia](#извлечь-разделы-статьи-в-wikipedia)
    -   [Получить Wikidata ID по названию статьи в
        Wikipedia](#получить-wikidata-id-по-названию-статьи-в-wikipedia)
    -   [Найти страницы Wikipedia по Wikidata
        ID](#найти-страницы-wikipedia-по-wikidata-id)
    -   [Цитировать статью Wikipedia в формате
        bibtex](#цитировать-статью-wikipedia-в-формате-bibtex)
-   [Типовые задачи – поиск статей и
    изображений](#типовые-задачи--поиск-статей-и-изображений)
    -   [:pushpin: Поиск статьи по
        названию](#pushpin-поиск-статьи-по-названию)
    -   [:pushpin: Поиск изображений по
        названию](#pushpin-поиск-изображений-по-названию)
-   [Типовые задачи – правки и
    просмотры](#типовые-задачи--правки-и-просмотры)
    -   [История правок статьи в
        Wikipedia](#история-правок-статьи-в-wikipedia)
    -   [Список пользователей, которые правили
        страницу](#список-пользователей-которые-правили-страницу)
    -   [Список всех правок пользователя или с
        IP-адреса](#список-всех-правок-пользователя-или-с-ip-адреса)
    -   [Статистика просмотров страницы в
        Wikipedia](#статистика-просмотров-страницы-в-wikipedia)
    -   [Количество новых страниц в Wikipedia по
        месяцам](#количество-новых-страниц-в-wikipedia-по-месяцам)
    -   [Рейтинг редакторов по дням](#рейтинг-редакторов-по-дням)
    -   [Количество новых редакторов по
        месяцам](#количество-новых-редакторов-по-месяцам)
-   [Типовые задачи – ссылки и
    цитирования](#типовые-задачи--ссылки-и-цитирования)
    -   [Поиск статей в Wikipedia, цитирующих внешний
        web-сайт](#поиск-статей-в-wikipedia-цитирующих-внешний-web-сайт)
    -   [Поиск статей Wikipedia, цитирующих выбранную страницу
        Wikipedia](#поиск-статей-wikipedia-цитирующих-выбранную-страницу-wikipedia)
    -   [Гиперссылки из статьи Wikipedia, ведущие на другие статьи
        Wikipedia](#гиперссылки-из-статьи-wikipedia-ведущие-на-другие-статьи-wikipedia)
    -   [Ссылки на внешние сайты с выбранной страницы
        Wikipedia](#ссылки-на-внешние-сайты-с-выбранной-страницы-wikipedia)
-   [“Наукометрия” в Wikidata](#наукометрия-в-wikidata)
    -   [Все российские журналы в
        Wikidata](#все-российские-журналы-в-wikidata)
    -   [Количество статей в Wikidata в российских
        журналах](#количество-статей-в-wikidata-в-российских-журналах)
    -   [Извлечение источников заданного
        атрибута](#извлечение-источников-заданного-атрибута)
    -   [Поиск журнала по ISSN в Wikidata и импорт
        сведений](#поиск-журнала-по-issn-в-wikidata-и-импорт-сведений)
    -   [Статьи из выбранного журнала и цитирующие их
        журналы](#статьи-из-выбранного-журнала-и-цитирующие-их-журналы)
    -   [Список авторов журнала, у которых указан
        ORCID](#список-авторов-журнала-у-которых-указан-orcid)
    -   [Женщины-ученые с наградами, цитировавшие выбранный
        журнал](#женщины-ученые-с-наградами-цитировавшие-выбранный-журнал)
    -   [Российские ученые, имеющие ORCID и статью в русскоязычной
        Wikipedia](#российские-ученые-имеющие-orcid-и-статью-в-русскоязычной-wikipedia)
    -   [Исследователи младше 30 лет, имеющие статью в англоязычной
        Wikipedia](#исследователи-младше-30-лет-имеющие-статью-в-англоязычной-wikipedia)
    -   [Исследователи, цитировавшие статьи из журнала со списком
        цитирующих и процитированных
        статей](#исследователи-цитировавшие-статьи-из-журнала-со-списком-цитирующих-и-процитированных-статей)
    -   [Перечень организаций, сотрудники которых цитировали статьи из
        выбранного
        журнала](#перечень-организаций-сотрудники-которых-цитировали-статьи-из-выбранного-журнала)
    -   [Статьи из журнала и процитировавшие их организации и
        страны](#статьи-из-журнала-и-процитировавшие-их-организации-и-страны)
    -   [Карта университетов Москвы, расположенных в \<=500 метрах от
        станций
        метро](#карта-университетов-москвы-расположенных-в-500-метрах-от-станций-метро)
-   [Практика – как вносить сведения в
    Wikidata?](#практика--как-вносить-сведения-в-wikidata)
    -   [:pushpin: Quick Statements](#pushpin-quick-statements)
    -   [:pushpin: SourceMD](#pushpin-sourcemd)
-   [:pushpin: Приложение 1. Энциклопедия
    Руниверсалис](#pushpin-приложение-1-энциклопедия-руниверсалис)
    -   [Информация о статье](#информация-о-статье)
    -   [Извлечь разделы статьи](#извлечь-разделы-статьи)
    -   [Извлечь категории статьи](#извлечь-категории-статьи-1)
    -   [История правок статьи](#история-правок-статьи)
    -   [Список пользователей, которые правили
        страницу](#список-пользователей-которые-правили-страницу-1)
    -   [Список всех правок
        пользователя](#список-всех-правок-пользователя)
    -   [Поиск статей, цитирующих внешний
        web-сайт](#поиск-статей-цитирующих-внешний-web-сайт)
    -   [Поиск статей, цитирующих выбранную
        страницу](#поиск-статей-цитирующих-выбранную-страницу)
    -   [Гиперссылки из статьи, ведущие на другие статьи
        энциклопедии](#гиперссылки-из-статьи-ведущие-на-другие-статьи-энциклопедии)
    -   [Ссылки на внешние сайты с выбранной
        страницы](#ссылки-на-внешние-сайты-с-выбранной-страницы)
-   [:pushpin: Приложение 2. РУВИКИ](#pushpin-приложение-2-рувики)
    -   [Информация о статье](#информация-о-статье-1)
    -   [Извлечь разделы статьи](#извлечь-разделы-статьи-1)
    -   [Извлечь категории статьи](#извлечь-категории-статьи-2)
    -   [История правок статьи](#история-правок-статьи-1)
    -   [Список пользователей, которые правили
        страницу](#список-пользователей-которые-правили-страницу-2)
    -   [Список всех правок
        пользователя](#список-всех-правок-пользователя-1)
    -   [Поиск статей, цитирующих внешний
        web-сайт](#поиск-статей-цитирующих-внешний-web-сайт-1)
    -   [Поиск статей, цитирующих выбранную
        страницу](#поиск-статей-цитирующих-выбранную-страницу-1)
    -   [Гиперссылки из статьи, ведущие на другие статьи
        энциклопедии](#гиперссылки-из-статьи-ведущие-на-другие-статьи-энциклопедии-1)
    -   [Ссылки на внешние сайты с выбранной
        страницы](#ссылки-на-внешние-сайты-с-выбранной-страницы-1)
-   [:pushpin: Приложение 3.
    Циклопедия](#pushpin-приложение-3-циклопедия)
    -   [Информация о статье](#информация-о-статье-2)
    -   [Извлечь разделы статьи](#извлечь-разделы-статьи-2)
    -   [Извлечь категории статьи](#извлечь-категории-статьи-3)
    -   [История правок статьи](#история-правок-статьи-2)
    -   [Список пользователей, которые правили
        страницу](#список-пользователей-которые-правили-страницу-3)
    -   [Список всех правок
        пользователя](#список-всех-правок-пользователя-2)
    -   [Поиск статей, цитирующих внешний
        web-сайт](#поиск-статей-цитирующих-внешний-web-сайт-2)
    -   [Поиск статей, цитирующих выбранную
        страницу](#поиск-статей-цитирующих-выбранную-страницу-2)
    -   [Гиперссылки из статьи, ведущие на другие статьи
        энциклопедии](#гиперссылки-из-статьи-ведущие-на-другие-статьи-энциклопедии-2)
    -   [Ссылки на внешние сайты с выбранной
        страницы](#ссылки-на-внешние-сайты-с-выбранной-страницы-2)
-   [Приложение 2. РУВИКИ](#приложение-2-рувики)
-   [Приложение 3. Циклопедия](#приложение-3-циклопедия)
    -   [Информация о статье](#информация-о-статье-3)
    -   [Извлечь разделы статьи](#извлечь-разделы-статьи-3)
    -   [Извлечь категории статьи](#извлечь-категории-статьи-4)
    -   [История правок статьи](#история-правок-статьи-3)
    -   [Список пользователей, которые правили
        страницу](#список-пользователей-которые-правили-страницу-4)
    -   [Список всех правок
        пользователя](#список-всех-правок-пользователя-3)
    -   [Поиск статей, цитирующих внешний
        web-сайт](#поиск-статей-цитирующих-внешний-web-сайт-3)
    -   [Поиск статей, цитирующих выбранную
        страницу](#поиск-статей-цитирующих-выбранную-страницу-3)
    -   [Гиперссылки из статьи, ведущие на другие статьи
        энциклопедии](#гиперссылки-из-статьи-ведущие-на-другие-статьи-энциклопедии-3)
    -   [Ссылки на внешние сайты с выбранной
        страницы](#ссылки-на-внешние-сайты-с-выбранной-страницы-3)
-   [Обратная связь](#обратная-связь)
    -   [Лицензия](#лицензия)
    -   [Позиция по поводу открытых
        энциклопедий](#позиция-по-поводу-открытых-энциклопедий)
    -   [Отказ от ответственности](#отказ-от-ответственности)

Цель этого сборника примеров – обратить внимание на уникальные
возможности API- и SPARQL-интерефейсов сервисов Wikipedia и Wikidata.

Большая часть примеров тематически связана с академическими журналами,
поскольку первоначальная версия материала была подготовлена для доклада
на 11-ой Международной научно-практической конференции Ассоциации
научных редакторов и издателей (АНРИ) «Научное издание международного
уровня – 2023: достижения, реалии, перспективы» (23-26 мая, 2023 г.).

Приведенные примеры демонстрируют лишь **малую** часть доступных
возможностей – акцент сделан на запросах, которые могут быть выполнены в
веб-браузере пользователями, не имеющими опыта написания скриптов на
языках программирования.

Материал будет существовать в виде README страницы и продолжать
пополняться новыми примерами до тех пор пока автор (или контрибьюторы)
не решат, что другой формат будет удобнее.

Приложения будут включать примеры использования API русскоязычных вики –
[Руниверсалис](https://%D1%80%D1%83%D0%BD%D0%B8.%D1%80%D1%84/),
[РУВИКИ](https://ru.ruwiki.ru/), [Циклопедии](https://cyclowiki.org/),
развернутых на базе ПО MediaWiki.Ни факт упоминания, ни порядок
перечисления этих проектов не отражают предпочтений автора и не являются
рекомендацией к использованию.

------------------------------------------------------------------------

**Обозначения**

:blue_book: – гиперссылка на веб-страницу с подробной спецификацией или
руководство.

:pushpin: – недавно добавленные примеры (подробную историю изменений
можно всегда увидеть в
[истории](https://github.com/alexeilutay/wiki4journals/commits/main).

:warning: – важное примечание.

:top: – кнопка для возвращения к оглавлению страницы.

:art: – есть на что посмотреть.

Остальные emoji могут интепретироваться произвольно.

------------------------------------------------------------------------

## API и SPARQL интерфейсы

:warning: MediaWiki Action API и MediaWiki REST API предоставляются со
стандартной версией MediaWiki и могут быть доступны в клонах Википедий
(см. Приложение 1). Остальные API доступны только для [проектов
Wikimedia](https://meta.wikimedia.org/wiki/Wikimedia_projects).

#### MediaWiki Action API

MediaWiki Action API (/api.php) предоставляет пользователям возможности
аутентификации, получения сведений о страницах, пользователях,
совершенных правках, а также вносить изменений, обращаться к
персональным настройкам и использовать специальные права.

-   <https://www.mediawiki.org/wiki/API:Main_page>

Перелистывание результатов :fast_forward:

-   <https://www.mediawiki.org/wiki/API:Continue>

Если запрос к API не срабатывает, рекомендуется добавлять в конец
запроса `&origin=*`.

#### MediaWiki REST API

MediaWiki REST API (/rest.php) позволяет взаимодействовать с MediaWiki
путем отправки HTTP запросов к rest.php адресам URL. Этот API можно
использовать для скриптов для поиска и сбора сведений из страниц и
иллюстраций, а также изучения истории правок.

-   <https://www.mediawiki.org/wiki/API:REST_API>
-   <https://www.mediawiki.org/wiki/API:REST_API/Reference>

#### Wikimedia REST API

Wikimedia REST API (/api/rest) предоставляет доступ к контенту Wikimedia
сервисов и метаданным в машиночитаемых форматах. API интегрирован с
Wikimedia’s globally distributed caching infrastructure и создан для
обеспечения работы приложений, запрашивающих большие объемы данных.

-   <https://www.mediawiki.org/wiki/Wikimedia_REST_API>

REST API вместе с документацией доступны для большинства главных
проектов Wikimedia по адресу /api/rest_v1/.

Для всех проектов Wikimedia:

-   <https://wikimedia.org/api/rest_v1/#/>

Для англоязычной Wikipedia:

-   <https://en.wikipedia.org/api/rest_v1/#/>

-   [Спецификация API в
    JSON](https://en.wikipedia.org/api/rest_v1/?spec)

:pushpin: Каталог новых REST API от Wikimedia (в стадии разработки):

-   <https://api.wikimedia.org/wiki/API_catalog>

Стоит обратить внимание на:

-   **Core REST API** <https://api.wikimedia.org/wiki/Core_REST_API>

-   **Page Description API**
    <https://api.wikimedia.org/wiki/Page_Description_API>

-   **Feed API** <https://api.wikimedia.org/wiki/Feed_API>

#### Wikidata API

Wikidata работает на ПО Wikibase, поэтому API более правильно называть
Wikibase REST API.

-   [Swagger API
    документация](https://doc.wikimedia.org/Wikibase/master/js/rest-api/)

#### Wikidata SPARQL

Примеры SPARQL-запросов в основной части будут сопровождаться
гиперссылками, открывающими запрос в интерфейсе [Wikidata Query
Service](https://query.wikidata.org/). Для выполнения запроса в
интерфейсе не забудьте нажать кнопку :arrow_forward:.

Их также можно отправлять программными средствами с помощью R:
[WikidataR](https://github.com/TS404/WikidataR) или :snake: : пакет
[Wikidata](https://github.com/dahlia/wikidata), см. также [другие
примеры](https://www.wikidata.org/wiki/Wikidata:Tools/For_programmers)).

-   [Руководство по использованию SPARQL (частично на русском
    языке)](https://www.wikidata.org/wiki/Wikidata:SPARQL_tutorial/ru)

-   <https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/queries/examples>

-   <https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/queries/examples/advanced>

-   <https://www.wikidata.org/wiki/User:MartinPoulter/queries>

-   <https://wdqs-tutorial.toolforge.org/>

-   :blue_book: [Архивная коллекция SPARQL-запросов к Викиданным из
    еженедельных дайджестов Query of the Week,
    2015-2022)](https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/qotw).

-   [Список
    атрибутов](https://www.wikidata.org/wiki/Wikidata:List_of_properties).
    Академические издатели найдут атрибуты для описания журналов, статей
    и авторов в разделах
    [research](https://www.wikidata.org/wiki/Wikidata:List_of_properties/research),
    [science](https://www.wikidata.org/wiki/Wikidata:List_of_properties/science),
    [unique
    identifier](https://www.wikidata.org/wiki/Wikidata:List_of_properties/unique_identifier),
    [work](https://www.wikidata.org/wiki/Wikidata:List_of_properties/work).

-   [Инструменты для работы с
    Викиданными](https://www.wikidata.org/wiki/Wikidata:Tools/)

------------------------------------------------------------------------

## Материалы на русском языке

**Базовые сведения:**

-   [Статья “Викиданные” в
    Викитеке](https://ru.wikisource.org/wiki/%D0%A1%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0:%D0%92%D0%B8%D0%BA%D0%B8%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5)

-   [Защита страниц в Викиданных
    :cop:](https://ru.wikipedia.org/wiki/%D0%9F%D1%80%D0%BE%D0%B5%D0%BA%D1%82:%D0%98%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F_%D1%81_%D0%92%D0%B8%D0%BA%D0%B8%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8/%D0%98%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5_%D0%92%D0%B8%D0%BA%D0%B8%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85#%D0%97%D0%B0%D1%89%D0%B8%D1%82%D0%B0_%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86_%D0%B2_%D0%92%D0%B8%D0%BA%D0%B8%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85)

**Популярным языком:**

-   Статья [“Сервис Викиданные для научных
    журналов”](https://podpiska.rfbr.ru/materials/wikidata4journals/),
    (2023).

-   Статья [“О профилях организаций в
    Wikidata”](https://openriro.github.io/posts/wikidata-profile/),
    (2022).

-   Семинар “Работа с метаданными” (12.10.2022) от Наукометрического
    центра ВШЭ. Видео YouTube, [про Викиданные с 25-ой
    минуты](https://youtu.be/XX6eT1ON4_I?t=1504).

**Для тех, кто готов пойти дальше:** :trophy:

-   [Курс Программирование Викиданных
    (ПетрГУ)](https://ru.wikiversity.org/wiki/%D0%9F%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5_%D0%92%D0%B8%D0%BA%D0%B8%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

## Типовые задачи – сведения о статье

#### Информация о статье в Wikipedia

**`MediaWiki REST API`**

Возвращает json-структуру, содержащую идентификатор статьи, сведения о
последней правке и элемент source, в котором находится полный текст
страницы в формате вики-разметки ([что такое
вики-разметка?](https://ru.wikipedia.org/wiki/%D0%92%D0%B8%D0%BA%D0%B8%D0%BF%D0%B5%D0%B4%D0%B8%D1%8F:%D0%9A%D0%B0%D0%BA_%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D1%82%D1%8C_%D1%81%D1%82%D0%B0%D1%82%D1%8C%D0%B8)).

> [`https://en.wikipedia.org/w/rest.php/v1/page/The%20BMJ`](https://en.wikipedia.org/w/rest.php/v1/page/The%20BMJ)

**`MediaWiki Action API`**

По сравнению с предыдущим запросом возвращает более детальную
json-структуру, из которой легко извлечь текст, языковые версии,
категории, ссылки на страницы Wikipedia, ссылка на внешние страницы,
перечень изображений, секций, шаблонов, интер-вики ссылок и
идентификатор элемента Викиданных, соответствующего статье
(wikibase_item в разделе properties).

> [`https://en.wikipedia.org/w/api.php?action=parse&page=The%20BMJ&format=json`](https://en.wikipedia.org/w/api.php?action=parse&page=The%20BMJ&format=json)

**`Wikimedia REST API`**

Возвращает не содержание статьи, а сведения о ней – пространство имён
(namespace), название, идентификатор элемента Викиданных, ссылки на
основную иллюстрацию статьи, сведения о последней правке (временная
отметка, ID), краткое описание в формате простого текста и HTML.

> [`https://en.wikipedia.org/api/rest_v1/page/summary/The%20BMJ`](https://en.wikipedia.org/api/rest_v1/page/summary/The%20BMJ)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Другие названия объекта статьи

Иногда предмету статьи могут соответствовать несколько названий – в
приведенном ниже примере запрос возвращает варианты названий журнала
BMJ.

> [`https://en.wikipedia.org/w/api.php?action=query&prop=pageterms&titles=The%20BMJ&format=json`](https://en.wikipedia.org/w/api.php?action=query&prop=pageterms&titles=The%20BMJ&format=json)

------------------------------------------------------------------------

#### Все языковые версии статьи в Wikipedia

:warning: Статья в Википедии может существовать как на одном, так и на
нескольких языках, при этом содержимое языковых версий может сильно
различаться.

Запросы ниже позволяют получить перечень всех языковых версий заданной
статьи.

**`MediaWiki REST API`**

возвращает только названия страниц

> [`https://en.wikipedia.org/w/rest.php/v1/page/The_Lancet/links/language`](https://en.wikipedia.org/w/rest.php/v1/page/The_Lancet/links/language)

**`MediaWiki Action API`**

возвращает pageid для страниц объекта и полные URL на страницы языковых
версий

> [`https://en.wikipedia.org/w/api.php?action=query&titles=The_Lancet&prop=langlinks&format=json&llprop=url&lllimit=500`](https://en.wikipedia.org/w/api.php?action=query&titles=The_Lancet&prop=langlinks&format=json&llprop=url&lllimit=500)

------------------------------------------------------------------------

#### Извлечь категории статьи

Статьи Wikipedia нередко бывают отнесены к различным категориям.

**`MediaWiki Action API`**

Приведенный ниже запрос возвращает перечень категорий, к которым
отнесена статья о журнале The BMJ в англоязычной Википедии.

> [`https://en.wikipedia.org/w/api.php?action=parse&page=The%20BMJ&prop=categories&format=json`](https://en.wikipedia.org/w/api.php?action=parse&page=The%20BMJ&prop=categories&format=json)

Одна из них – “BMJ Group academic journals”.

:pushpin: Запрос ниже возвращает перечень статей, также отнесенных к
категории BMJ Group academic journals
([подробнее](https://en.wikipedia.org/w/api.php?action=help&modules=query%2Bcategorymembers)).

> [`https://en.wikipedia.org/w/api.php?cmtitle=Category:BMJ%20Group%20academic%20journals&action=query&list=categorymembers&cmlimit=500&cmprop=title|sortkey|timestamp&format=json`](https://en.wikipedia.org/w/api.php?cmtitle=Category:BMJ%20Group%20academic%20journals&action=query&list=categorymembers&cmlimit=500&cmprop=title%7Csortkey%7Ctimestamp&format=json)

------------------------------------------------------------------------

#### :pushpin: Получение изображений из статьи

**`MediaWiki Action API`**

Запрос ниже использует ранее рассмотренный механизм запроса к API
<https://www.mediawiki.org/wiki/API:Query> для получения списка всех
иллюстраций из страниц русскоязычной Википедии, содержащих строку
“аграрный университет”:

> [`https://ru.wikipedia.org/w/api.php?action=query&generator=search&gsrsearch=intitle:"аграрный университет"&prop=info|pageimages|images&gsrlimit=20&format=json`](https://ru.wikipedia.org/w/api.php?action=query&generator=search&gsrsearch=intitle:%22%D0%B0%D0%B3%D1%80%D0%B0%D1%80%D0%BD%D1%8B%D0%B9%20%D1%83%D0%BD%D0%B8%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%82%D0%B5%D1%82%22&prop=info%7Cpageimages%7Cimages&gsrlimit=20&format=json)

Расширение перечня параметров позволяет получить более широкий набор
полей:

-   inprop=url возвращает URL на найденные статьи
-   piprop=name\|original\|thumbnail&pithumbsize=300 возвращает сведения
    (в т.ч. URL) на оригинальное изображение статьи (pageimage) и его
    иконке (thumbnail), автоматически увеличенной до 300 px в ширину
    (см.
    [query+pageimages](https://www.mediawiki.org/w/api.php?action=help&modules=query%2Bpageimages))

[`https://ru.wikipedia.org/w/api.php?action=query&generator=search&gsrsearch=intitle:"аграрный университет"&prop=info|pageimages|images&inprop=url&piprop=original|thumbnail&pithumbsize=300&gsrlimit=50&format=json`](https://ru.wikipedia.org/w/api.php?action=query&generator=search&gsrsearch=intitle:%22%D0%B0%D0%B3%D1%80%D0%B0%D1%80%D0%BD%D1%8B%D0%B9%20%D1%83%D0%BD%D0%B8%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%82%D0%B5%D1%82%22&prop=info%7Cpageimages%7Cimages&inprop=url&piprop=original%7Cthumbnail&pithumbsize=300&gsrlimit=50&format=json)

Более полные сведения об изображениях внутри статьи (images) можно
получить запросами, используя имена файлов (в примере ниже запрос для
получения сведений о файле
<File:Moscow_08-2012_Petrovsko-Razumovskoe_img01.jpg>):

> [`https://www.mediawiki.org/w/api.php?action=query&titles=File:Moscow_08-2012_Petrovsko-Razumovskoe_img01.jpg&prop=imageinfo&iiprop=timestamp|url|user|extmetadata&iiextmetadatafilter=Artist|ImageDescription|GPSLatitude|GPSLongitude&format=json`](https://www.mediawiki.org/w/api.php?action=query&titles=File:Moscow_08-2012_Petrovsko-Razumovskoe_img01.jpg&prop=imageinfo&iiprop=timestamp%7Curl%7Cuser%7Cextmetadata&iiextmetadatafilter=Artist%7CImageDescription%7CGPSLatitude%7CGPSLongitude&format=json)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Извлечь разделы статьи в Wikipedia

**`MediaWiki Action API`**

[:blue_book:
Инструкция](https://www.mediawiki.org/wiki/API:Parsing_wikitext)

Возвращает перечень разделов страницы Wikipedia, их размер, порядковые
номера и названия внутренних ссылок.

> [`https://en.wikipedia.org/w/api.php?action=parse&format=json&page=The%20BMJ&prop=sections`](https://en.wikipedia.org/w/api.php?action=parse&format=json&page=The%20BMJ&prop=sections)

Получив сведения из запроса выше, можно извлечь отдельные разделы в
форматах wikitext или parsetree

> [`https://en.wikipedia.org/w/api.php?action=parse&page=The%20BMJ&prop=wikitext|parsetree&section=5&format=json`](https://en.wikipedia.org/w/api.php?action=parse&page=The%20BMJ&prop=wikitext%7Cparsetree&section=5&format=json)

------------------------------------------------------------------------

#### Получить Wikidata ID по названию статьи в Wikipedia

В отличие от Википедии, в которой не всякому академическому журналу
полагается собственная статья ([см. статью
Wikipedia:Notability\_(academic_journals)](https://en.wikipedia.org/wiki/Wikipedia:Notability_(academic_journals))),
создание и редактирование карточки журнала в Викиданных доступно каждому
зарегистрированному пользователю ([при условии соблюдения
правил](https://ru.wikipedia.org/wiki/%D0%92%D0%B8%D0%BA%D0%B8%D0%BF%D0%B5%D0%B4%D0%B8%D1%8F:%D0%9A%D1%80%D0%B0%D1%82%D0%BA%D0%B8%D0%B9_%D1%81%D0%B2%D0%BE%D0%B4_%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB)).
Типы объектов и отношений в Wikidata предлагают издателю широкий выбор
инструментов для описания журнала – истории его трансформаций, отношений
с юридическими и физическими лицами, отражения опубликованных статей и
т.д. ([подробнее в статье Сервис Викиланные для научных
журналов](https://podpiska.rfbr.ru/materials/wikidata4journals/)).

Запросы ниже позволяют для перечня статей Википедии собрать
идентификаторы Викиданных.

**`MediaWiki Action API`**

возвращает Wikibase ID (aka Wikidata ID) и wikibase-shortdesc (если
есть)

> [`https://ru.wikipedia.org/w/api.php?action=query&prop=pageprops&format=json&titles=Криосфера_Земли`](https://ru.wikipedia.org/w/api.php?action=query&prop=pageprops&format=json&titles=Криосфера_Земли)

**`Wikimedia REST API`**

возвращает информацию о странице, в которой есть поле wikibase_item

> [`https://ru.wikipedia.org/api/rest_v1/page/summary/Криосфера_Земли`](https://ru.wikipedia.org/api/rest_v1/page/summary/Криосфера_Земли)

**`Wikidata REST API`**

возвращает все запрошенные элементы Wikidata. При запросе русскоязычной
страницы необходимо заменить enwiki на ruwiki, можно также получать
заголовки на нескольких языках (en\|ru).

> [`https://www.wikidata.org/w/api.php?action=wbgetentities&format=json&sites=ruwiki&titles=Журнал_технической_физики&props=info|labels|descriptions|claims&languages=en|ru`](https://www.wikidata.org/w/api.php?action=wbgetentities&format=json&sites=ruwiki&titles=Журнал_технической_физики&props=info%7Clabels%7Cdescriptions%7Cclaims&languages=en%7Cru)

**`Wikidata SPARQL`**

```
SELECT ?lemma ?item WHERE {
  VALUES ?lemma {"Успехи химии"@ru}
  ?sitelink schema:about ?item; 
            schema:isPartOf <https://ru.wikipedia.org/>; 
            schema:name ?lemma.
}
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/#SELECT%20%3Flemma%20%3Fitem%20WHERE%20%7B%0A%20%20VALUES%20%3Flemma%20%7B%22%D0%A3%D1%81%D0%BF%D0%B5%D1%85%D0%B8%20%D1%85%D0%B8%D0%BC%D0%B8%D0%B8%22%40ru%7D%0A%20%20%3Fsitelink%20schema%3Aabout%20%3Fitem%3B%20%0A%20%20%20%20%20%20%20%20%20%20%20%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fru.wikipedia.org%2F%3E%3B%20%0A%20%20%20%20%20%20%20%20%20%20%20%20schema%3Aname%20%3Flemma.%0A%7D%0A)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Найти страницы Wikipedia по Wikidata ID

Нередко можно столкнуться и с обратной задачей – из какого-нибудь
реестра собраны идентификаторы Wikidata (например, OpenAlex или ROR) и
необходимо собрать список существующих статей в Википедии.

**`Wikidata REST API`**

> [`https://www.wikidata.org/w/api.php?action=wbgetentities&format=xml&props=sitelinks&ids=Q3453517`](https://www.wikidata.org/w/api.php?action=wbgetentities&format=xml&props=sitelinks&ids=Q3453517)

Добавление в запрос выражения вида `&sitefilter=enwiki` возвращает
английскоязычную версию статьи (ruwiki – русскоязычную).

**`Wikidata SPARQL`**

```
SELECT DISTINCT ?article WHERE {
  VALUES ?item {wd:Q3453517}
  ?article schema:about ?item; 
           schema:isPartOf <https://ru.wikipedia.org/>
}
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/#SELECT%20DISTINCT%20%3Farticle%20WHERE%20%7B%0A%20%20VALUES%20%3Fitem%20%7Bwd%3AQ3453517%7D%0A%20%20%3Farticle%20schema%3Aabout%20%3Fitem%3B%0A%20%20%20%20%20%20%20%20%20%20%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fru.wikipedia.org%2F%3E%0A%7D%0A)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Цитировать статью Wikipedia в формате bibtex

**`Wikimedia REST API`**

Сервис поддерживает также формат zotero и несколько других (mediawiki,
wikibase). Цитируемый URL включает параметр oldid – идентификатор
последней правки на момент цитирования!

:warning: Гиперссылку на страницу Wikipedia необходимо кодировать для
URL. Результат – скачивание текстового файла с цитированием в выбранном
формате.

> [`https://en.wikipedia.org/api/rest_v1/data/citation/bibtex/https%3A%2F%2Fru.wikipedia.org%2Fwiki%2FЖурнал_технической_физики`](https://en.wikipedia.org/api/rest_v1/data/citation/bibtex/https%3A%2F%2Fru.wikipedia.org%2Fwiki%2FЖурнал_технической_физики)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

## Типовые задачи – поиск статей и изображений

#### :pushpin: Поиск статьи по названию

**`MediaWiki Action API`**

В MediaWiki Action API есть 2 варианта поиска по тексту :

(а) **<https://www.mediawiki.org/wiki/API:Search>** – выполняет поиск
строки, указанной в параметре (srcsearch=) по названию статьи
(srsearch=intitle:) или тексту статьи (srsearch=text:)

> [`https://en.wikipedia.org/w/api.php?action=query&list=search&srsearch=nejm&utf8=&format=json`](https://en.wikipedia.org/w/api.php?action=query&list=search&srsearch=nejm&utf8=&format=json)

> [`https://en.wikipedia.org/w/api.php?action=query&list=search&srsearch=intitle:"Tetrahedron journal"&utf8=&format=json`](https://en.wikipedia.org/w/api.php?action=query&list=search&srsearch=intitle:%22Tetrahedron%20journal%22&utf8=&format=json)

Результаты можно выводить с дополнительной информацией, если
использовать generator, в этом случае параметры будут содержать префикс
g (например: gsrsearch вместо search). В примере ниже к результатам
поиска статей, содержащих в названии строку Chemical journal добавлены
сведения (prop=) о статьи, категориях, внутренних и внешних ссылках.

> [`https://en.wikipedia.org/w/api.php?action=query&generator=search&gsrsearch=intitle:%22Chemical%20journal%22&prop=info|categories|links|extlinks&utf8=&gsrlimit=100&format=json`](https://en.wikipedia.org/w/api.php?action=query&generator=search&gsrsearch=intitle:%22Chemical%20journal%22&prop=info%7Ccategories%7Clinks%7Cextlinks&utf8=&gsrlimit=100&format=json)

(б) **<https://www.mediawiki.org/wiki/API:Opensearch>** – выполняет
поиск строки, указанной в параметре (search=) по тексту статьи в формате
[Open Search](https://en.wikipedia.org/wiki/OpenSearch). Параметр
profile позволяет варьировать строгость запроса от strict до fuzzy (по
умолчанию – поисковик сам выбирает формат поиска).

Возвращает результаты в виде 3 списков:

-   названия страниц
-   [пустой блок, где должны были быть
    descriptions](https://phabricator.wikimedia.org/T241437),
-   URL страниц

> [`https://en.wikipedia.org/w/api.php?action=opensearch&namespace=0&profile=fuzzy&search=The Lancet&limit=5&format=json`](https://en.wikipedia.org/w/api.php?action=opensearch&namespace=0&profile=fuzzy&search=The%20Lancet&limit=5&format=json)

> [`https://ru.wikipedia.org/w/api.php?action=opensearch&namespace=0&profile=fuzzy&search=журнал общей химии&limit=5&format=json`](https://ru.wikipedia.org/w/api.php?action=opensearch&search=%D0%B6%D1%83%D1%80%D0%BD%D0%B0%D0%BB%20%D0%BE%D0%B1%D1%89%D0%B5%D0%B9%20%D1%85%D0%B8%D0%BC%D0%B8%D0%B8&profile=fuzzy&limit=5&format=json)

**`Wikimedia Core REST API`**

Новый Core REST API позволяет проводить текстовый поиск:

-   по названию
    <https://api.wikimedia.org/wiki/Core_REST_API/Reference/Search/Search_titles>

> [`https://api.wikimedia.org/core/v1/wikipedia/ru/search/title?q=институт физической химии&limit=10`](https://api.wikimedia.org/core/v1/wikipedia/ru/search/title?q=%D0%B8%D0%BD%D1%81%D1%82%D0%B8%D1%82%D1%83%D1%82%20%D1%84%D0%B8%D0%B7%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B9%20%D1%85%D0%B8%D0%BC%D0%B8%D0%B8&limit=10)

-   по полному тексту
    <https://api.wikimedia.org/wiki/Core_REST_API/Reference/Search/Search_content>

> [`https://api.wikimedia.org/core/v1/wikipedia/en/search/page?q=the%20lancet&limit=10`](https://api.wikimedia.org/core/v1/wikipedia/en/search/page?q=the%20lancet&limit=10)

Поиск имеет универсальный синтаксис и позволяет проводить поиск по
широкому перечню [проектов
Wikimedia](https://api.wikimedia.org/wiki/Wikimedia_projects) –
например, по wikipedia (статьи), по commons (иллюстрации, аудио, видео),
по wiktionary (словарные записи).

[:top:](#mediawiki-action-api)

#### :pushpin: Поиск изображений по названию

Поиск по названию изображений выполняется так:

> [`https://commons.wikimedia.org/w/api.php?action=query&generator=search&gsrsearch=intitle:"аграрный университет"&prop=info|imageinfo|redirects&inprop=url&gsrnamespace=6&iiprop=timestamp|url|user|extmetadata&iiextmetadatafilter=Artist|ImageDescription|GPSLatitude|GPSLongitude&redirects=&format=json&gsrlimit=20`](https://commons.wikimedia.org/w/api.php?action=query&generator=search&gsrsearch=intitle:%22%D0%B0%D0%B3%D1%80%D0%B0%D1%80%D0%BD%D1%8B%D0%B9%20%D1%83%D0%BD%D0%B8%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%82%D0%B5%D1%82%22&prop=info%7Cimageinfo%7Credirects&inprop=url&gsrnamespace=6&iiprop=timestamp%7Curl%7Cuser%7Cextmetadata&iiextmetadatafilter=Artist%7CImageDescription%7CGPSLatitude%7CGPSLongitude&redirects=&format=json&gsrlimit=20)

Запрос выше возвращает изображения, содержащие “аграрный университет” в
названии.

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

## Типовые задачи – правки и просмотры

Правки в статьи Википедию и в записи Викиданных могут вносить люди и
боты, но история всех изменений доступна для просмотра. Подобная
прозрачность, в сочетании с правилами противодействия
[Вандализму](https://ru.wikipedia.org/wiki/%D0%92%D0%B8%D0%BA%D0%B8%D0%BF%D0%B5%D0%B4%D0%B8%D1%8F:%D0%92%D0%B0%D0%BD%D0%B4%D0%B0%D0%BB%D0%B8%D0%B7%D0%BC),
[Войнам
правок](https://ru.wikipedia.org/wiki/%D0%92%D0%B8%D0%BA%D0%B8%D0%BF%D0%B5%D0%B4%D0%B8%D1%8F:%D0%92%D0%BE%D0%B9%D0%BD%D0%B0_%D0%BF%D1%80%D0%B0%D0%B2%D0%BE%D0%BA)
и другим негативным проявлениям человеческого несогласия, повышают
доверие читателей.

#### История правок статьи в Wikipedia

**`MediaWiki Action API`**

:pushpin: [Спецификация
API](https://www.mediawiki.org/wiki/API:Revisions)

Запрос ниже возвращает информацию о 5 правках, внесенных после 01 января
2021 года в статью Lancet в англоязычной Википедии.

> [`https://en.wikipedia.org/w/api.php?action=query&prop=revisions&titles=Lancet&rvslots=main&rvlimit=5&rvdir=newer&rvstart=2021-01-01T00:00:00Z&rvprop=ids|flags|timestamp|user|userid|size|contentmodel|comment|parsedcomment|content|tags|flagged&format=json`](https://en.wikipedia.org/w/api.php?action=query&prop=revisions&titles=Lancet&rvslots=main&rvlimit=5&rvdir=newer&rvstart=2021-01-01T00:00:00Z&rvprop=ids%7Cflags%7Ctimestamp%7Cuser%7Cuserid%7Csize%7Ccontentmodel%7Ccomment%7Cparsedcomment%7Ccontent%7Ctags%7Cflagged&format=json)

**`MediaWiki REST API`**

Запрос возвращает историю правок с id изменения, временем правки,
данными о создателе (id, name), размером изменений (delta) и
сопутствующими комментариями.

> [`https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history`](https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history)

Дополнив запрос выражением `?older_than=939967546` (или
`?newer_than=1018790892`) можно получить более ранние (или поздние)
правки (вместо цифр подставлять id конкретной правки)

Добавив в запрос выражение `?filter=...`, можно отобрать только
определенные правки:

-   `reverted`: правки, отменяющие более ранние изменения
-   `anonymous`: правки, сделанные анонимными пользователями (показывает
    IP),
-   `bot`: правки, сделанные ботами,
-   `minor`: правки, отмеченные как незначительные (minor edits)

> [`https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history?older_than=97918317&filter=anonymous`](https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history?older_than=97918317&filter=anonymous)

**Количество правок**

:warning: В названии страницы необходимо предварительно заменить пробелы
на \_ (вместо The BMJ, не The%20BMJ, а The_BMJ) – в сведениях о
странице, возвращаемых MediaWiki REST API
([пример](https://en.wikipedia.org/w/rest.php/v1/page/The_BMJ)),
название в необходимом формате находится в поле key. В противном случае
запрос вернет ошибку.

> [`https://en.wikipedia.org/w/rest.php/v1/page/The_BMJ/history/counts/edits`](https://en.wikipedia.org/w/rest.php/v1/page/The_BMJ/history/counts/edits)

> [`https://ru.wikipedia.org/w/rest.php/v1/page/Доклады_Академии_наук/history/counts/edits?from=88695017&to=97918317`](https://ru.wikipedia.org/w/rest.php/v1/page/Доклады_Академии_наук/history/counts/edits?from=88695017&to=97918317)

:pushpin: **Количество редакторов**

> [`https://en.wikipedia.org/w/rest.php/v1/page/The_BMJ/history/counts/editors`](https://en.wikipedia.org/w/rest.php/v1/page/The_BMJ/history/counts/editors)

**`Wikimedia REST API`**

Запрос ниже возвращает последнюю правку и имя последнего пользователя

> [`https://ru.wikipedia.org/api/rest_v1/page/title/Доклады%20Академии%20наук`](https://ru.wikipedia.org/api/rest_v1/page/title/Доклады%20Академии%20наук)

Синтаксис запросов в Wikimedia Core REST API –
<https://api.wikimedia.org/wiki/Core_REST_API/Reference/Revisions/Get_page_history>

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Список пользователей, которые правили страницу

**`MediaWiki Action API`**

[:blue_book:
Информация](https://www.mediawiki.org/w/api.php?action=help&modules=query%2Bcontributors)

> [`https://en.wikipedia.org/w/api.php?action=query&titles=The%20BMJ&prop=contributors&pclimit=200&pcgroup=bot&format=json`](https://en.wikipedia.org/w/api.php?action=query&titles=The%20BMJ&prop=contributors&pclimit=200&pcgroup=bot&format=json)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Список всех правок пользователя или с IP-адреса

**`MediaWiki Action API`**

:pushpin: [:blue_book:
API-спецификация](https://www.mediawiki.org/wiki/API:Allrevisions)

> [`https://en.wikipedia.org/w/api.php?action=query&list=allrevisions&arvuser=Thinker78&arvprop=ids|flags|timestamp|user|userid|size|contentmodel|comment|parsedcomment|tags|flagged`](https://en.wikipedia.org/w/api.php?action=query&list=allrevisions&arvuser=Thinker78&arvprop=ids%7Cflags%7Ctimestamp%7Cuser%7Cuserid%7Csize%7Ccontentmodel%7Ccomment%7Cparsedcomment%7Ctags%7Cflagged)

Для получения текста правок добавьте в аргумент arvprop значение
content.

Для получения правок, сделанных с IP-адреса, используйте IP-адрес вмето
имени пользователя в аргументе `arvuser=...`

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Статистика просмотров страницы в Wikipedia

[:blue_book: Инструкция](https://wikimedia.org/api/rest_v1/)

Запрос ниже возвращает количество просмотров статьи о журнале The BMJ в
англоязычной Википедии с 01 января 2022 по 31 марта 2023 г.

> [`https://wikimedia.org/api/rest_v1/metrics/pageviews/per-article/en.wikipedia/all-access/all-agents/The%20BMJ/monthly/20220101/20230331`](https://wikimedia.org/api/rest_v1/metrics/pageviews/per-article/en.wikipedia/all-access/all-agents/The%20BMJ/monthly/20220101/20230331)

**Другие веб-интерфейсы:**

-   <https://meta.wikimedia.org/wiki/Pageviews_Analysis>
-   <https://pageviews.wmcloud.org/>
-   <http://stats.grok.se/json/en/latest30/Britney_Spears>
-   <https://www.wikishark.com/title/en/The_BMJ>
-   <https://wikipediaviews.org/>

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Количество новых страниц в Wikipedia по месяцам

**`Wikimedia REST API`**

> [`https://wikimedia.org/api/rest_v1/metrics/edited-pages/new/ru.wikipedia.org/user/content/monthly/20210101/20230401`](https://wikimedia.org/api/rest_v1/metrics/edited-pages/new/ru.wikipedia.org/user/content/monthly/20210101/20230401)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Рейтинг редакторов по дням

**`Wikimedia REST API`**

> [`https://wikimedia.org/api/rest_v1/metrics/editors/top-by-edits/ru.wikipedia.org/user/content/2023/03/31`](https://wikimedia.org/api/rest_v1/metrics/editors/top-by-edits/ru.wikipedia.org/user/content/2023/03/31)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Количество новых редакторов по месяцам

**`Wikimedia REST API`**

> [`https://wikimedia.org/api/rest_v1/metrics/registered-users/new/ru.wikipedia.org/monthly/20200101/20230331`](https://wikimedia.org/api/rest_v1/metrics/registered-users/new/ru.wikipedia.org/monthly/20200101/20230331)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

## Типовые задачи – ссылки и цитирования

#### Поиск статей в Wikipedia, цитирующих внешний web-сайт

**`MediaWiki Action API`**

[:blue_book: Инструкция](https://www.mediawiki.org/wiki/API:Exturlusage)

Можно искать ссылки только в статьях определенного типа, используя
выражение `&eunamespace=...` и определенные значения (0 – Wikipedia
Page, 1 – Talk:Page, 2 – Профили пользователей, 3 – личные User talk
страницы).

Запрос ниже возвращает перечень статей Википедии (namespace = 0), в
которых присутствуют гиперссылки на сайт издательства “Медиасфера”.

> [`https://ru.wikipedia.org/w/api.php?action=query&format=json&list=exturlusage&euquery=www.mediasphera.ru&eunamespace=0`](https://ru.wikipedia.org/w/api.php?action=query&format=json&list=exturlusage&euquery=www.mediasphera.ru&eunamespace=0)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Поиск статей Wikipedia, цитирующих выбранную страницу Wikipedia

**`MediaWiki Action API`**

[:blue_book:
Инструкция](https://www.mediawiki.org/w/api.php?action=help&modules=query%2Blinkshere)

Запрос ниже возвращает перечень статей в русскоязычной Википедии, в
которых присутствует гиперссылка на статью о Журнале экспериментальной и
теоретической физике (ЖЭТФ).

> [`https://ru.wikipedia.org/w/api.php?action=query&titles=Журнал_экспериментальной_и_теоретической_физики&prop=linkshere&lhlimit=200&lhnamespace=0&format=json`](https://ru.wikipedia.org/w/api.php?action=query&titles=%D0%96%D1%83%D1%80%D0%BD%D0%B0%D0%BB_%D1%8D%D0%BA%D1%81%D0%BF%D0%B5%D1%80%D0%B8%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D0%B9_%D0%B8_%D1%82%D0%B5%D0%BE%D1%80%D0%B5%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B9_%D1%84%D0%B8%D0%B7%D0%B8%D0%BA%D0%B8&prop=linkshere&lhlimit=200&lhnamespace=0&format=json)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Гиперссылки из статьи Wikipedia, ведущие на другие статьи Wikipedia

Запрос ниже возвращает перечень статей Википедии, на которые ссылается
выбранная статья.

**`MediaWiki Action API`**

> [`https://en.wikipedia.org/w/api.php?action=parse&page=The%20BMJ&prop=links&format=json`](https://en.wikipedia.org/w/api.php?action=parse&page=The%20BMJ&prop=links&format=json)

------------------------------------------------------------------------

#### Ссылки на внешние сайты с выбранной страницы Wikipedia

[:blue_book: Инструкция](https://www.mediawiki.org/wiki/API:Extlinks)

**`MediaWiki Action API`**

> [`https://en.wikipedia.org/w/api.php?action=query&titles=The%20BMJ&prop=extlinks&ellimit=500&elexpandurl=true&format=json`](https://en.wikipedia.org/w/api.php?action=query&titles=The%20BMJ&prop=extlinks&ellimit=500&elexpandurl=true&format=json)

Можно объединить ссылки с внутренними (на страницы Wikipedia), указав
`prop=extlinks|links`.

**\[Альтернативный
способ\]**(<https://www.mediawiki.org/wiki/API:Parsing_wikitext>)

> [`https://en.wikipedia.org/w/api.php?action=parse&page=The%20BMJ&prop=externallinks&format=json`](https://en.wikipedia.org/w/api.php?action=parse&page=The%20BMJ&prop=externallinks&format=json)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

## “Наукометрия” в Wikidata

Сведения о научных изданиях и публикациях непрерывно добавляются в
Wikidata см. [раздел Journals в сервисе
Mix’n’match](https://mix-n-match.toolforge.org/#/group/journals)
трудолюбивыми ботами и энтузиастами (см.
[1](https://www.wikidata.org/wiki/Wikidata:WikiProject_Source_MetaData),
[2](https://meta.wikimedia.org/wiki/WikiCite/Projects), что [упрощает их
цитирование в статьях
Wikipedia](https://en.wikipedia.org/wiki/Template:Cite_Q).

Более того, [крупнейшие мировые издатели предоставляют бесплатный
доступ](https://wikipedialibrary.wmflabs.org/) к своим полнотекстовым
архивам для опытных редакторов Wikipedia. Не только потому, что это
[источник
трафика](http://chronograph.labs.crossref.org/domain.html?domain=en.wikipedia.org),
но и потому, что Википедию читают в том числе и люди вне академической
среды, которые оценят готовые ссылки на научные источники (журналисты,
лоббисты, просветители, волонтеры, школьники, учителя и другие категории
небезразличных и незащищенных от информационного воздействия граждан).

Цитирования статей в Википедии учитываются аналитическими инструментами
([Altmetric](https://www.altmetric.com/solutions/free-tools/bookmarklet/),
[Plum Analytics](https://plumanalytics.com/), а также CrossRef (см.
[Event Data API](https://www.crossref.org/services/event-data/) и
[Relations
API](https://community.crossref.org/t/relationships-are-here/3523)).

Связанность данных в Wikidata позволяет расширить диапазон возможностей
для анализа научных журналов, публикаций, авторов (см. ссылки ниже).

-   [:art: Профиль журнала ЖЭТФ в сервисе Reasonator / на основе
    Викиданных)](https://reasonator.toolforge.org/?q=Q23973)

-   [:art: Профиль журнала ЖЭТФ в сервисе Scholia / на основе
    Викиданных)](https://scholia.toolforge.org/venue/Q23973)

И хотя сервис Wikidata, как источник сведений для библиометрического
анализа, не может всерьез рассматриваться как альтернатива Web of
Science или Scopus, он позволяет включить в анализ новые данные, которые
в вышеупомянутых индексах цитирования отсутствуют. Запросы ниже призваны
проиллюстрировать данный тезис.

------------------------------------------------------------------------

#### Все российские журналы в Wikidata

Запрос ниже возвращает список журналов, которые относятся к
типу/подклассу Q5633421 (scientific journal) или Q737498 (academic
journal), и для атрибута P495 (country of origin) имеют значение Russia
(Q159).

:warning: если журнал в Wikidata отнесен к другому типу изданий, который
не является подклассом Q5633421 или Q737498 (например, magazine), то
такой журнал не будет найден. Так же запрос не обнаружит журналы, у
которых поле P495 не заполнено или указывает на другую страну.

**`Wikidata SPARQL`**

``` r
SELECT DISTINCT ?journal ?name WHERE {
  VALUES ?type {wd:Q5633421 wd:Q737498}
  ?journal wdt:P31/wdt:P279* ?type;  wdt:P495 wd:Q159.     
  SERVICE wikibase:label {
    bd:serviceParam wikibase:language "en, ru".
    ?journal rdfs:label ?name .
  }
}
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/#SELECT%20DISTINCT%20%3Fjournal%20%3Fname%20WHERE%20%7B%0A%20%20VALUES%20%3Ftype%20%7Bwd%3AQ5633421%20wd%3AQ737498%7D%0A%20%20%3Fjournal%20wdt%3AP31%2Fwdt%3AP279%2a%20%3Ftype%3B%20%20wdt%3AP495%20wd%3AQ159.%20%20%20%20%20%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22en%2C%20ru%22.%0A%20%20%20%20%3Fjournal%20rdfs%3Alabel%20%3Fname%20.%0A%20%20%7D%0A%7D)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Количество статей в Wikidata в российских журналах

**`Wikidata SPARQL`**

``` r
SELECT ?journal ?journal_title (count(distinct(?item)) as ?count) 
WITH {
 SELECT DISTINCT ?journal ?journal_title 
  WHERE {
    VALUES ?type {wd:Q5633421 wd:Q737498}.
           ?journal wdt:P31/wdt:P279 ?type; wdt:P495 wd:Q159.
    SERVICE wikibase:label {
      bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en,ru". 
      ?journal rdfs:label ?journal_title.
      }
    }
} as %sss 
WHERE {
  INCLUDE %sss .
  ?item wdt:P1433 ?journal; wdt:P31 wd:Q13442814.
  }
GROUP BY ?journal ?journal_title
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/#SELECT%20%3Fjournal%20%3Fjournal_title%20%28count%28distinct%28%3Fitem%29%29%20as%20%3Fcount%29%20%0AWITH%20%7B%0A%20SELECT%20DISTINCT%20%3Fjournal%20%3Fjournal_title%20%0A%20%20WHERE%20%7B%0A%20%20%20%20VALUES%20%3Ftype%20%7Bwd%3AQ5633421%20wd%3AQ737498%7D.%0A%20%20%20%20%20%20%20%20%20%20%20%3Fjournal%20wdt%3AP31%2Fwdt%3AP279%20%3Ftype%3B%20wdt%3AP495%20wd%3AQ159.%0A%20%20%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%2Cru%22.%20%0A%20%20%20%20%20%20%3Fjournal%20rdfs%3Alabel%20%3Fjournal_title.%0A%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%7D%20as%20%25sss%20%0AWHERE%20%7B%0A%20%20INCLUDE%20%25sss%20.%0A%20%20%3Fitem%20wdt%3AP1433%20%3Fjournal%3B%20wdt%3AP31%20wd%3AQ13442814.%0A%20%20%7D%0AGROUP%20BY%20%3Fjournal%20%3Fjournal_title%0A)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Извлечение источников заданного атрибута

Согласно правилам Wikidata при присвоении значения атрибуту (Property)
объекта рекомендуется указывать источник (Reference). Запрос ниже
извлекает из карточки журнала Russian Chemical Reviews (Q3453517)
значения атрибута P236 (ISSN) и указанные для них источники типов P248
(ссылка на источник, который присутствует в Wikidata как описанный
объект – ЕГРЮЛ или перечень журналов ERA 2012) или P143 (извлечено из
других Вики-сервисов – Wikipedia).

**`Wikidata SPARQL`**

``` r
SELECT ?issn ?ref ?refLabel 
WHERE {
  wd:Q3453517 p:P236 [
    ps:P236 ?issn; prov:wasDerivedFrom [
      pr:P248|pr:P143 ?ref 
    ]
  ].
  SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
}
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/#SELECT%20%3Fissn%20%3Fref%20%3FrefLabel%20%0AWHERE%20%7B%0A%20%20wd%3AQ3453517%20p%3AP236%20%5B%0A%20%20%20%20ps%3AP236%20%3Fissn%3B%20prov%3AwasDerivedFrom%20%5B%0A%20%20%20%20%20%20pr%3AP248%7Cpr%3AP143%20%3Fref%20%0A%20%20%20%20%5D%0A%20%20%5D.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22en%22.%20%7D%0A%7D%0A%0A)

[:top:](#mediawiki-action-api)

#### Поиск журнала по ISSN в Wikidata и импорт сведений

Запрос ниже находит элементы Wikidata, содержащие значения ISSN
1550-8943 и 0007-1447, и для каждого извлекает значения для широкого
набора атрибутов.

**`Wikidata SPARQL`**

``` r
SELECT DISTINCT ?item ?types ?issns ?issnLs ?titles ?short_titles 
    ?itemlabel_en ?itemlabel_ru  ?countries ?langs ?publishers ?websites 
    ?articleEN ?articleRU  ?elibrary ?openalex_ids ?scilit_ids ?nlm_ids 
    ?cref_ids ?coci_ids ?scids ?dim_ids  ?doaj_ids ?bnf_ids ?sudoc_ids ?gnd_ids 
    ?eics ?eic_orcids ?editors ?editor_orcids  ?inception  ?founded ?part_of ?has_part 
    ?follows ?followed ?replaces ?replaced ?discontinued ?translation ?subjects
WITH {
 SELECT DISTINCT ?item 
  (GROUP_CONCAT(DISTINCT ?website; separator = " | ") as ?websites) 
  (GROUP_CONCAT(DISTINCT ?typeLabel; separator = " | ") as ?types)
  (GROUP_CONCAT(DISTINCT ?title; separator = " | ") as ?titles)
  (GROUP_CONCAT(DISTINCT ?short_title; separator = " | ") as ?short_titles)
  (GROUP_CONCAT(DISTINCT ?main_subjectLabel; separator = " | ") as ?subjects)
  (GROUP_CONCAT(DISTINCT ?publisherLabel; separator = " | ") as ?publishers)
  (GROUP_CONCAT(DISTINCT ?country; separator = " | ") as ?countries)
  (GROUP_CONCAT(DISTINCT ?language; separator = " | ") as ?langs)
  (GROUP_CONCAT(DISTINCT ?issn; separator = " | ") as ?issns) 
  (GROUP_CONCAT(DISTINCT ?issnL; separator = " | ") as ?issnLs)
  (GROUP_CONCAT(DISTINCT ?openalex; separator = " | ") as ?openalex_ids)
  (GROUP_CONCAT(DISTINCT ?dimensions; separator = " | ") as ?dim_ids)
  (GROUP_CONCAT(DISTINCT ?crossref; separator = " | ") as ?cref_ids) 
  (GROUP_CONCAT(DISTINCT ?nlm; separator = " | ") as ?nlm_ids)
  (GROUP_CONCAT(DISTINCT ?coci; separator = " | ") as ?coci_ids)
  (GROUP_CONCAT(DISTINCT ?bnf; separator = " | ") as ?bnf_ids)
  (GROUP_CONCAT(DISTINCT ?gnd; separator = " | ") as ?gnd_ids)
  (GROUP_CONCAT(DISTINCT ?doaj; separator = " | ") as ?doaj_ids)
  (GROUP_CONCAT(DISTINCT ?sudoc; separator = " | ") as ?sudoc_ids)
  (GROUP_CONCAT(DISTINCT ?scilit; separator = " | ") as ?scilit_ids)
  (GROUP_CONCAT(DISTINCT ?scid; separator = " | ") as ?scids)
  (GROUP_CONCAT(DISTINCT ?editor_orcid; separator = " | ") as ?editor_orcids)
  (GROUP_CONCAT(DISTINCT ?eic_orcid; separator = " | ") as ?eic_orcids)                 
  (GROUP_CONCAT(DISTINCT ?editorLabel; separator = " | ") as ?editors)
  (GROUP_CONCAT(DISTINCT ?eicLabel; separator = " | ") as ?eics)  
WHERE{
    ?item wdt:P236 ?query. FILTER(?query in ("1550-8943", "0007-1447")).
    optional{?item wdt:P31 ?type. ?type rdfs:label ?typeLabel.
                 FILTER(lang(?typeLabel)="en").}
    optional{?item wdt:P236 ?issn.} 
    optional{?item wdt:P7363 ?issnL.} 
    optional{?item wdt:P5115 ?doaj.} 
    optional{?item wdt:P10283 ?openalex.}
    optional{?item wdt:P8375 ?crossref.}  
    optional{?item wdt:P3181 ?coci.}
    optional{?item wdt:P1156 ?scid.} 
    optional{?item wdt:P6180 ?dimensions.}             
    optional{?item wdt:P268 ?bnf.}  
    optional{?item wdt:P227 ?gnd.}
    optional{?item wdt:P1025 ?sudoc.}
    optional{?item wdt:P7662 ?scilit.} 
    optional{?item wdt:P1055 ?nlm.}
    optional{?item wdt:P856 ?website.}
    optional{?item wdt:P1476 ?title} 
    optional{?item wdt:P1813 ?short_title.}
    optional{?item wdt:P407 ?ll. ?ll rdfs:label ?language.
           FILTER(lang(?language)="en")}
    optional{?item wdt:P495 ?cc. ?cc rdfs:label ?country.
           FILTER(lang(?country)="en")}
    optional{?item wdt:P921 ?main_subject. 
           ?main_subject rdfs:label ?main_subjectLabel.
           FILTER(lang(?main_subjectLabel)="en") }
   optional{?item wdt:P123 ?publisher. 
           ?publisher rdfs:label ?publisherLabel.
           FILTER(lang(?publisherLabel)="en")}
   optional{?item wdt:P5769 ?eic. 
           ?eic rdfs:label ?eicLabel. 
           FILTER(lang(?eicLabel)="en").
           optional{?eic wdt:P496 ?eic_orcid.}}
   optional{?item wdt:P98 ?editor. 
           ?editor rdfs:label ?editorLabel.
           FILTER(lang(?editorLabel)="en").
           optional{?editor wdt:P496 ?editor_orcid.}}
   } 
GROUP BY ?item ?itemlabel_en
} as %sss
WHERE {
INCLUDE %sss .
   optional{?item rdfs:label ?itemlabel_en. FILTER(lang(?itemlabel_en)="en")}
   optional{?item rdfs:label ?itemlabel_ru. FILTER(lang(?itemlabel_ru)="ru")}
   optional{?item wdt:P10952 ?elibrary}    
   optional{?item wdt:P571 ?inception} 
   optional{?item wdt:P112 ?founded}
   optional{?item wdt:P527 ?has_part}
   optional{?item wdt:P361 ?part_of}
   optional{?item wdt:P155 ?follows}  
   optional{?item wdt:P156 ?followed}         
   optional{?item wdt:P1365 ?replaces} 
   optional{?item wdt:P1366 ?replaced}
   optional{?item wdt:P2669 ?discontinued}  
   optional{?item wdt:P9745 ?translation}
   optional {
     ?articleEN schema:about ?item.
     ?articleEN schema:isPartOf <https://en.wikipedia.org/>.
     ?articleRU schema:about ?item.
     ?articleRU schema:isPartOf <https://ru.wikipedia.org/>.
    }
}
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/#SELECT%20DISTINCT%20%3Fitem%20%3Ftypes%20%3Fissns%20%3FissnLs%20%3Ftitles%20%3Fshort_titles%20%0A%20%20%20%20%3Fitemlabel_en%20%3Fitemlabel_ru%20%20%3Fcountries%20%3Flangs%20%3Fpublishers%20%3Fwebsites%20%0A%20%20%20%20%3FarticleEN%20%3FarticleRU%20%20%3Felibrary%20%3Fopenalex_ids%20%3Fscilit_ids%20%3Fnlm_ids%20%0A%20%20%20%20%3Fcref_ids%20%3Fcoci_ids%20%3Fscids%20%3Fdim_ids%20%20%3Fdoaj_ids%20%3Fbnf_ids%20%3Fsudoc_ids%20%3Fgnd_ids%20%0A%20%20%20%20%3Feics%20%3Feic_orcids%20%3Feditors%20%3Feditor_orcids%20%20%3Finception%20%20%3Ffounded%20%3Fpart_of%20%3Fhas_part%20%0A%20%20%20%20%3Ffollows%20%3Ffollowed%20%3Freplaces%20%3Freplaced%20%3Fdiscontinued%20%3Ftranslation%20%3Fsubjects%0AWITH%20%7B%0A%20SELECT%20DISTINCT%20%3Fitem%20%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fwebsite%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fwebsites%29%20%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3FtypeLabel%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Ftypes%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Ftitle%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Ftitles%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fshort_title%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fshort_titles%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fmain_subjectLabel%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fsubjects%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3FpublisherLabel%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fpublishers%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fcountry%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fcountries%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Flanguage%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Flangs%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fissn%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fissns%29%20%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3FissnL%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3FissnLs%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fopenalex%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fopenalex_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fdimensions%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fdim_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fcrossref%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fcref_ids%29%20%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fnlm%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fnlm_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fcoci%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fcoci_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fbnf%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fbnf_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fgnd%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fgnd_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fdoaj%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fdoaj_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fsudoc%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fsudoc_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fscilit%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fscilit_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fscid%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fscids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Feditor_orcid%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Feditor_orcids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Feic_orcid%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Feic_orcids%29%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3FeditorLabel%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Feditors%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3FeicLabel%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Feics%29%20%20%0AWHERE%7B%0A%20%20%20%20%3Fitem%20wdt%3AP236%20%3Fquery.%20FILTER%28%3Fquery%20in%20%28%221550-8943%22%2C%20%220007-1447%22%29%29.%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP31%20%3Ftype.%20%3Ftype%20rdfs%3Alabel%20%3FtypeLabel.%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20FILTER%28lang%28%3FtypeLabel%29%3D%22en%22%29.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP236%20%3Fissn.%7D%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP7363%20%3FissnL.%7D%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP5115%20%3Fdoaj.%7D%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP10283%20%3Fopenalex.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP8375%20%3Fcrossref.%7D%20%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP3181%20%3Fcoci.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP1156%20%3Fscid.%7D%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP6180%20%3Fdimensions.%7D%20%20%20%20%20%20%20%20%20%20%20%20%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP268%20%3Fbnf.%7D%20%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP227%20%3Fgnd.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP1025%20%3Fsudoc.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP7662%20%3Fscilit.%7D%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP1055%20%3Fnlm.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP856%20%3Fwebsite.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP1476%20%3Ftitle%7D%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP1813%20%3Fshort_title.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP407%20%3Fll.%20%3Fll%20rdfs%3Alabel%20%3Flanguage.%0A%20%20%20%20%20%20%20%20%20%20%20FILTER%28lang%28%3Flanguage%29%3D%22en%22%29%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP495%20%3Fcc.%20%3Fcc%20rdfs%3Alabel%20%3Fcountry.%0A%20%20%20%20%20%20%20%20%20%20%20FILTER%28lang%28%3Fcountry%29%3D%22en%22%29%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP921%20%3Fmain_subject.%20%0A%20%20%20%20%20%20%20%20%20%20%20%3Fmain_subject%20rdfs%3Alabel%20%3Fmain_subjectLabel.%0A%20%20%20%20%20%20%20%20%20%20%20FILTER%28lang%28%3Fmain_subjectLabel%29%3D%22en%22%29%20%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP123%20%3Fpublisher.%20%0A%20%20%20%20%20%20%20%20%20%20%20%3Fpublisher%20rdfs%3Alabel%20%3FpublisherLabel.%0A%20%20%20%20%20%20%20%20%20%20%20FILTER%28lang%28%3FpublisherLabel%29%3D%22en%22%29%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP5769%20%3Feic.%20%0A%20%20%20%20%20%20%20%20%20%20%20%3Feic%20rdfs%3Alabel%20%3FeicLabel.%20%0A%20%20%20%20%20%20%20%20%20%20%20FILTER%28lang%28%3FeicLabel%29%3D%22en%22%29.%0A%20%20%20%20%20%20%20%20%20%20%20optional%7B%3Feic%20wdt%3AP496%20%3Feic_orcid.%7D%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP98%20%3Feditor.%20%0A%20%20%20%20%20%20%20%20%20%20%20%3Feditor%20rdfs%3Alabel%20%3FeditorLabel.%0A%20%20%20%20%20%20%20%20%20%20%20FILTER%28lang%28%3FeditorLabel%29%3D%22en%22%29.%0A%20%20%20%20%20%20%20%20%20%20%20optional%7B%3Feditor%20wdt%3AP496%20%3Feditor_orcid.%7D%7D%0A%20%20%20%7D%20%0AGROUP%20BY%20%3Fitem%20%3Fitemlabel_en%0A%7D%20as%20%25sss%0AWHERE%20%7B%0AINCLUDE%20%25sss%20.%0A%20%20%20optional%7B%3Fitem%20rdfs%3Alabel%20%3Fitemlabel_en.%20FILTER%28lang%28%3Fitemlabel_en%29%3D%22en%22%29%7D%0A%20%20%20optional%7B%3Fitem%20rdfs%3Alabel%20%3Fitemlabel_ru.%20FILTER%28lang%28%3Fitemlabel_ru%29%3D%22ru%22%29%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP10952%20%3Felibrary%7D%20%20%20%20%0A%20%20%20optional%7B%3Fitem%20wdt%3AP571%20%3Finception%7D%20%0A%20%20%20optional%7B%3Fitem%20wdt%3AP112%20%3Ffounded%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP527%20%3Fhas_part%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP361%20%3Fpart_of%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP155%20%3Ffollows%7D%20%20%0A%20%20%20optional%7B%3Fitem%20wdt%3AP156%20%3Ffollowed%7D%20%20%20%20%20%20%20%20%20%0A%20%20%20optional%7B%3Fitem%20wdt%3AP1365%20%3Freplaces%7D%20%0A%20%20%20optional%7B%3Fitem%20wdt%3AP1366%20%3Freplaced%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP2669%20%3Fdiscontinued%7D%20%20%0A%20%20%20optional%7B%3Fitem%20wdt%3AP9745%20%3Ftranslation%7D%0A%20%20%20optional%20%7B%0A%20%20%20%20%20%3FarticleEN%20schema%3Aabout%20%3Fitem.%0A%20%20%20%20%20%3FarticleEN%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fen.wikipedia.org%2F%3E.%0A%20%20%20%20%20%3FarticleRU%20schema%3Aabout%20%3Fitem.%0A%20%20%20%20%20%3FarticleRU%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fru.wikipedia.org%2F%3E.%0A%20%20%20%20%7D%0A%7D)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Статьи из выбранного журнала и цитирующие их журналы

Запрос ниже находит в Wikidata записи, соответствующие статьям из
“Палеонтологического журнала” и имеющие значение DOI, и возвращает для
каждой статьи название, перечень цитирующих журналов и общее количество
цитирований.

:warning: результат учитывает только статьи, которые имеют собственные
элементы в Wikidata, отнесены к журналам через атрибут P1433 (published
in) и связаны отношением P2860 (cites work).

**`Wikidata SPARQL`**

``` r
SELECT DISTINCT ?doi ?itemLabel ?citingJournalLabel 
                (count(distinct(?citing_pub)) as ?count)
WHERE {
  ?item wdt:P1433 wd:Q246955; 
        wdt:P356 ?doi. 
  optional{ 
    ?citing_pub wdt:P2860 ?item; 
                wdt:P1433 ?citingJournal.
  }
  SERVICE wikibase:label {
      bd:serviceParam wikibase:language "[AUTO_LANGUAGE], en, ru".
      ?item rdfs:label ?itemLabel .
      ?citingJournal rdfs:label ?citingJournalLabel .
  }
}
GROUP BY ?doi ?itemLabel ?citingJournalLabel
ORDER BY ?itemLabel
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/#SELECT%20DISTINCT%20%3Fdoi%20%3FitemLabel%20%3FcitingJournalLabel%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%28count%28distinct%28%3Fciting_pub%29%29%20as%20%3Fcount%29%0AWHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP1433%20wd%3AQ246955%3B%20%0A%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP356%20%3Fdoi.%20%0A%20%20optional%7B%20%0A%20%20%20%20%3Fciting_pub%20wdt%3AP2860%20%3Fitem%3B%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP1433%20%3FcitingJournal.%0A%20%20%7D%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2C%20en%2C%20ru%22.%0A%20%20%20%20%20%20%3Fitem%20rdfs%3Alabel%20%3FitemLabel%20.%0A%20%20%20%20%20%20%3FcitingJournal%20rdfs%3Alabel%20%3FcitingJournalLabel%20.%0A%20%20%7D%0A%7D%0AGROUP%20BY%20%3Fdoi%20%3FitemLabel%20%3FcitingJournalLabel%0AORDER%20BY%20%3FitemLabel%0A)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Список авторов журнала, у которых указан ORCID

Запрос ниже возвращает перечень авторов (P50 = author) статей (P1433 =
published in) из “Палеонтологического журнала”, имеющих атрибут ORCID
(P496).

**`Wikidata SPARQL`**

``` r
SELECT DISTINCT ?author_id ?orcid ?author
WHERE {
   ?item wdt:P1433 wd:Q246955.
   optional{
           ?item p:P50 ?author_statement .
           ?author_statement ps:P50 ?author_id .
           ?author_id wdt:P496 ?orcid. }
  SERVICE wikibase:label {
    bd:serviceParam wikibase:language "[AUTO_LANGUAGE], en, ru".
    ?author_id rdfs:label ?author .
  }
}
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/#SELECT%20DISTINCT%20%3Fauthor_id%20%3Forcid%20%3Fauthor%0AWHERE%20%7B%0A%20%20%20%3Fitem%20wdt%3AP1433%20wd%3AQ246955.%0A%20%20%20optional%7B%0A%20%20%20%20%20%20%20%20%20%20%20%3Fitem%20p%3AP50%20%3Fauthor_statement%20.%0A%20%20%20%20%20%20%20%20%20%20%20%3Fauthor_statement%20ps%3AP50%20%3Fauthor_id%20.%0A%20%20%20%20%20%20%20%20%20%20%20%3Fauthor_id%20wdt%3AP496%20%3Forcid.%20%7D%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2C%20en%2C%20ru%22.%0A%20%20%20%20%3Fauthor_id%20rdfs%3Alabel%20%3Fauthor%20.%0A%20%20%7D%0A%7D%0A)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Женщины-ученые с наградами, цитировавшие выбранный журнал

Запрос ниже возвращает перечень авторов (P50 = автор) работ, цитирующих
статьи (P2860 = cites work) из журнала “Молекулярная биология”, имеющих
награды (P166 = award received) и чей пол (P21 = gender) указан в
Википедии как женский (Q6581072). Для каждого автора запрос возвращает
объединенный перечень наград и значение идентификатора ORCID (при
наличии).

**`Wikidata SPARQL`**

``` r
SELECT ?authorLabel ?orcid ?awards
WITH {
  SELECT ?author 
    (GROUP_CONCAT(DISTINCT(?award); separator=" | ") AS ?awards)
  WHERE {
  ?work wdt:P1433 wd:Q4300349.
  ?reference_pub wdt:P2860 ?work.
  ?reference_pub wdt:P50 ?author .
  ?author p:P166 ?award_statement.
  ?award_statement ps:P166 ?award_.
  ?author wdt:P21 wd:Q6581072 .
    SERVICE wikibase:label {
      bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en" . 
      ?award_ rdfs:label ?award.
    } 
  }
GROUP BY ?author  
} AS %result
WHERE {
  INCLUDE %result 
   optional{?author wdt:P496 ?orcid .}
    SERVICE wikibase:label { 
           bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en" .
        ?author rdfs:label ?authorLabel.    
    }
 }
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/#SELECT%20%3FauthorLabel%20%3Forcid%20%3Fawards%0AWITH%20%7B%0A%20%20SELECT%20%3Fauthor%20%0A%20%20%20%20%28GROUP_CONCAT%28DISTINCT%28%3Faward%29%3B%20separator%3D%22%20%7C%20%22%29%20AS%20%3Fawards%29%0A%20%20WHERE%20%7B%0A%20%20%3Fwork%20wdt%3AP1433%20wd%3AQ4300349.%0A%20%20%3Freference_pub%20wdt%3AP2860%20%3Fwork.%0A%20%20%3Freference_pub%20wdt%3AP50%20%3Fauthor%20.%0A%20%20%3Fauthor%20p%3AP166%20%3Faward_statement.%0A%20%20%3Faward_statement%20ps%3AP166%20%3Faward_.%0A%20%20%3Fauthor%20wdt%3AP21%20wd%3AQ6581072%20.%0A%20%20%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22%20.%20%0A%20%20%20%20%20%20%3Faward_%20rdfs%3Alabel%20%3Faward.%0A%20%20%20%20%7D%20%0A%20%20%7D%0AGROUP%20BY%20%3Fauthor%20%20%0A%7D%20AS%20%25result%0AWHERE%20%7B%0A%20%20INCLUDE%20%25result%20%0A%20%20%20optional%7B%3Fauthor%20wdt%3AP496%20%3Forcid%20.%7D%0A%20%20%20%20SERVICE%20wikibase%3Alabel%20%7B%20%0A%09%20%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22%20.%0A%20%20%20%20%20%20%20%20%3Fauthor%20rdfs%3Alabel%20%3FauthorLabel.%09%0A%20%20%09%7D%0A%20%7D%0A)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Российские ученые, имеющие ORCID и статью в русскоязычной Wikipedia

**`Wikidata SPARQL`**

``` r
SELECT DISTINCT ?author ?authorLabel ?orcid ?article
  WHERE {
    ?author wdt:P31 wd:Q5; 
            wdt:P27 wd:Q159;
            wdt:P496 ?orcid.      
    ?article schema:about ?author;
             schema:isPartOf <https://ru.wikipedia.org/>.
SERVICE wikibase:label { 
    bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en" . }
}
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/#SELECT%20DISTINCT%20%3Fauthor%20%3FauthorLabel%20%3Forcid%20%3Farticle%0A%20%20WHERE%20%7B%0A%20%20%20%20%3Fauthor%20wdt%3AP31%20wd%3AQ5%3B%20%0A%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP27%20wd%3AQ159%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP496%20%3Forcid.%20%20%20%20%20%20%0A%20%20%20%20%3Farticle%20schema%3Aabout%20%3Fauthor%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fru.wikipedia.org%2F%3E.%0ASERVICE%20wikibase%3Alabel%20%7B%20%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22%20.%20%7D%0A%7D%0A)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Исследователи младше 30 лет, имеющие статью в англоязычной Wikipedia

Запрос ниже возвращает найденных в Wikidata людей, имеющих страницу в
англоязычной Wikipedia, чей род занятий (P106 = occupation) указан как
Q901 = scientist, и с указанной датой рождения, согласно которой возраст
этих ученых на 23 мая 2023 года не превышал 30 лет. Запрос исключает
людей, у которых присутствует значение атрибута P570 = date of death.

**`Wikidata SPARQL`**

``` r
SELECT ?sitelink ?itemLabel WHERE {
  ?item wdt:P106 wd:Q901;
        wdt:P31 wd:Q5;
        wdt:P569 ?born .
  FILTER (?born >= "1993-05-23T00:00:00Z"^^xsd:dateTime). 
  # exclude if there is a date of death
  MINUS {?item wdt:P570 []}    
  ?sitelink schema:about ?item ;
            schema:isPartOf <https://en.wikipedia.org/>.  
  SERVICE wikibase:label {
        bd:serviceParam wikibase:language "en"
   }.
}  
ORDER BY ?itemLabel
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/#SELECT%20%3Fsitelink%20%3FitemLabel%20WHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP106%20wd%3AQ901%3B%0A%20%20%20%20%20%20%20%20wdt%3AP31%20wd%3AQ5%3B%0A%20%20%20%20%20%20%20%20wdt%3AP569%20%3Fborn%20.%0A%20%20FILTER%20%28%3Fborn%20%3E%3D%20%221993-04-24T00%3A00%3A00Z%22%5E%5Exsd%3AdateTime%29.%20%0A%20%20%23%20exclude%20if%20there%20is%20a%20date%20of%20death%0A%20%20MINUS%20%7B%3Fitem%20wdt%3AP570%20%5B%5D%7D%20%20%20%20%0A%20%20%3Fsitelink%20schema%3Aabout%20%3Fitem%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fen.wikipedia.org%2F%3E.%20%20%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22en%22%0A%20%20%20%7D.%0A%7D%20%20%0AORDER%20BY%20%3FitemLabel%0A)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Исследователи, цитировавшие статьи из журнала со списком цитирующих и процитированных статей

Запрос находит список элементов Wikidata, соответствующих авторам статей
с DOI (P356), цитировавших статьи (также имеющие DOI) из журнала Russian
Journal of Organic Chemistry. Для каждого автора возвращаются ORCID,
список DOI цитирующих публикаций, список DOI и количество
процитированных статей из искомого журнала.

**`Wikidata SPARQL`**

``` r
SELECT DISTINCT ?citing_author ?citing_authorLabel 
     (GROUP_CONCAT(DISTINCT ?orcid; separator = "; ") as ?orcids_yes_sometimes_few)
     (GROUP_CONCAT(DISTINCT ?citing_doi; separator = "; ") as ?list_of_citing_dois)
     (COUNT(DISTINCT ?doi) AS ?n_dois)
     (GROUP_CONCAT(DISTINCT ?doi; separator = "; ") as ?list_of_cited_dois)
WHERE {
  ?item wdt:P1433 wd:Q3453520;
        wdt:P356 ?doi. 
  ?citing_work wdt:P2860 ?item; 
        wdt:P50 ?citing_author;
        wdt:P356 ?citing_doi.
 optional{?citing_author wdt:P496 ?orcid.} 
  SERVICE wikibase:label { 
    bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". 
    }      
  }
GROUP BY ?citing_authorLabel ?citing_author 
ORDER BY DESC(?n_dois)
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/index.html#SELECT%20DISTINCT%20%3Fciting_author%20%3Fciting_authorLabel%20%0A%20%20%20%20%20%28GROUP_CONCAT%28DISTINCT%20%3Forcid%3B%20separator%20%3D%20%22%3B%20%22%29%20as%20%3Forcids_yes_sometimes_few%29%0A%20%20%20%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fciting_doi%3B%20separator%20%3D%20%22%3B%20%22%29%20as%20%3Flist_of_citing_dois%29%0A%20%20%20%20%20%28COUNT%28DISTINCT%20%3Fdoi%29%20AS%20%3Fn_dois%29%0A%20%20%20%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fdoi%3B%20separator%20%3D%20%22%3B%20%22%29%20as%20%3Flist_of_cited_dois%29%0AWHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP1433%20wd%3AQ3453520%3B%0A%20%20%20%20%20%20%20%20wdt%3AP356%20%3Fdoi.%20%0A%20%20%3Fciting_work%20wdt%3AP2860%20%3Fitem%3B%20%0A%20%20%20%20%20%20%20%20wdt%3AP50%20%3Fciting_author%3B%0A%20%20%20%20%20%20%20%20wdt%3AP356%20%3Fciting_doi.%0A%20optional%7B%3Fciting_author%20wdt%3AP496%20%3Forcid.%7D%20%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%0A%20%20%20%20%7D%20%20%20%20%20%20%0A%20%20%7D%0AGROUP%20BY%20%3Fciting_authorLabel%20%3Fciting_author%20%0AORDER%20BY%20DESC%28%3Fn_dois%29%0A%0A)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Перечень организаций, сотрудники которых цитировали статьи из выбранного журнала

Запрос ниже возвращает перечень организаций, чьи сотрудники (P108 =
employer) в своих работах (P50 = author) цитировали (P2860 = cites work)
статьи из журнала “Вестник офтальмологии”. Для каждой организации
возвращается страна, количество процитированных публикаций из журнала
“Вестник офтальмологии” и их названия.

**`Wikidata SPARQL`**

``` r
SELECT DISTINCT ?citing_organizationLabel ?citing_countryLabel 
       (COUNT(DISTINCT ?item) AS ?n_items)
       (GROUP_CONCAT(DISTINCT ?itemLabel; separator = " | ") as ?list_of_items)
WHERE {
  ?item wdt:P1433 wd:Q27713783;
        rdfs:label ?itemLabel.
  FILTER (LANG (?itemLabel) = "en" ). 
  ?citing_work wdt:P2860 ?item; 
        wdt:P50 ?citing_author . 
  ?citing_author wdt:P108 ?citing_organization . 
  ?citing_organization wdt:P17 ?citing_country.
  SERVICE wikibase:label { 
    bd:serviceParam wikibase:language "en".
  }
  }
GROUP BY ?citing_organizationLabel ?citing_countryLabel
ORDER BY DESC (?n_items)
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/#SELECT%20DISTINCT%20%3Fciting_organizationLabel%20%3Fciting_countryLabel%20%0A%20%20%20%20%20%20%20%28COUNT%28DISTINCT%20%3Fitem%29%20AS%20%3Fn_items%29%0A%20%20%20%20%20%20%20%28GROUP_CONCAT%28DISTINCT%20%3FitemLabel%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Flist_of_items%29%0AWHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP1433%20wd%3AQ27713783%3B%0A%20%20%20%20%20%20%20%20rdfs%3Alabel%20%3FitemLabel.%0A%20%20FILTER%20%28LANG%20%28%3FitemLabel%29%20%3D%20%22en%22%20%29.%20%0A%20%20%3Fciting_work%20wdt%3AP2860%20%3Fitem%3B%20%0A%20%20%20%20%20%20%20%20wdt%3AP50%20%3Fciting_author%20.%20%0A%20%20%3Fciting_author%20wdt%3AP108%20%3Fciting_organization%20.%20%0A%20%20%3Fciting_organization%20wdt%3AP17%20%3Fciting_country.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22en%22.%0A%20%20%7D%0A%20%20%7D%0AGROUP%20BY%20%3Fciting_organizationLabel%20%3Fciting_countryLabel%0AORDER%20BY%20DESC%20%28%3Fn_items%29)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Статьи из журнала и процитировавшие их организации и страны

Запрос возвращает элементы Wikidata, соответствующие публикациям из
“Палеонтологического журнала”, которые были процитированы другими
публикациями (также имеющими записи в Wikidata). Для каждой статьи
искомого журнала, имеющей цитирование, приведено название статьи,
количество организаций публикаций,

**`Wikidata SPARQL`**

``` r
SELECT DISTINCT ?doi ?title 
    (COUNT(DISTINCT ?citing_work) AS ?n_cites)
    (GROUP_CONCAT(DISTINCT ?citing_organizationLabel; separator = "; ") as ?citing_orgs)
    (GROUP_CONCAT(DISTINCT ?citing_countryLabel; separator = "; ") as ?citing_countries)
WHERE {
  ?item wdt:P1433 wd:Q246955;
        wdt:P356 ?doi. 
  ?citing_work wdt:P2860 ?item; 
        wdt:P50 ?citing_author . 
  ?citing_author wdt:P108 ?citing_organization . 
  ?citing_organization wdt:P17 ?citing_country.
  SERVICE wikibase:label { 
    bd:serviceParam wikibase:language "en". 
    ?citing_organization rdfs:label ?citing_organizationLabel.
    ?citing_country rdfs:label ?citing_countryLabel.
    ?item rdfs:label ?title.
   }      
 }
GROUP BY ?doi ?title
ORDER BY DESC(?n_cited)
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/index.html#SELECT%20DISTINCT%20%3Fdoi%20%3Ftitle%20%0A%20%20%20%20%28COUNT%28DISTINCT%20%3Fciting_work%29%20AS%20%3Fn_cites%29%0A%20%20%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fciting_organizationLabel%3B%20separator%20%3D%20%22%3B%20%22%29%20as%20%3Fciting_orgs%29%0A%20%20%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fciting_countryLabel%3B%20separator%20%3D%20%22%3B%20%22%29%20as%20%3Fciting_countries%29%0AWHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP1433%20wd%3AQ246955%3B%0A%20%20%20%20%20%20%20%20wdt%3AP356%20%3Fdoi.%20%0A%20%20%3Fciting_work%20wdt%3AP2860%20%3Fitem%3B%20%0A%20%20%20%20%20%20%20%20wdt%3AP50%20%3Fciting_author%20.%20%0A%20%20%3Fciting_author%20wdt%3AP108%20%3Fciting_organization%20.%20%0A%20%20%3Fciting_organization%20wdt%3AP17%20%3Fciting_country.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22en%22.%20%0A%20%20%20%20%3Fciting_organization%20rdfs%3Alabel%20%3Fciting_organizationLabel.%0A%20%20%20%20%3Fciting_country%20rdfs%3Alabel%20%3Fciting_countryLabel.%0A%20%20%20%20%3Fitem%20rdfs%3Alabel%20%3Ftitle.%0A%20%20%20%7D%20%20%20%20%20%20%0A%20%7D%0AGROUP%20BY%20%3Fdoi%20%3Ftitle%0AORDER%20BY%20DESC%28%3Fn_cited%29%0A)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

#### Карта университетов Москвы, расположенных в \<=500 метрах от станций метро

Запрос возращает карту с расположением элементов Викиданных типа
университет (Q3918), расположенных (P625 = coordinate location) в
радиусе 0.5 км от станций метро (Q928830).

Для того, чтобы увидеть перечень результатов в виде таблицы, измените
\#defaultView в начале запроса на Table (или воспользуйтесь выпадающим
меню, расположенным над картой с левой стороны).

**`Wikidata SPARQL`**

``` r
#defaultView:Map
SELECT ?place ?placeLabel ?subwayLabel ?location WHERE
{ 
  ?subway wdt:P131+ wd:Q649;
          wdt:P31 wd:Q928830.
  ?subway wdt:P625 ?arcLoc .
  SERVICE wikibase:around {
      ?place wdt:P625 ?location .
      bd:serviceParam wikibase:center ?arcLoc .
      bd:serviceParam wikibase:radius "0.5" .
  }
    ?place wdt:P31 wd:Q3918.
  SERVICE wikibase:label {
    bd:serviceParam wikibase:language "ru" .
  }
}
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/index.html#%23defaultView%3AMap%0ASELECT%20%3Fplace%20%3FplaceLabel%20%3FsubwayLabel%20%3Flocation%20WHERE%0A%7B%20%0A%20%20%3Fsubway%20wdt%3AP131%2B%20wd%3AQ649%3B%0A%20%20%20%20%20%20%20%20%20%20wdt%3AP31%20wd%3AQ928830.%0A%20%20%3Fsubway%20wdt%3AP625%20%3FarcLoc%20.%0A%20%20SERVICE%20wikibase%3Aaround%20%7B%0A%20%20%20%20%20%20%3Fplace%20wdt%3AP625%20%3Flocation%20.%0A%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Acenter%20%3FarcLoc%20.%0A%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Aradius%20%220.5%22%20.%0A%20%20%7D%0A%20%20%20%20%3Fplace%20wdt%3AP31%20wd%3AQ3918.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22ru%22%20.%0A%20%20%7D%0A%7D%0A)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

## Практика – как вносить сведения в Wikidata?

Ответы на этот вопрос частично освещены в статьях:

-   [“Сервис Викиданные для научных
    журналов”](https://podpiska.rfbr.ru/materials/wikidata4journals/),
    (2023).

-   [“О профилях организаций в
    Wikidata”](https://openriro.github.io/posts/wikidata-profile/),
    (2022).

Можно выделить 3 подхода:

(а) “ручками”. Профиль журнала, главного редактора,
организации-учредителя быстрее всего поправить именно так. С помощью
поисковых запросов в интерфейсе Wikidata проверьте, существует ли уже
профиль (поиск по вариантам названия, ФИО, ORCID, ISSN). Если профиля
нет, смело нажимайте Creare a new item (Создать новый элемент) в меню
левой панели. При создании достаточно указать язык описания, название,
краткое описание и варианты названий (потом вы сможете изменить все эти
поля или добавить новые).

Порог входа – зарегистрироваться в Wikidata. При создании полей
ориентируйтесь на рекомендации в статьях выше и примеры оформления
других журналов.

(б) через специальные инструменты Wikidata. После преодоления порога в
50 правок пользователи аккаунтов старше 4 дней приобретают статус
[Autoconfirmed
Users](https://www.wikidata.org/wiki/Wikidata:Autoconfirmed_users) (в
рускоязычной версии статьи указан порог [в 15
правок](https://ru.wikipedia.org/wiki/%D0%92%D0%B8%D0%BA%D0%B8%D0%BF%D0%B5%D0%B4%D0%B8%D1%8F:%D0%90%D0%B2%D1%82%D0%BE%D0%BF%D0%BE%D0%B4%D1%82%D0%B2%D0%B5%D1%80%D0%B6%D0%B4%D1%91%D0%BD%D0%BD%D1%8B%D0%B5_%D1%83%D1%87%D0%B0%D1%81%D1%82%D0%BD%D0%B8%D0%BA%D0%B8)).
В любом случае этот порог преодолется незаметно при заполнении первых
карточек.

А далее в вашем распоряжении появятся множество инструментов для
редактирования Викиданных, из которых кратко рассмотрим два: [Quick
Statements](https://quickstatements.toolforge.org) и
[SourceMD](https://sourcemd.toolforge.org/index_old.php), которые чуть
подробнее рассмотрим ниже.

(в) через API-интерфейс [Swagger API
документация](https://doc.wikimedia.org/Wikibase/master/js/rest-api/).
Если вы умеете пользоваться REST API, дополнительные комментарии не
требуются. Если же это ваше первое столкновение с методами REST API,
прежде чем править Викиданные, хорошенько изучите инструкции, начните
тренировки с безопасного метода (GET) и потом “поиграйте в
[песочнице”](https://www.wikidata.org/wiki/Q4115189), в которую можно
вносить правки.

------------------------------------------------------------------------

#### :pushpin: Quick Statements

-   <https://quickstatements.toolforge.org>

Этот сервис позволяет вносит изменения в Wikidata без опыта работы с API
и головоломными :grimacing: механизмами авторизации.

-   [Подробное описание работы с QuickStatements на английском
    языке](https://www.wikidata.org/wiki/Help:QuickStatements)

Для работы пользователь должен иметь статус Autoconfirmed user,
предварительно авторизоваться в Wikidata и дать разрешения всплывающим
запросам. Если после авторизации вы видите имя своего пользователя в
правом углу и после нажатия на New Batch видите поле для ввода, значит
интерфейс готов к работе. За кнопкой с именем пользователя скрывается
приятный сюрприз :wink: для, кто умеет использовать API.

**Небольшой пример:**

Внесем в карточку пользователя Q118779563 2 новых свойства:
идентификатор автора в OpenAlex. Синтаксис QuickStatements очень прост –
в одной строке, через табуляцию или знак “\|”, перечисляются
entity\|property\|value, что для нашей задачи приводит к строкам
следующего вида:

``` r
Q118779563|P10283|"A2638483588"
```

Нажимаем Import V1 Commands, в открывшемся интерфейсе проверяем, что
будет сформировано, после чего нажимаем Run in background (система
предложить назвать данный набор правок. Например, “OA id for
Q118779563”). Если наверху появится Status DONE и индикатор прогресса
целиком зеленый и показывает 100%, значит, результат достигнут.

Проверяем:

*способ 0*

Открыв карточку [Q118779563](https://www.wikidata.org/wiki/Q118779563)

*способ 1*

Поиском A2638483588 в интерфейсе Wikidata

*способ 2*

**`Wikidata SPARQL`**

``` r
SELECT ?person ?openalex_id
   WHERE {
     VALUES ?person {wd:Q118779563}
     ?person wdt:P10283 ?openalex_id.
     }
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/index.html#SELECT%20%3Fperson%20%3Fopenalex_id%0A%20%20%20WHERE%20%7BVALUES%20%3Fperson%20%7Bwd%3AQ118779563%7D%0A%20%20%20%20%20%3Fperson%20wdt%3AP10283%20%3Fopenalex_id.%0A%20%7D)

*способ 3*

**`Wikidata API`**

> [`https://www.wikidata.org/w/rest.php/wikibase/v0/entities/items/Q118779563/statements?property=P10283`](https://www.wikidata.org/w/rest.php/wikibase/v0/entities/items/Q118779563/statements?property=P10283)

------------------------------------------------------------------------

#### :pushpin: SourceMD

-   [Новая версия](https://sourcemd.toolforge.org/) - (*прим. у автора
    капризничает с авторизацией*).

-   [Старая версия](https://sourcemd.toolforge.org/index_old.php)
    :point_left:

Этот сервис многократно облегчает задачу по переносу метаданных статей
из CrossRef в Викиданные.

-   вносим список DOI (1 doi в строке)
-   нажимаем Check source
-   сервис проверяет по DOI наличие статей в Wikidata.

Если публикация уже присутствует в Wikidata, то сверху над полем
появится формулировка вида

> Other sources with these identifiers exist: Q…. Trying to update
> values of Q….; this will not change existing ones.

для отсутствующих предлагает внести базовые сведения в формате Quick
Statements (см. :point_up:), с той разницей, что в качестве разделителя
вместо \| используется табуляций (оба варианта подходят для
QuickStatements).

Пример добавления статьи 10.24069/SEP-22-40

``` r
CREATE
LAST    P356    "10.24069/SEP-22-40"
LAST    P31 Q13442814
LAST    P1476   en:"Tabular form of description of statistical methods and programs in scientific publications"
LAST    Len "Tabular form of description of statistical methods and programs in scientific publications"
LAST    P433    "2"
LAST    P304    "182-184"
LAST    P478    "7"
LAST    P577    +2023-04-14T00:00:00Z/11
LAST    P1433   Q96728083
LAST    P2093   "N. N. Khromov-Borisov" P1545   "1"
```

Если ввести несколько DOI, то сервис вернет фрагменты для отдельных
статей, расположенные друг над другом. Блок каждой статьи начинается с
CREATE, который “дает команду” создать запись, к которой будут применены
инструкции в следующих строках, начинающихся с LAST.

Какие атрибуты будут созданы?

-   P31 (тип элемента) = scholarly article
    [Q13442814](https://www.wikidata.org/wiki/Q13442814)

-   P1476 (тип элемента) =
    [title](https://www.wikidata.org/wiki/Property:P1476), с указанием
    языка (en)

-   Len - это Label на английском, который отражается в заголовках
    Wikidata карточек.

-   P478 (том) = [volume](https://www.wikidata.org/wiki/Property:P478)

-   P433 (выпуск) = [issue](https://www.wikidata.org/wiki/Property:P433)

-   P304 (страницы) =
    [pages](https://www.wikidata.org/wiki/Property:P304)

-   P577 (дата публикации) = [publication
    date](https://www.wikidata.org/wiki/Property:P577)

-   P1433 (опубликовано в) = [published
    in](https://www.wikidata.org/wiki/Property:P1433). :warning:
    Поскольку в Wikidata уже существует карточка журнала с указанием
    ISSN и в метаданных CrossRef есть ISSN, то атрибут P1433 сразу
    связывает статьи с записью журнала
    [Q96728083](https://www.wikidata.org/wiki/Q96728083).

-   P2093 (строка с указанием имени автора) = [author
    string](https://www.wikidata.org/wiki/Property:P2093) с указанием
    P1545 (порядковый номер автора).

Обратите внимание, что будет создана не связь с карточкой автора (сервис
не распознает авторов по фамилии), а только текстовое значение.

:warning: если вы вносите статьи конкретного автора и у него уже создана
карточка в Wikidata, тогда можно прямо в окне SourceMD добавить ещё одну
строку (прямо под LAST P2093…) с инструкцией вида
`LAST P50 {Wikidata ID автора} P1545...`

Получится вот так

``` r
CREATE
LAST    P356    "10.24069/SEP-22-40"
LAST    P31 Q13442814
LAST    P1476   en:"Tabular form of description of statistical methods and programs in scientific publications"
LAST    Len "Tabular form of description of statistical methods and programs in scientific publications"
LAST    P433    "2"
LAST    P304    "182-184"
LAST    P478    "7"
LAST    P577    +2023-04-14T00:00:00Z/11
LAST    P1433   Q96728083
LAST    P2093   "N. N. Khromov-Borisov" P1545   "1"
LAST    P50 Q70155088   P1545   "1"
```

Нажимаем кнопку Open in Quick Statements, в открывшемся интерфейсе
проверяем, что будет сформировано, после чего нажимаем Run in background
(система предложить назвать данный набор правок. Например, “article 1”).
Если наверху появится Status DONE и индикатор прогресса будет показывать
100%, то всё – статья внесена в Wikidata.

Как найти созданную статью?

В карточке автора статья не отражается, поскольку это не статья является
атрибутом автора, а наоборот – автор выступает в качестве атрибута
статьи (спасибо, что не
[AMDG](https://ru.wikipedia.org/wiki/Ad_majorem_Dei_gloriam) по
умолчанию).

*способ 1*

Поиском 10.24069/SEP-22-40 в интерфейсе Wikidata

*Способ 2*

Выполнив поиск по DOI в Wikidata или с помощью SPARQL запроса (пример
ниже).

``` r
SELECT ?article ?doi 
   WHERE {
     VALUES ?doi {"10.24069/SEP-22-40"}
     ?article wdt:P356 ?doi.
     }
```

[отправить через Wikidata Query
Service](https://query.wikidata.org/#SELECT%20%3Farticle%20%3Fdoi%20%0A%20WHERE%20%7B%0A%20%20%20%20VALUES%20%3Fdoi%20%7B%2210.24069%2FSEP-22-40%22%7D%0A%20%20%20%20%3Farticle%20wdt%3AP356%20%3Fdoi.%0A%7D)

Идентификатор созданной статьи –
[Q118798976](https://www.wikidata.org/wiki/Q118798976).

------------------------------------------------------------------------

Итак, оптимальная стратегия примерно следующая:

1)  регистрируем профиль в Wikidata

2)  создаем/редактируем вручную индивидуальные карточки журналов,
    организации-учредителя, редактора, пока не достигнем статус
    Autoconfirmed (отражается в меню Preferences Wikidata / раздел Basic
    information \> Member of groups).

3)  проверяем готовность к работе QuickStatements (разрешения)

4)  вносим DOI через SourceMD

5)  вносим атрибуты статей и авторов через QuickStatements (их можно
    готовить в любом текстовом или колоночном редакторе).

Созданными профилями любуемся в сервисе
[Scholia](https://scholia.toolforge.org).

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

## :pushpin: Приложение 1. Энциклопедия Руниверсалис

На момент подготовки статьи на сайте [Энциклопедии
Руниверсалис](https://%D1%80%D1%83%D0%BD%D0%B8.%D1%80%D1%84/) автору не
удалось найти документацию API, но администраторы ТГ-канала указали, что
MediaWiki API работает. Удалось обнаружить работающий MediaWiki Action
API

#### Информация о статье

Краткий запрос, возвращающий только id статьи:

> [`https://руни.рф/api.php?action=query&titles=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&format=json`](https://руни.рф/api.php?action=query&titles=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&format=json)

Запрос ниже возвращает более детальную json-структуру, из которой легко
извлечь текст, категории (categories), ссылки на страницы (links),
ссылка на внешние страницы (externallinks), перечень изображений
(images), секций (sections), шаблонов (template), интер-вики ссылок
(iwlinks – здесь ссылки на оригинальную Википедию и другие Викисервисы).

> [`https://руни.рф/api.php?action=parse&page=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&format=json`](https://руни.рф/api.php?action=parse&page=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&format=json)

По сравнению с оригиналом (далее под оригиналом подразумевается
MediaWiki API в оригинальной Wikipedia) отсутствуют идентификатор
соответствующего статье элемента Викиданных (wikibase_item) и ссылки на
языковые версии статей (раздел есть, но автор не встретил примеров
статей, где он был бы заполнен).

#### Извлечь разделы статьи

Возвращает перечень разделов страницы, их размер, порядковые номера и
названия внутренних ссылок. \>
[`https://руни.рф/api.php?action=parse&page=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&prop=sections&format=json`](https://руни.рф/api.php?action=parse&page=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&prop=sections&format=json)

Получив сведения из запроса выше, можно извлечь отдельные разделы в
форматах wikitext или parsetree.

> [`https://руни.рф/api.php?action=parse&page=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&prop=wikitext|parsetree&section=5&format=json`](https://руни.рф/api.php?action=parse&page=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&prop=wikitext%7Cparsetree&section=5&format=json)

#### Извлечь категории статьи

> [`https://руни.рф/api.php?action=parse&page=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&prop=categories&format=json`](https://руни.рф/api.php?action=parse&page=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&prop=categories&format=json)

Некоторые категории отмечены как hidden. Там много забавного – например,
вышеприведенная статья о Кубинской революции отнесена к скрытой
категории “Статьи_к\_проверке:ЛГБТ_и\_Ко”. К этой категории на 26 июля
2023 года была отнесена [4281
статья](https://руни.рф/index.php?title=%D0%9A%D0%B0%D1%82%D0%B5%D0%B3%D0%BE%D1%80%D0%B8%D1%8F:%D0%A1%D1%82%D0%B0%D1%82%D1%8C%D0%B8_%D0%BA_%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B5:%D0%9B%D0%93%D0%91%D0%A2_%D0%B8_%D0%9A%D0%BE)
– туда попали статьи о квиритском праве, Иоанне Павле II, Джоне Керри,
миндалевидном теле, движении “Наши” и многом другом, требующем
“проверки” (см. запрос ниже).

> [`https://руни.рф/api.php?cmtitle=Category:Статьи_к_проверке:ЛГБТ_и_Ко&action=query&list=categorymembers&cmlimit=500&cmprop=title|timestamp&format=json`](https://руни.рф/api.php?cmtitle=Category:Статьи_к_проверке:ЛГБТ_и_Ко&action=query&list=categorymembers&cmlimit=500&cmprop=title%7Ctimestamp&format=json)

#### История правок статьи

Запрос ниже возвращает информацию о 10 правках, внесенных после 01
декабря 2022 года в статью о бывшем словацком президенте (поскольку его
имя Андрей Киска, разумеется, статья тоже попала в вышеупомянутую
категорию).

> [`https://руни.рф/api.php?action=query&titles=%D0%9A%D0%B8%D1%81%D0%BA%D0%B0,_%D0%90%D0%BD%D0%B4%D1%80%D0%B5%D0%B9&prop=revisions&rvslots=main&rvlimit=10&rvdir=newer&rvstart=2022-12-01T00:00:00Z&rvprop=ids|flags|timestamp|user|userid|size|contentmodel|comment|parsedcomment|content|tags&format=json`](https://руни.рф/api.php?action=query&titles=%D0%9A%D0%B8%D1%81%D0%BA%D0%B0,_%D0%90%D0%BD%D0%B4%D1%80%D0%B5%D0%B9&prop=revisions&rvslots=main&rvlimit=10&rvdir=newer&rvstart=2022-12-01T00:00:00Z&rvprop=ids%7Cflags%7Ctimestamp%7Cuser%7Cuserid%7Csize%7Ccontentmodel%7Ccomment%7Cparsedcomment%7Ccontent%7Ctags&format=json)

#### Список пользователей, которые правили страницу

Запрос ниже возвращает список пользователей, которые редактировали
статью о Крыме.

> [`https://руни.рф/api.php?action=query&titles=%D0%9A%D1%80%D1%8B%D0%BC&prop=contributors&pclimit=200&format=json`](https://руни.рф/api.php?action=query&titles=%D0%9A%D1%80%D1%8B%D0%BC&prop=contributors&pclimit=200&format=json).

Можно добавить &pcgroup=bot, чтобы получить список редакторов-ботов.

#### Список всех правок пользователя

Запрос ниже возвращает в формате json правки пользователя [Sergio «El
Profesor»
Marquina](https://руни.рф/index.php/%D0%9E%D0%B1%D1%81%D1%83%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5_%D1%83%D1%87%D0%B0%D1%81%D1%82%D0%BD%D0%B8%D0%BA%D0%B0:Sergio_%C2%ABEl_Profesor%C2%BB_Marquina).

> [`https://руни.рф/api.php?action=query&list=allrevisions&arvuser=Sergio%20%C2%ABEl%20Profesor%C2%BB%20Marquina&arvslots=*&arvprop=ids|flags|timestamp|user|userid|size|contentmodel|comment|parsedcomment|tags&format=json`](https://руни.рф/api.php?action=query&list=allrevisions&arvuser=Sergio%20%C2%ABEl%20Profesor%C2%BB%20Marquina&arvslots=*&arvprop=ids%7Cflags%7Ctimestamp%7Cuser%7Cuserid%7Csize%7Ccontentmodel%7Ccomment%7Cparsedcomment%7Ctags&format=json)

Для получения текста правок добавьте в аргумент arvprop значение
content.

#### Поиск статей, цитирующих внешний web-сайт

Можно искать ссылки только в статьях определенного типа, используя
выражение `&eunamespace=...` и определенные значения (0 – статьи, 1 –
Talk:Page, 2 – Профили пользователей, 3 – личные User talk страницы).

Запрос ниже возвращает перечень статей (namespace = 0), в которых
присутствуют гиперссылки на сайт издательства “Медиасфера”.

> [`https://руни.рф/api.php?action=query&format=json&list=exturlusage&euquery=www.mediasphera.ru&eunamespace=0`](https://руни.рф/api.php?action=query&format=json&list=exturlusage&euquery=www.mediasphera.ru&eunamespace=0)

#### Поиск статей, цитирующих выбранную страницу

Запрос ниже возвращает перечень статей, в которых присутствует
гиперссылка на статью о Кубинской революции.

> [`https://руни.рф/api.php?action=query&titles=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&prop=linkshere&lhlimit=200&lhnamespace=0&format=json`](https://руни.рф/api.php?action=query&titles=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&prop=linkshere&lhlimit=200&lhnamespace=0&format=json)

#### Гиперссылки из статьи, ведущие на другие статьи энциклопедии

Запрос ниже возвращает перечень статей энциклопедии, на которые
ссылается выбранная статья.

> [`https://руни.рф/api.php?action=parse&page=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&prop=links&format=json`](https://руни.рф/api.php?action=parse&page=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&prop=links&format=json)

#### Ссылки на внешние сайты с выбранной страницы

> [`https://руни.рф/api.php?action=query&titles=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&prop=extlinks&ellimit=500&elexpandurl=true&format=json`](https://руни.рф/api.php?action=query&titles=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&prop=extlinks&ellimit=500&elexpandurl=true&format=json)

Можно объединить ссылки с внутренними (на страницы энциклопедии), указав
`prop=extlinks|links`.

**\[Альтернативный способ\]**

> [`https://руни.рф/api.php?action=parse&page=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&prop=externallinks&format=json`](https://руни.рф/api.php?action=parse&page=%D0%9A%D1%83%D0%B1%D0%B8%D0%BD%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B2%D0%BE%D0%BB%D1%8E%D1%86%D0%B8%D1%8F&prop=externallinks&format=json)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

## :pushpin: Приложение 2. РУВИКИ

На момент подготовки материала сайт [РУВИКИ](https://ru.ruwiki.ru/)
работал в бета-версии. Автору не удалось найти на сайте документации
API, но поскольку РУВИКИ сделана на базе MediaWiki, то удалось
обнаружить работающие MediaWiki Action API и MediaWiki REST API.

#### Информация о статье

> [`https://ru.ruwiki.ru/w/api.php?action=query&titles=Весёлый Роджер&format=json`](https://ru.ruwiki.ru/w/api.php?action=query&titles=%D0%92%D0%B5%D1%81%D1%91%D0%BB%D1%8B%D0%B9_%D0%A0%D0%BE%D0%B4%D0%B6%D0%B5%D1%80&format=json)

Запрос ниже возвращает более детальную json-структуру, из которой легко
извлечь текст, категории (categories), ссылки на страницы (links),
ссылка на внешние страницы (externallinks), перечень изображений
(images), секций (sections), шаблонов (template), интер-вики ссылок
(iwlinks – здесь ссылки на оригинальную Википедию и другие Викисервисы),
идентификатор элемента Викиданных, соответствующего статье
(wikibase_item в разделе properties)

> [`https://ru.ruwiki.ru/w/api.php?action=parse&page=Весёлый Роджер&format=json`](https://ru.ruwiki.ru/w/api.php?action=parse&page=%D0%92%D0%B5%D1%81%D1%91%D0%BB%D1%8B%D0%B9_%D0%A0%D0%BE%D0%B4%D0%B6%D0%B5%D1%80&format=json)

На 03.08.2023 ссылки на все языковые версии статьи (раздел langlinks)
ведут на ru.ruwiki.ru и не функционируют (пример:
<https://ru.ruwiki.ru/wiki/Nl:Jolly_Roger>).

Версия MediWiki REST API

> [`https://ru.ruwiki.ru/w/rest.php/v1/page/Весёлый Роджер`](https://ru.ruwiki.ru/w/rest.php/v1/page/%D0%92%D0%B5%D1%81%D1%91%D0%BB%D1%8B%D0%B9_%D0%A0%D0%BE%D0%B4%D0%B6%D0%B5%D1%80)

#### Извлечь разделы статьи

Возвращает перечень разделов страницы, их размер, порядковые номера и
названия внутренних ссылок.

> [`https://ru.ruwiki.ru/w/api.php?action=parse&page=Весёлый Роджер&prop=sections&format=json`](https://ru.ruwiki.ru/w/api.php?action=parse&page=%D0%92%D0%B5%D1%81%D1%91%D0%BB%D1%8B%D0%B9%20%D0%A0%D0%BE%D0%B4%D0%B6%D0%B5%D1%80&prop=sections&format=json)

Получив сведения из запроса выше, можно извлечь отдельные разделы в
форматах wikitext или parsetree.

> [`https://ru.ruwiki.ru/w/api.php?action=parse&page=Весёлый Роджер&prop=wikitext|parsetree&section=2&format=json`](https://ru.ruwiki.ru/w/api.php?action=parse&page=%D0%92%D0%B5%D1%81%D1%91%D0%BB%D1%8B%D0%B9%20%D0%A0%D0%BE%D0%B4%D0%B6%D0%B5%D1%80&prop=wikitext%7Cparsetree&section=2&format=json)

#### Извлечь категории статьи

> [`https://ru.ruwiki.ru/w/api.php?action=parse&page=Весёлый Роджер&prop=categories&format=json`](https://ru.ruwiki.ru/w/api.php?action=parse&page=%D0%92%D0%B5%D1%81%D1%91%D0%BB%D1%8B%D0%B9%20%D0%A0%D0%BE%D0%B4%D0%B6%D0%B5%D1%80&prop=categories&format=json)

Найти все статьи по категории

> [`https://ru.ruwiki.ru/w/api.php?cmtitle=Category:Пиратство&action=query&list=categorymembers&cmlimit=100&cmprop=title|timestamp&format=json`](https://ru.ruwiki.ru/w/api.php?cmtitle=Category:%D0%9F%D0%B8%D1%80%D0%B0%D1%82%D1%81%D1%82%D0%B2%D0%BE&action=query&list=categorymembers&cmlimit=100&cmprop=title%7Ctimestamp&format=json)

#### История правок статьи

Запрос ниже возвращает информацию о 10 правках, внесенных после 01
декабря 2022 года в статью о Весёлом Роджере.

> [`https://ru.ruwiki.ru/w/api.php?action=query&titles=Пиратство Роджер&prop=revisions&rvslots=main&rvlimit=10&rvdir=newer&rvstart=2022-12-01T00:00:00Z&rvprop=ids|flags|timestamp|user|userid|size|contentmodel|comment|parsedcomment|content|tags&format=json`](https://ru.ruwiki.ru/w/api.php?action=query&titles=%D0%9F%D0%B8%D1%80%D0%B0%D1%82%D1%81%D1%82%D0%B2%D0%BE&prop=revisions&rvslots=main&rvlimit=10&rvdir=newer&rvstart=2022-12-01T00:00:00Z&rvprop=ids%7Cflags%7Ctimestamp%7Cuser%7Cuserid%7Csize%7Ccontentmodel%7Ccomment%7Cparsedcomment%7Ccontent%7Ctags&format=json)

#### Список пользователей, которые правили страницу

Запрос ниже возвращает список пользователей, которые редактировали
статью о Крыме.

> [`https://ru.ruwiki.ru/w/api.php?action=query&titles=%D0%9A%D1%80%D1%8B%D0%BC&prop=contributors&pclimit=200&format=json`](https://ru.ruwiki.ru/w/api.php?action=query&titles=%D0%9A%D1%80%D1%8B%D0%BC&prop=contributors&pclimit=200&format=json).

Чтобы получить список редакторов-ботов к запросу необходимо добавить
&pcgroup=bot.

#### Список всех правок пользователя

Запрос ниже возвращает в формате json правки пользователя
[Beginner67](https://ru.ruwiki.ru/w/index.php?title=%D0%A3%D1%87%D0%B0%D1%81%D1%82%D0%BD%D0%B8%D0%BA:Beginner67),
чей профиль пока в системе не отражается (beta есть beta.

> [`https://ru.ruwiki.ru/w/api.php?action=query&list=allrevisions&arvuser=Beginner67&arvslots=*&arvprop=ids|flags|timestamp|user|userid|size|contentmodel|comment|parsedcomment|tags&format=json`](https://ru.ruwiki.ru/w/api.php?action=query&list=allrevisions&arvuser=Beginner67&arvslots=*&arvprop=ids%7Cflags%7Ctimestamp%7Cuser%7Cuserid%7Csize%7Ccontentmodel%7Ccomment%7Cparsedcomment%7Ctags&format=json)

Для получения текста правок добавьте в аргумент arvprop значение
content.

#### Поиск статей, цитирующих внешний web-сайт

Можно искать ссылки только в статьях определенного типа, используя
выражение `&eunamespace=...` и определенные значения (0 – статьи, 1 –
Talk:Page, 2 – Профили пользователей, 3 – личные User talk страницы).

Запрос ниже возвращает перечень статей (namespace = 0), в которых
присутствуют гиперссылки на сайт издательства “Медиасфера”.

> [`https://ru.ruwiki.ru/w/api.php?action=query&list=exturlusage&euquery=www.mediasphera.ru&eunamespace=0&format=json`](https://ru.ruwiki.ru/w/api.php?action=query&list=exturlusage&euquery=www.mediasphera.ru&eunamespace=0&format=json)

#### Поиск статей, цитирующих выбранную страницу

Запрос ниже возвращает перечень статей, в которых присутствует
гиперссылка на статью о Кубинской революции. \>
[`https://ru.ruwiki.ru/w/api.php?action=query&titles=Изгнание_евреев_из_Испании&prop=linkshere&lhlimit=200&lhnamespace=0&format=json`](https://ru.ruwiki.ru/w/api.php?action=query&titles=%D0%98%D0%B7%D0%B3%D0%BD%D0%B0%D0%BD%D0%B8%D0%B5_%D0%B5%D0%B2%D1%80%D0%B5%D0%B5%D0%B2_%D0%B8%D0%B7_%D0%98%D1%81%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8&prop=linkshere&lhlimit=200&lhnamespace=0&format=json)

#### Гиперссылки из статьи, ведущие на другие статьи энциклопедии

Запрос ниже возвращает перечень статей энциклопедии, на которые
ссылается выбранная статья.

> [`https://ru.ruwiki.ru/w/api.php?action=query&titles=Изгнание_евреев_из_Испании&prop=links&format=json`](https://ru.ruwiki.ru/w/api.php?action=query&titles=%D0%98%D0%B7%D0%B3%D0%BD%D0%B0%D0%BD%D0%B8%D0%B5_%D0%B5%D0%B2%D1%80%D0%B5%D0%B5%D0%B2_%D0%B8%D0%B7_%D0%98%D1%81%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8&prop=links&format=json)

#### Ссылки на внешние сайты с выбранной страницы

> [`https://ru.ruwiki.ru/w/api.php?action=query&titles=Изгнание_евреев_из_Испании&prop=extlinks&ellimit=500&elexpandurl=true&format=json`](https://ru.ruwiki.ru/w/api.php?action=query&titles=%D0%98%D0%B7%D0%B3%D0%BD%D0%B0%D0%BD%D0%B8%D0%B5_%D0%B5%D0%B2%D1%80%D0%B5%D0%B5%D0%B2_%D0%B8%D0%B7_%D0%98%D1%81%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8&prop=extlinks&ellimit=500&elexpandurl=true&format=json)

Можно объединить ссылки с внутренними (на страницы энциклопедии), указав
`prop=extlinks|links`.

**\[Альтернативный способ\]**

> [`https://ru.ruwiki.ru/w/api.php?action=parse&page=Изгнание_евреев_из_Испании&prop=externallinks&format=json`](https://ru.ruwiki.ru/w/api.php?action=parse&page=%D0%98%D0%B7%D0%B3%D0%BD%D0%B0%D0%BD%D0%B8%D0%B5_%D0%B5%D0%B2%D1%80%D0%B5%D0%B5%D0%B2_%D0%B8%D0%B7_%D0%98%D1%81%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8&prop=externallinks&format=json)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

## :pushpin: Приложение 3. Циклопедия

На момент подготовки статьи на сайте
[Циклопедии](https://cyclowiki.org/) автору не удалось найти
документацию API, но поскольку Циклопедия сделана на базе MediaWiki, то
удалось обнаружить работающие MediaWiki Action API и MediaWiki REST API.

#### Информация о статье

> [`https://cyclowiki.org/w/api.php?action=query&titles=Китайская кошка&format=json`](https://cyclowiki.org/w/api.php?action=query&titles=%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F_%D0%BA%D0%BE%D1%88%D0%BA%D0%B0&format=json)

Запрос ниже возвращает более детальную json-структуру, из которой легко
извлечь текст, категории (categories), ссылки на страницы (links),
ссылка на внешние страницы (externallinks), перечень изображений
(images), секций (sections), шаблонов (template), интер-вики ссылок
(iwlinks – здесь ссылки на оригинальную Википедию и другие Викисервисы).

> [`https://cyclowiki.org/w/api.php?action=parse&page=Китайская кошка&format=json`](https://cyclowiki.org/w/api.php?action=parse&page=%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F_%D0%BA%D0%BE%D1%88%D0%BA%D0%B0&format=json)

По сравнению с оригиналом (далее под оригиналом подразумевается
MediaWiki API в оригинальной Wikipedia) отсутствуют идентификатор
соответствующего статье элемента Викиданных (wikibase_item) и ссылки на
языковые версии статей (раздел есть, но автор не встретил примеров
статей, где он был бы заполнен).

Версия MediWiki REST API

> [`https://cyclowiki.org/w/rest.php/v1/page/Китайская кошка`](https://cyclowiki.org/w/rest.php/v1/page/%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F_%D0%BA%D0%BE%D1%88%D0%BA%D0%B0)

#### Извлечь разделы статьи

Возвращает перечень разделов страницы, их размер, порядковые номера и
названия внутренних ссылок. \>
[`https://cyclowiki.org/w/api.php?action=parse&page=Китайская кошка&prop=sections&format=json`](https://cyclowiki.org/w/api.php?action=parse&page=%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F_%D0%BA%D0%BE%D1%88%D0%BA%D0%B0&prop=sections&format=json)

Получив сведения из запроса выше, можно извлечь отдельные разделы в
форматах wikitext или parsetree.

> [`https://cyclowiki.org/w/api.php?action=parse&page=Китайская кошка&prop=wikitext|parsetree&section=5&format=json`](https://cyclowiki.org/w/api.php?action=parse&page=%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F_%D0%BA%D0%BE%D1%88%D0%BA%D0%B0&prop=wikitext%7Cparsetree&section=5&format=json)

#### Извлечь категории статьи

> [`https://cyclowiki.org/w/api.php?action=parse&page=Китайская кошка&prop=categories&format=json`](https://cyclowiki.org/w/api.php?action=parse&page=%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F_%D0%BA%D0%BE%D1%88%D0%BA%D0%B0&prop=categories&format=json)

Найти все статьи по категории

> [`https://cyclowiki.org/w/api.php?cmtitle=Category:Сады и парки России&action=query&list=categorymembers&cmlimit=100&cmprop=title|timestamp&format=json`](https://cyclowiki.org/w/api.php?cmtitle=Category:%D0%A1%D0%B0%D0%B4%D1%8B%20%D0%B8%20%D0%BF%D0%B0%D1%80%D0%BA%D0%B8%20%D0%A0%D0%BE%D1%81%D1%81%D0%B8%D0%B8&action=query&list=categorymembers&cmlimit=100&cmprop=title%7Ctimestamp&format=json)

#### История правок статьи

Запрос ниже возвращает информацию о 10 правках, внесенных после 01
декабря 2022 года в статью о Китайской кошке.

> [`https://cyclowiki.org/w/api.php?action=query&titles=Китайская кошка&prop=revisions&rvslots=main&rvlimit=10&rvdir=newer&rvstart=2022-12-01T00:00:00Z&rvprop=ids|flags|timestamp|user|userid|size|contentmodel|comment|parsedcomment|content|tags&format=json`](https://cyclowiki.org/w/api.php?action=query&titles=%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F%20%D0%BA%D0%BE%D1%88%D0%BA%D0%B0&prop=revisions&rvslots=main&rvlimit=10&rvdir=newer&rvstart=2022-12-01T00:00:00Z&rvprop=ids%7Cflags%7Ctimestamp%7Cuser%7Cuserid%7Csize%7Ccontentmodel%7Ccomment%7Cparsedcomment%7Ccontent%7Ctags&format=json)

#### Список пользователей, которые правили страницу

Запрос ниже возвращает список пользователей, которые редактировали
статью о Китайской кошке.

> [`https://cyclowiki.org/w/api.php?action=query&titles=Китайская кошка&prop=contributors&pclimit=200&format=json`](https://cyclowiki.org/w/api.php?action=query&titles=%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F%20%D0%BA%D0%BE%D1%88%D0%BA%D0%B0&prop=contributors&pclimit=200&format=json).

Чтобы получить список редакторов-ботов к запросу необходимо добавить
&pcgroup=bot.

#### Список всех правок пользователя

Запрос ниже возвращает в формате json правки пользователя
[Serebr](https://cyclowiki.org/wiki/%D0%A3%D1%87%D0%B0%D1%81%D1%82%D0%BD%D0%B8%D0%BA:Serebr).

> [`https://cyclowiki.org/w/api.php?action=query&list=allrevisions&arvuser=Serebr&arvslots=*&arvprop=ids|flags|timestamp|user|userid|size|contentmodel|comment|parsedcomment|tags&format=json`](https://cyclowiki.org/w/api.php?action=query&list=allrevisions&arvuser=Serebr&arvslots=*&arvprop=ids%7Cflags%7Ctimestamp%7Cuser%7Cuserid%7Csize%7Ccontentmodel%7Ccomment%7Cparsedcomment%7Ctags&format=json)

Для получения текста правок добавьте в аргумент arvprop значение
content.

#### Поиск статей, цитирующих внешний web-сайт

Можно искать ссылки только в статьях определенного типа, используя
выражение `&eunamespace=...` и определенные значения (0 – статьи, 1 –
Talk:Page, 2 – Профили пользователей, 3 – личные User talk страницы).

Запрос ниже возвращает перечень статей (namespace = 0), в которых
присутствуют гиперссылки на сайт издательства “Медиасфера”.

> [`https://cyclowiki.org/w/api.php?action=query&list=exturlusage&euquery=www.mediasphera.ru&eunamespace=0&format=json`](https://cyclowiki.org/w/api.php?action=query&list=exturlusage&euquery=www.mediasphera.ru&eunamespace=0&format=json)

#### Поиск статей, цитирующих выбранную страницу

Запрос ниже возвращает перечень статей, в которых присутствует
гиперссылка на статью о Кубинской революции. \>
[`https://cyclowiki.org/w/api.php?action=query&titles=Роза Люксембург&prop=linkshere&lhlimit=200&lhnamespace=0&format=json`](https://cyclowiki.org/w/api.php?action=query&titles=%D0%A0%D0%BE%D0%B7%D0%B0%20%D0%9B%D1%8E%D0%BA%D1%81%D0%B5%D0%BC%D0%B1%D1%83%D1%80%D0%B3&prop=linkshere&lhlimit=200&lhnamespace=0&format=json)

#### Гиперссылки из статьи, ведущие на другие статьи энциклопедии

Запрос ниже возвращает перечень статей Циклопедии, на которые ссылается
выбранная статья.

> [`https://cyclowiki.org/w/api.php?action=query&titles=Компьютерная оптика&prop=links&format=json`](https://cyclowiki.org/w/api.php?action=query&titles=%D0%9A%D0%BE%D0%BC%D0%BF%D1%8C%D1%8E%D1%82%D0%B5%D1%80%D0%BD%D0%B0%D1%8F_%D0%BE%D0%BF%D1%82%D0%B8%D0%BA%D0%B0&prop=links&format=json)

#### Ссылки на внешние сайты с выбранной страницы

> [`https://cyclowiki.org/w/api.php?action=query&titles=Компьютерная оптика&prop=extlinks&ellimit=500&elexpandurl=true&format=json`](https://cyclowiki.org/w/api.php?action=query&titles=%D0%9A%D0%BE%D0%BC%D0%BF%D1%8C%D1%8E%D1%82%D0%B5%D1%80%D0%BD%D0%B0%D1%8F%20%D0%BE%D0%BF%D1%82%D0%B8%D0%BA%D0%B0&prop=extlinks&ellimit=500&elexpandurl=true&format=json)

Можно объединить ссылки с внутренними (на страницы энциклопедии), указав
`prop=extlinks|links`.

**\[Альтернативный способ\]**

> [`https://cyclowiki.org/w/api.php?action=parse&page=Компьютерная оптика&prop=externallinks&format=json`](https://cyclowiki.org/w/api.php?action=parse&page=%D0%9A%D0%BE%D0%BC%D0%BF%D1%8C%D1%8E%D1%82%D0%B5%D1%80%D0%BD%D0%B0%D1%8F%20%D0%BE%D0%BF%D1%82%D0%B8%D0%BA%D0%B0&prop=externallinks&format=json)

[:top:](#mediawiki-action-api)

------------------------------------------------------------------------

## Приложение 2. РУВИКИ

------------------------------------------------------------------------

## Приложение 3. Циклопедия

На момент подготовки статьи на сайте
[Циклопедии](https://cyclowiki.org/) автору не удалось найти
документацию API, но поскольку Циклопедия сделана на базе MediaWiki, то
удалось обнаружить работающие MediaWiki Action API и MediaWiki REST API.

#### Информация о статье

> [`https://cyclowiki.org/w/api.php?action=query&titles=Китайская кошка&format=json`](https://cyclowiki.org/w/api.php?action=query&titles=%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F_%D0%BA%D0%BE%D1%88%D0%BA%D0%B0&format=json)

Запрос ниже возвращает более детальную json-структуру, из которой легко
извлечь текст, категории (categories), ссылки на страницы (links),
ссылка на внешние страницы (externallinks), перечень изображений
(images), секций (sections), шаблонов (template), интер-вики ссылок
(iwlinks – здесь ссылки на оригинальную Википедию и другие Викисервисы).

> [`https://cyclowiki.org/w/api.php?action=parse&page=Китайская кошка&format=json`](https://cyclowiki.org/w/api.php?action=parse&page=%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F_%D0%BA%D0%BE%D1%88%D0%BA%D0%B0&format=json)

По сравнению с оригиналом (далее под оригиналом подразумевается
MediaWiki API в оригинальной Wikipedia) отсутствуют идентификатор
соответствующего статье элемента Викиданных (wikibase_item) и ссылки на
языковые версии статей (раздел есть, но автор не встретил примеров
статей, где он был бы заполнен).

Версия MediWiki REST API

> [`https://cyclowiki.org/w/rest.php/v1/page/Китайская кошка`](https://cyclowiki.org/w/rest.php/v1/page/%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F_%D0%BA%D0%BE%D1%88%D0%BA%D0%B0)

#### Извлечь разделы статьи

Возвращает перечень разделов страницы, их размер, порядковые номера и
названия внутренних ссылок.

> [`https://cyclowiki.org/w/api.php?action=parse&page=Китайская кошка&prop=sections&format=json`](https://cyclowiki.org/w/api.php?action=parse&page=%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F_%D0%BA%D0%BE%D1%88%D0%BA%D0%B0&prop=sections&format=json)

Получив сведения из запроса выше, можно извлечь отдельные разделы в
форматах wikitext или parsetree.

> [`https://cyclowiki.org/w/api.php?action=parse&page=Китайская кошка&prop=wikitext|parsetree&section=5&format=json`](https://cyclowiki.org/w/api.php?action=parse&page=%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F_%D0%BA%D0%BE%D1%88%D0%BA%D0%B0&prop=wikitext%7Cparsetree&section=5&format=json)

#### Извлечь категории статьи

> [`https://cyclowiki.org/w/api.php?action=parse&page=Китайская кошка&prop=categories&format=json`](https://cyclowiki.org/w/api.php?action=parse&page=%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F_%D0%BA%D0%BE%D1%88%D0%BA%D0%B0&prop=categories&format=json)

Найти все статьи по категории

> [`https://cyclowiki.org/w/api.php?cmtitle=Category:Сады и парки России&action=query&list=categorymembers&cmlimit=100&cmprop=title|timestamp&format=json`](https://cyclowiki.org/w/api.php?cmtitle=Category:%D0%A1%D0%B0%D0%B4%D1%8B%20%D0%B8%20%D0%BF%D0%B0%D1%80%D0%BA%D0%B8%20%D0%A0%D0%BE%D1%81%D1%81%D0%B8%D0%B8&action=query&list=categorymembers&cmlimit=100&cmprop=title%7Ctimestamp&format=json)

#### История правок статьи

Запрос ниже возвращает информацию о 10 правках, внесенных после 01
декабря 2022 года в статью о Китайской кошке.

> [`https://cyclowiki.org/w/api.php?action=query&titles=Китайская кошка&prop=revisions&rvslots=main&rvlimit=10&rvdir=newer&rvstart=2022-12-01T00:00:00Z&rvprop=ids|flags|timestamp|user|userid|size|contentmodel|comment|parsedcomment|content|tags&format=json`](https://cyclowiki.org/w/api.php?action=query&titles=%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F%20%D0%BA%D0%BE%D1%88%D0%BA%D0%B0&prop=revisions&rvslots=main&rvlimit=10&rvdir=newer&rvstart=2022-12-01T00:00:00Z&rvprop=ids%7Cflags%7Ctimestamp%7Cuser%7Cuserid%7Csize%7Ccontentmodel%7Ccomment%7Cparsedcomment%7Ccontent%7Ctags&format=json)

#### Список пользователей, которые правили страницу

Запрос ниже возвращает список пользователей, которые редактировали
статью о Китайской кошке.

> [`https://cyclowiki.org/w/api.php?action=query&titles=Китайская кошка&prop=contributors&pclimit=200&format=json`](https://cyclowiki.org/w/api.php?action=query&titles=%D0%9A%D0%B8%D1%82%D0%B0%D0%B9%D1%81%D0%BA%D0%B0%D1%8F%20%D0%BA%D0%BE%D1%88%D0%BA%D0%B0&prop=contributors&pclimit=200&format=json).

Чтобы получить список редакторов-ботов к запросу необходимо добавить
&pcgroup=bot.

#### Список всех правок пользователя

Запрос ниже возвращает в формате json правки пользователя
[Serebr](https://cyclowiki.org/wiki/%D0%A3%D1%87%D0%B0%D1%81%D1%82%D0%BD%D0%B8%D0%BA:Serebr).

> [`https://cyclowiki.org/w/api.php?action=query&list=allrevisions&arvuser=Serebr&arvslots=*&arvprop=ids|flags|timestamp|user|userid|size|contentmodel|comment|parsedcomment|tags&format=json`](https://cyclowiki.org/w/api.php?action=query&list=allrevisions&arvuser=Serebr&arvslots=*&arvprop=ids%7Cflags%7Ctimestamp%7Cuser%7Cuserid%7Csize%7Ccontentmodel%7Ccomment%7Cparsedcomment%7Ctags&format=json)

Для получения текста правок добавьте в аргумент arvprop значение
content.

#### Поиск статей, цитирующих внешний web-сайт

Можно искать ссылки только в статьях определенного типа, используя
выражение `&eunamespace=...` и определенные значения (0 – статьи, 1 –
Talk:Page, 2 – Профили пользователей, 3 – личные User talk страницы).

Запрос ниже возвращает перечень статей (namespace = 0), в которых
присутствуют гиперссылки на сайт издательства “Медиасфера”.

> [`https://cyclowiki.org/w/api.php?action=query&list=exturlusage&euquery=www.mediasphera.ru&eunamespace=0&format=json`](https://cyclowiki.org/w/api.php?action=query&list=exturlusage&euquery=www.mediasphera.ru&eunamespace=0&format=json)

#### Поиск статей, цитирующих выбранную страницу

Запрос ниже возвращает перечень статей, в которых присутствует
гиперссылка на статью о Кубинской революции. \>
[`https://cyclowiki.org/w/api.php?action=query&titles=Роза Люксембург&prop=linkshere&lhlimit=200&lhnamespace=0&format=json`](https://cyclowiki.org/w/api.php?action=query&titles=%D0%A0%D0%BE%D0%B7%D0%B0%20%D0%9B%D1%8E%D0%BA%D1%81%D0%B5%D0%BC%D0%B1%D1%83%D1%80%D0%B3&prop=linkshere&lhlimit=200&lhnamespace=0&format=json)

#### Гиперссылки из статьи, ведущие на другие статьи энциклопедии

Запрос ниже возвращает перечень статей Википедии, на которые ссылается
выбранная статья.

> [`https://cyclowiki.org/w/api.php?action=query&titles=Компьютерная оптика&prop=links&format=json`](https://cyclowiki.org/w/api.php?action=query&titles=%D0%9A%D0%BE%D0%BC%D0%BF%D1%8C%D1%8E%D1%82%D0%B5%D1%80%D0%BD%D0%B0%D1%8F_%D0%BE%D0%BF%D1%82%D0%B8%D0%BA%D0%B0&prop=links&format=json)

#### Ссылки на внешние сайты с выбранной страницы

> [`https://cyclowiki.org/w/api.php?action=query&titles=Компьютерная оптика&prop=extlinks&ellimit=500&elexpandurl=true&format=json`](https://cyclowiki.org/w/api.php?action=query&titles=%D0%9A%D0%BE%D0%BC%D0%BF%D1%8C%D1%8E%D1%82%D0%B5%D1%80%D0%BD%D0%B0%D1%8F%20%D0%BE%D0%BF%D1%82%D0%B8%D0%BA%D0%B0&prop=extlinks&ellimit=500&elexpandurl=true&format=json)

Можно объединить ссылки с внутренними (на страницы энциклопедии), указав
`prop=extlinks|links`.

**\[Альтернативный способ\]**

> [`https://cyclowiki.org/w/api.php?action=parse&page=Компьютерная оптика&prop=externallinks&format=json`](https://cyclowiki.org/w/api.php?action=parse&page=%D0%9A%D0%BE%D0%BC%D0%BF%D1%8C%D1%8E%D1%82%D0%B5%D1%80%D0%BD%D0%B0%D1%8F%20%D0%BE%D0%BF%D1%82%D0%B8%D0%BA%D0%B0&prop=externallinks&format=json)

------------------------------------------------------------------------

## Обратная связь

Если сделаете pull request, постараюсь принять.

#### Лицензия

Знание – людям!

#### Позиция по поводу открытых энциклопедий

Я убежден в том, что возможности оригинальных Вики-сервисов (Wikipedia,
Wikidata и др.) следует изучать прежде всего для того, чтобы знать “как
оно может быть”. Надеюсь, что после ознакомления с перечисленными в
данном материале возможностями Вики-сервисов, читатели смогут по-новому
взглянуть на практическую ценность любых других онлайн-ресурсов
(особенно тех, которыми предлагается импортозамещать Wikipedia).

#### Отказ от ответственности

На момент опубликования материала автор не осведомлен о каких-либо
ограничениях, касающихся использования перечисленных ресурсов. Автор не
может судить о наличии в упоминаемых онлайн-ресурсах сведений, которые
могут рассматриваться как порочащие или ложные. Материал не является
рекламой и предназначен для половозрелых благоразумных людей, которые
сами смогут решить who is who.

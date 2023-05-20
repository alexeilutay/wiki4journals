API-Викисервисов для академических издателей
================
Лутай А.В.
2023-05-20

-   [API и SPARQL интерфейсы](#api-и-sparql-интерфейсы)
    -   [Wikipedia REST API (WP)](#wikipedia-rest-api-wp)
    -   [Wikimedia REST API (WM)](#wikimedia-rest-api-wm)
    -   [MediaWiki Action API (MWA)](#mediawiki-action-api-mwa)
    -   [Wikidata API (WD)](#wikidata-api-wd)
    -   [SPARQL](#sparql)
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
    -   [Извлечь разделы статьи в
        Wikipedia](#извлечь-разделы-статьи-в-wikipedia)
    -   [Получить Wikidata ID по названию статьи в
        Wikipedia](#получить-wikidata-id-по-названию-статьи-в-wikipedia)
    -   [Найти страницы Wikipedia по Wikidata
        ID](#найти-страницы-wikipedia-по-wikidata-id)
    -   [Цитировать статью Wikipedia в формате
        bibtex](#цитировать-статью-wikipedia-в-формате-bibtex)
-   [Типовые задачи – правки и
    просмотры](#типовые-задачи--правки-и-просмотры)
    -   [История правок статьи в
        Wikipedia](#история-правок-статьи-в-wikipedia)
    -   [Список тех, кто правил
        страницу](#список-тех-кто-правил-страницу)
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
    -   [Ссылки на другие статьи Wikipedia с выбранной страницы
        Wikipedia](#ссылки-на-другие-статьи-wikipedia-с-выбранной-страницы-wikipedia)
    -   [Ссылки на внешние сайты с выбранной страницы
        Wikipedia](#ссылки-на-внешние-сайты-с-выбранной-страницы-wikipedia)
-   [Наукометрия в Wikidata](#наукометрия-в-wikidata)
    -   [Сбор Wikidata-сведений о журнале по
        ISSN](#сбор-wikidata-сведений-о-журнале-по-issn)
    -   [Все российские журналы в
        Wikidata](#все-российские-журналы-в-wikidata)
    -   [Количество статей в Wikidata в российских
        журналах](#количество-статей-в-wikidata-в-российских-журналах)
    -   [Извлечение источников заданного
        свойства](#извлечение-источников-заданного-свойства)
    -   [Статьи из выбранного журнала и цитирующие их
        журналы](#статьи-из-выбранного-журнала-и-цитирующие-их-журналы)
    -   [Список авторов выбранного журнала, имеющих
        ORCID](#список-авторов-выбранного-журнала-имеющих-orcid)
    -   [Женщины-ученые с наградами, цитировавшие выбранный
        журнал](#женщины-ученые-с-наградами-цитировавшие-выбранный-журнал)
    -   [Российские ученые, имеющие ORCID и страницу в
        RU-Wikipedia](#российские-ученые-имеющие-orcid-и-страницу-в-ru-wikipedia)
    -   [Исследователи младше 30 лет, имеющие статью в EN
        Wikipedia](#исследователи-младше-30-лет-имеющие-статью-в-en-wikipedia)
    -   [Перечень университетов, расположенных в \<=500 метрах от
        метро](#перечень-университетов-расположенных-в-500-метрах-от-метро)
    -   [Перечень организаций, цитировавших статьи из выбранного
        журнала](#перечень-организаций-цитировавших-статьи-из-выбранного-журнала)
    -   [Исследователи, цитировавшие статьи из журнала со списком
        цитирующих и процитированных
        статей](#исследователи-цитировавшие-статьи-из-журнала-со-списком-цитирующих-и-процитированных-статей)
    -   [Статьи из журнала и цитирующие их организации и
        страны](#статьи-из-журнала-и-цитирующие-их-организации-и-страны)
    -   [Лицензия](#лицензия)

------------------------------------------------------------------------

## API и SPARQL интерфейсы

### Wikipedia REST API (WP)

-   <https://www.mediawiki.org/wiki/API:REST_API>
-   <https://www.mediawiki.org/wiki/API:REST_API/Reference>

**Перелистывание результатов**

-   <https://www.mediawiki.org/wiki/API:Continue>

### Wikimedia REST API (WM)

-   <https://en.wikipedia.org/api/rest_v1/#/>

-   [Спецификация API в
    JSON](https://en.wikipedia.org/api/rest_v1/?spec)

### MediaWiki Action API (MWA)

-   <https://www.mediawiki.org/wiki/API:Main_page>

### Wikidata API (WD)

### SPARQL

Примеры запросов в основной части будут сопровождаться гиперссылками,
открывающими запрос в интерфейсе
<a href="https://query.wikidata.org/" target="_blank">Wikidata Query
Service</a>. Их также можно отправлять программными средствами с помощью
специальных пакетов для R: <a href="https://github.com/TS404/WikidataR"
target="_blank">WikidataR</a>, для Python: пакет
<a href="https://github.com/dahlia/wikidata"
target="_blank">Wikidata</a>,
<a href="https://www.wikidata.org/wiki/Wikidata:Tools/For_programmers"
target="_blank">другие примеры</a>).

-   <a href="https://www.wikidata.org/wiki/Wikidata:SPARQL_tutorial/ru"
    target="_blank">Руководство по использованию SPARQL (частично на русском
    языке)</a>

-   <https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/queries/examples>

-   <https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/queries/examples/advanced>

-   <https://www.wikidata.org/wiki/User:MartinPoulter/queries>

-   <https://wdqs-tutorial.toolforge.org/>

-   :boom: <a
    href="https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/qotw"
    target="_blank">Архив SPARQL запросов 2015-2022 из еженедельных
    дайджестов)</a>

------------------------------------------------------------------------

## Материалы на русском языке

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**Базовые сведения:**

-   <a href="https://podpiska.rfbr.ru/materials/wikidata4journals/"
    target="_blank">Сервис Викиданные для научных журналов</a>

-   <a
    href="https://ru.wikisource.org/wiki/%D0%A1%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0:%D0%92%D0%B8%D0%BA%D0%B8%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5"
    target="_blank">Статья “Викиданные” в Викитеке</a>

**Популярным языком:**

-   Статья <a href="https://openriro.github.io/posts/wikidata-profile/"
    target="_blank">“О профилях организаций в Wikidata”</a>, в которой
    описываются приемы по описанию профиля научной организации в
    Викиданных”

-   Статья <a href="https://openriro.github.io/posts/wikidata-profile/"
    target="_blank">“О профилях организаций в Wikidata”</a>, в которой
    описываются приемы по описанию профиля научной организации в
    Викиданных”

-   Семинар “Работа с метаданными” (12.10.2022) от Наукометрического
    центра ВШЭ. Видео YouTube,
    <a href="https://youtu.be/XX6eT1ON4_I?t=1504" target="_blank">про
    Викиданные с 25-ой минуты</a>.

**Для тех, кто готов пойти дальше:**

-   <a
    href="https://ru.wikiversity.org/wiki/%D0%9F%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5_%D0%92%D0%B8%D0%BA%D0%B8%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85"
    target="_blank">Курс Программирование Викиданных (ПетрГУ)</a>

------------------------------------------------------------------------

## Типовые задачи – сведения о статье

### Информация о статье в Wikipedia

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**WP**

Возвращает json с ID последней правки и подробным wiki-text HTML
(infobox, ссылки с библиографическими деталями и т.д.).

> <a href="https://en.wikipedia.org/w/rest.php/v1/page/The%20BMJ"
> target="_blank"><code>https://en.wikipedia.org/w/rest.php/v1/page/The%20BMJ</code></a>

**MWA**

Возвращает в JSON текст, языковые версии, категории, ссылки на страницы
Wikipedia, ссылка на внешние страницы, перечень изображений, секций,
шаблонов, интер-вики ссылок и wikibase item (в properties)

> <a
> href="https://en.wikipedia.org/w/api.php?action=parse&amp;page=The%20BMJ&amp;format=json"
> target="_blank"><code>https://en.wikipedia.org/w/api.php?action=parse&amp;page=The%20BMJ&amp;format=json</code></a>

**WM**

Возвращает namespace, Wikibase ID, название, thumbnail, original image,
последнюю правку с временной отметкой и ID, аннотацию (текст и HTML).

> <a href="https://en.wikipedia.org/api/rest_v1/page/summary/The%20BMJ"
> target="_blank"><code>https://en.wikipedia.org/api/rest_v1/page/summary/The%20BMJ</code></a>

------------------------------------------------------------------------

### Другие названия объекта статьи

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**MWA**

> <a
> href="https://en.wikipedia.org/w/api.php?action=query&amp;prop=pageterms&amp;titles=The%20BMJ&amp;format=json"
> target="_blank"><code>https://en.wikipedia.org/w/api.php?action=query&amp;prop=pageterms&amp;titles=The%20BMJ&amp;format=json</code></a>

------------------------------------------------------------------------

### Все языковые версии статьи в Wikipedia

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**WP**

возвращает только названия страниц

> <a
> href="https://en.wikipedia.org/w/rest.php/v1/page/The_Lancet/links/language"
> target="_blank"><code>https://en.wikipedia.org/w/rest.php/v1/page/The_Lancet/links/language</code></a>

**MWA**

возвращает pageid для страниц объекта и полные URL на страницы языковых
версий

> <a
> href="https://en.wikipedia.org/w/api.php?action=query&amp;titles=The_Lancet&amp;prop=langlinks&amp;format=json&amp;llprop=url&amp;lllimit=500"
> target="_blank"><code>https://en.wikipedia.org/w/api.php?action=query&amp;titles=The_Lancet&amp;prop=langlinks&amp;format=json&amp;llprop=url&amp;lllimit=500</code></a>

------------------------------------------------------------------------

### Извлечь категории статьи

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**MWA**

> <a
> href="https://en.wikipedia.org/w/api.php?action=parse&amp;page=The%20BMJ&amp;prop=categories&amp;format=json"
> target="_blank"><code>https://en.wikipedia.org/w/api.php?action=parse&amp;page=The%20BMJ&amp;prop=categories&amp;format=json</code></a>

------------------------------------------------------------------------

### Извлечь разделы статьи в Wikipedia

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**MWA**

<a href="https://www.mediawiki.org/wiki/API:Parsing_wikitext"
target="_blank">Инструкция</a>

Возвращает перечень разделов страницы Wikipedia, их размер, порядковые
номера и названия внутренних ссылок.

> <a
> href="https://en.wikipedia.org/w/api.php?action=parse&amp;format=json&amp;page=The%20BMJ&amp;prop=sections"
> target="_blank"><code>https://en.wikipedia.org/w/api.php?action=parse&amp;format=json&amp;page=The%20BMJ&amp;prop=sections</code></a>

Получив сведения из запроса выше, можно извлечь отдельные разделы в
форматах wikitext или parsetree

> <a
> href="https://en.wikipedia.org/w/api.php?action=parse&amp;page=The%20BMJ&amp;prop=wikitext%7Cparsetree&amp;section=5&amp;format=json"
> target="_blank"><code>https://en.wikipedia.org/w/api.php?action=parse&amp;page=The%20BMJ&amp;prop=wikitext|parsetree&amp;section=5&amp;format=json</code></a>

------------------------------------------------------------------------

### Получить Wikidata ID по названию статьи в Wikipedia

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**MWA**

возвращает Wikibase ID (aka Wikidata ID) и wikibase-shortdesc (если
есть)

> <a
> href="https://ru.wikipedia.org/w/api.php?action=query&amp;prop=pageprops&amp;format=json&amp;titles=Криосфера_Земли"
> target="_blank"><code>https://ru.wikipedia.org/w/api.php?action=query&amp;prop=pageprops&amp;format=json&amp;titles=Криосфера_Земли</code></a>

**WP**

возвращает информацию о странице, в которой есть поле wikibase_item

> <a
> href="https://ru.wikipedia.org/api/rest_v1/page/summary/Криосфера_Земли"
> target="_blank"><code>https://ru.wikipedia.org/api/rest_v1/page/summary/Криосфера_Земли</code></a>

**WD**

возвращает все запрошенные элементы Wikidata. При запросе русскоязычной
страницы необходимо заменить enwiki на ruwiki, можно также получать
заголовки на нескольких языках (en\|ru).

> <a
> href="https://www.wikidata.org/w/api.php?action=wbgetentities&amp;format=json&amp;sites=ruwiki&amp;titles=Журнал_технической_физики&amp;props=info%7Clabels%7Cdescriptions%7Cclaims&amp;languages=en%7Cru"
> target="_blank"><code>https://www.wikidata.org/w/api.php?action=wbgetentities&amp;format=json&amp;sites=ruwiki&amp;titles=Журнал_технической_физики&amp;props=info|labels|descriptions|claims&amp;languages=en|ru</code></a>

**SPARQL**

```
SELECT ?lemma ?item WHERE {
  VALUES ?lemma {"Успехи химии"@ru}
  ?sitelink schema:about ?item; 
            schema:isPartOf <https://ru.wikipedia.org/>; 
            schema:name ?lemma.
}
```

<a
href="https://query.wikidata.org/#SELECT%20%3Flemma%20%3Fitem%20WHERE%20%7B%0A%20%20VALUES%20%3Flemma%20%7B%22%D0%A3%D1%81%D0%BF%D0%B5%D1%85%D0%B8%20%D1%85%D0%B8%D0%BC%D0%B8%D0%B8%22%40ru%7D%0A%20%20%3Fsitelink%20schema%3Aabout%20%3Fitem%3B%20%0A%20%20%20%20%20%20%20%20%20%20%20%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fru.wikipedia.org%2F%3E%3B%20%0A%20%20%20%20%20%20%20%20%20%20%20%20schema%3Aname%20%3Flemma.%0A%7D%0A"
target="_blank">отправить через Wikidata Query Service</a>

------------------------------------------------------------------------

### Найти страницы Wikipedia по Wikidata ID

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**MWA**

> <a
> href="https://www.wikidata.org/w/api.php?action=wbgetentities&amp;format=xml&amp;props=sitelinks&amp;ids=Q3453517"
> target="_blank"><code>https://www.wikidata.org/w/api.php?action=wbgetentities&amp;format=xml&amp;props=sitelinks&amp;ids=Q3453517</code></a>

Добавляя выражения вида *&sitefilter=enwiki* можно ограничить результаты
определенным языком.

**SPARQL**

```
SELECT DISTINCT ?article WHERE {
  VALUES ?item {wd:Q3453517}
  ?article schema:about ?item; 
           schema:isPartOf <https://ru.wikipedia.org/>
}
```

<a
href="https://query.wikidata.org/#SELECT%20DISTINCT%20%3Farticle%20WHERE%20%7B%0A%20%20VALUES%20%3Fitem%20%7Bwd%3AQ3453517%7D%0A%20%20%3Farticle%20schema%3Aabout%20%3Fitem%3B%0A%20%20%20%20%20%20%20%20%20%20%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fru.wikipedia.org%2F%3E%0A%7D%0A"
target="_blank">отправить через Wikidata Query Service</a>

------------------------------------------------------------------------

### Цитировать статью Wikipedia в формате bibtex

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**WM**

Сервис поддерживает также формат zotero и несколько других (mediawiki,
wikibase). Цитируемый URL включает параметр oldid – идентификатор
последней правки на момент цитирования! Обратите внимание на
необходимость URL-кодирования гиперссылки страницы Wikipedia. Результат
– скачивание текстового файла с цитирование в выбранном формате.

> <a
> href="https://en.wikipedia.org/api/rest_v1/data/citation/bibtex/https%3A%2F%2Fru.wikipedia.org%2Fwiki%2FЖурнал_технической_физики"
> target="_blank"><code>https://en.wikipedia.org/api/rest_v1/data/citation/bibtex/https%3A%2F%2Fru.wikipedia.org%2Fwiki%2FЖурнал_технической_физики</code></a>

------------------------------------------------------------------------

## Типовые задачи – правки и просмотры

### История правок статьи в Wikipedia

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**WM**

возвращает последнюю правку и имя последнего пользователя

> <a
> href="https://ru.wikipedia.org/api/rest_v1/page/title/Доклады%20Академии%20наук"
> target="_blank"><code>https://ru.wikipedia.org/api/rest_v1/page/title/Доклады%20Академии%20наук</code></a>

**WP**

возвращает историю правок с id изменения, временем правки, данными о
создателе (id, name) и размером правок (delta).

> <a
> href="https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history"
> target="_blank"><code>https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history</code></a>

Дополнив запрос выражением *?older_than=939967546* (или
*?newer_than=1018790892*) можно получить более ранние (или поздние)
правки (вместо цифр подставлять id конкретной правки)

Добавив в запрос выражение ?filter=…, можно отобрать только определенные
правки:

-   reverted: правки, отменяющие более ранние изменения
-   anonymous: правки, сделанные анонимными пользователями (показывает
    IP),
-   bot: правки, сделанные ботами,
-   minor: правки, отмеченные как незначительные (minor edits)

> <a
> href="https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history?older_than=97918317&amp;filter=anonymous"
> target="_blank"><code>https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history?older_than=97918317&amp;filter=anonymous</code></a>

**Количество правок**

> <a
> href="https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history/counts/edits"
> target="_blank"><code>https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history/counts/edits</code></a>

> <a
> href="https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history/counts/edits?from=88695017&amp;to=97918317"
> target="_blank"><code>https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history/counts/edits?from=88695017&amp;to=97918317</code></a>

------------------------------------------------------------------------

### Список тех, кто правил страницу

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**MWA**

<a
href="https://www.mediawiki.org/w/api.php?action=help&amp;modules=query%2Bcontributors"
target="_blank">Информация</a>

> <a
> href="https://en.wikipedia.org/w/api.php?action=query&amp;titles=The%20BMJ&amp;prop=contributors&amp;pclimit=200&amp;pcgroup=bot&amp;format=json"
> target="_blank"><code>https://en.wikipedia.org/w/api.php?action=query&amp;titles=The%20BMJ&amp;prop=contributors&amp;pclimit=200&amp;pcgroup=bot&amp;format=json</code></a>

------------------------------------------------------------------------

### Статистика просмотров страницы в Wikipedia

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

<a href="https://wikimedia.org/api/rest_v1/"
target="_blank">Инструкция</a>

Запросы должны иметь синтаксис вида
`https://wikimedia.org/api/rest_v1/metrics/pageviews/per-article/ {project}/{access}/{agent}/{article}/{granularity}/{start}/{end}`,
в {article} необходимо заменить пробелы на \_ и использовать
URL-кодирование.

> <a
> href="https://wikimedia.org/api/rest_v1/metrics/pageviews/per-article/en.wikipedia/all-access/all-agents/The%20BMJ/monthly/20220101/20230331"
> target="_blank"><code>https://wikimedia.org/api/rest_v1/metrics/pageviews/per-article/en.wikipedia/all-access/all-agents/The%20BMJ/monthly/20220101/20230331</code></a>

**Другие веб-интерфейсы:**

-   <https://meta.wikimedia.org/wiki/Pageviews_Analysis>
-   <https://pageviews.wmcloud.org/>
-   <http://stats.grok.se/json/en/latest30/Britney_Spears>
-   <https://www.wikishark.com/title/en/The_BMJ>
-   <https://wikipediaviews.org/>

------------------------------------------------------------------------

### Количество новых страниц в Wikipedia по месяцам

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**WM**

> <a
> href="https://wikimedia.org/api/rest_v1/metrics/edited-pages/new/ru.wikipedia.org/user/content/monthly/20210101/20230401"
> target="_blank"><code>https://wikimedia.org/api/rest_v1/metrics/edited-pages/new/ru.wikipedia.org/user/content/monthly/20210101/20230401</code></a>

------------------------------------------------------------------------

### Рейтинг редакторов по дням

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**WM**

> <a
> href="https://wikimedia.org/api/rest_v1/metrics/editors/top-by-edits/ru.wikipedia.org/user/content/2023/03/31"
> target="_blank"><code>https://wikimedia.org/api/rest_v1/metrics/editors/top-by-edits/ru.wikipedia.org/user/content/2023/03/31</code></a>

------------------------------------------------------------------------

### Количество новых редакторов по месяцам

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**WM**

> <a
> href="https://wikimedia.org/api/rest_v1/metrics/registered-users/new/ru.wikipedia.org/monthly/20200101/20230331"
> target="_blank"><code>https://wikimedia.org/api/rest_v1/metrics/registered-users/new/ru.wikipedia.org/monthly/20200101/20230331</code></a>

------------------------------------------------------------------------

## Типовые задачи – ссылки и цитирования

### Поиск статей в Wikipedia, цитирующих внешний web-сайт

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**MWA**

<a href="https://www.mediawiki.org/wiki/API:Exturlusage"
target="_blank">Инструкция</a>

Можно искать ссылки только в статьях определенного типа, используя
выражение *&eunamespace=…* и определенные значения (0 – Wikipedia Page,
1 – Talk:Page, 2 – Профили пользователей, 3 – личные User talk
страницы).

> <a
> href="https://ru.wikipedia.org/w/api.php?action=query&amp;format=json&amp;list=exturlusage&amp;euquery=www.mediasphera.ru&amp;eunamespace=0"
> target="_blank"><code>https://ru.wikipedia.org/w/api.php?action=query&amp;format=json&amp;list=exturlusage&amp;euquery=www.mediasphera.ru&amp;eunamespace=0</code></a>

------------------------------------------------------------------------

### Поиск статей Wikipedia, цитирующих выбранную страницу Wikipedia

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**MWA**

<a
href="https://www.mediawiki.org/w/api.php?action=help&amp;modules=query%2Blinkshere"
target="_blank">Инструкция</a>

> <a
> href="https://en.wikipedia.org/w/api.php?action=query&amp;titles=The%20BMJ&amp;prop=linkshere&amp;lhlimit=200&amp;lhnamespace=0&amp;format=json"
> target="_blank"><code>https://en.wikipedia.org/w/api.php?action=query&amp;titles=The%20BMJ&amp;prop=linkshere&amp;lhlimit=200&amp;lhnamespace=0&amp;format=json</code></a>

------------------------------------------------------------------------

### Ссылки на другие статьи Wikipedia с выбранной страницы Wikipedia

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**MWA**

> <a
> href="https://en.wikipedia.org/w/api.php?action=parse&amp;page=The%20BMJ&amp;prop=links&amp;format=json"
> target="_blank"><code>https://en.wikipedia.org/w/api.php?action=parse&amp;page=The%20BMJ&amp;prop=links&amp;format=json</code></a>

------------------------------------------------------------------------

### Ссылки на внешние сайты с выбранной страницы Wikipedia

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

<a href="https://www.mediawiki.org/wiki/API:Extlinks"
target="_blank">Инструкция</a>

**MWA**

> <a
> href="https://en.wikipedia.org/w/api.php?action=query&amp;titles=The%20BMJ&amp;prop=extlinks&amp;ellimit=500&amp;elexpandurl=true&amp;format=json"
> target="_blank"><code>https://en.wikipedia.org/w/api.php?action=query&amp;titles=The%20BMJ&amp;prop=extlinks&amp;ellimit=500&amp;elexpandurl=true&amp;format=json</code></a>

Можно объединить ссылки с внутренними (на страницы Wikipedia), выбрав
*prop=extlinks\|links*.

<a href="https://www.mediawiki.org/wiki/API:Parsing_wikitext"
target="_blank">Альтернативный способ</a>

> <a
> href="https://en.wikipedia.org/w/api.php?action=parse&amp;page=The%20BMJ&amp;prop=externallinks&amp;format=json"
> target="_blank"><code>https://en.wikipedia.org/w/api.php?action=parse&amp;page=The%20BMJ&amp;prop=externallinks&amp;format=json</code></a>

------------------------------------------------------------------------

## Наукометрия в Wikidata

### Сбор Wikidata-сведений о журнале по ISSN

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**SPARQL**

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

<a
href="https://query.wikidata.org/#SELECT%20DISTINCT%20%3Fitem%20%3Ftypes%20%3Fissns%20%3FissnLs%20%3Ftitles%20%3Fshort_titles%20%0A%20%20%20%20%3Fitemlabel_en%20%3Fitemlabel_ru%20%20%3Fcountries%20%3Flangs%20%3Fpublishers%20%3Fwebsites%20%0A%20%20%20%20%3FarticleEN%20%3FarticleRU%20%20%3Felibrary%20%3Fopenalex_ids%20%3Fscilit_ids%20%3Fnlm_ids%20%0A%20%20%20%20%3Fcref_ids%20%3Fcoci_ids%20%3Fscids%20%3Fdim_ids%20%20%3Fdoaj_ids%20%3Fbnf_ids%20%3Fsudoc_ids%20%3Fgnd_ids%20%0A%20%20%20%20%3Feics%20%3Feic_orcids%20%3Feditors%20%3Feditor_orcids%20%20%3Finception%20%20%3Ffounded%20%3Fpart_of%20%3Fhas_part%20%0A%20%20%20%20%3Ffollows%20%3Ffollowed%20%3Freplaces%20%3Freplaced%20%3Fdiscontinued%20%3Ftranslation%20%3Fsubjects%0AWITH%20%7B%0A%20SELECT%20DISTINCT%20%3Fitem%20%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fwebsite%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fwebsites%29%20%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3FtypeLabel%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Ftypes%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Ftitle%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Ftitles%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fshort_title%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fshort_titles%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fmain_subjectLabel%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fsubjects%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3FpublisherLabel%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fpublishers%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fcountry%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fcountries%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Flanguage%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Flangs%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fissn%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fissns%29%20%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3FissnL%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3FissnLs%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fopenalex%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fopenalex_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fdimensions%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fdim_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fcrossref%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fcref_ids%29%20%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fnlm%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fnlm_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fcoci%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fcoci_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fbnf%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fbnf_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fgnd%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fgnd_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fdoaj%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fdoaj_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fsudoc%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fsudoc_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fscilit%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fscilit_ids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fscid%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Fscids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Feditor_orcid%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Feditor_orcids%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3Feic_orcid%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Feic_orcids%29%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3FeditorLabel%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Feditors%29%0A%20%20%28GROUP_CONCAT%28DISTINCT%20%3FeicLabel%3B%20separator%20%3D%20%22%20%7C%20%22%29%20as%20%3Feics%29%20%20%0AWHERE%7B%0A%20%20%20%20%3Fitem%20wdt%3AP236%20%3Fquery.%20FILTER%28%3Fquery%20in%20%28%221550-8943%22%2C%20%220007-1447%22%29%29.%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP31%20%3Ftype.%20%3Ftype%20rdfs%3Alabel%20%3FtypeLabel.%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20FILTER%28lang%28%3FtypeLabel%29%3D%22en%22%29.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP236%20%3Fissn.%7D%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP7363%20%3FissnL.%7D%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP5115%20%3Fdoaj.%7D%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP10283%20%3Fopenalex.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP8375%20%3Fcrossref.%7D%20%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP3181%20%3Fcoci.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP1156%20%3Fscid.%7D%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP6180%20%3Fdimensions.%7D%20%20%20%20%20%20%20%20%20%20%20%20%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP268%20%3Fbnf.%7D%20%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP227%20%3Fgnd.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP1025%20%3Fsudoc.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP7662%20%3Fscilit.%7D%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP1055%20%3Fnlm.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP856%20%3Fwebsite.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP1476%20%3Ftitle%7D%20%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP1813%20%3Fshort_title.%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP407%20%3Fll.%20%3Fll%20rdfs%3Alabel%20%3Flanguage.%0A%20%20%20%20%20%20%20%20%20%20%20FILTER%28lang%28%3Flanguage%29%3D%22en%22%29%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP495%20%3Fcc.%20%3Fcc%20rdfs%3Alabel%20%3Fcountry.%0A%20%20%20%20%20%20%20%20%20%20%20FILTER%28lang%28%3Fcountry%29%3D%22en%22%29%7D%0A%20%20%20%20optional%7B%3Fitem%20wdt%3AP921%20%3Fmain_subject.%20%0A%20%20%20%20%20%20%20%20%20%20%20%3Fmain_subject%20rdfs%3Alabel%20%3Fmain_subjectLabel.%0A%20%20%20%20%20%20%20%20%20%20%20FILTER%28lang%28%3Fmain_subjectLabel%29%3D%22en%22%29%20%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP123%20%3Fpublisher.%20%0A%20%20%20%20%20%20%20%20%20%20%20%3Fpublisher%20rdfs%3Alabel%20%3FpublisherLabel.%0A%20%20%20%20%20%20%20%20%20%20%20FILTER%28lang%28%3FpublisherLabel%29%3D%22en%22%29%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP5769%20%3Feic.%20%0A%20%20%20%20%20%20%20%20%20%20%20%3Feic%20rdfs%3Alabel%20%3FeicLabel.%20%0A%20%20%20%20%20%20%20%20%20%20%20FILTER%28lang%28%3FeicLabel%29%3D%22en%22%29.%0A%20%20%20%20%20%20%20%20%20%20%20optional%7B%3Feic%20wdt%3AP496%20%3Feic_orcid.%7D%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP98%20%3Feditor.%20%0A%20%20%20%20%20%20%20%20%20%20%20%3Feditor%20rdfs%3Alabel%20%3FeditorLabel.%0A%20%20%20%20%20%20%20%20%20%20%20FILTER%28lang%28%3FeditorLabel%29%3D%22en%22%29.%0A%20%20%20%20%20%20%20%20%20%20%20optional%7B%3Feditor%20wdt%3AP496%20%3Feditor_orcid.%7D%7D%0A%20%20%20%7D%20%0AGROUP%20BY%20%3Fitem%20%3Fitemlabel_en%0A%7D%20as%20%25sss%0AWHERE%20%7B%0AINCLUDE%20%25sss%20.%0A%20%20%20optional%7B%3Fitem%20rdfs%3Alabel%20%3Fitemlabel_en.%20FILTER%28lang%28%3Fitemlabel_en%29%3D%22en%22%29%7D%0A%20%20%20optional%7B%3Fitem%20rdfs%3Alabel%20%3Fitemlabel_ru.%20FILTER%28lang%28%3Fitemlabel_ru%29%3D%22ru%22%29%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP10952%20%3Felibrary%7D%20%20%20%20%0A%20%20%20optional%7B%3Fitem%20wdt%3AP571%20%3Finception%7D%20%0A%20%20%20optional%7B%3Fitem%20wdt%3AP112%20%3Ffounded%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP527%20%3Fhas_part%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP361%20%3Fpart_of%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP155%20%3Ffollows%7D%20%20%0A%20%20%20optional%7B%3Fitem%20wdt%3AP156%20%3Ffollowed%7D%20%20%20%20%20%20%20%20%20%0A%20%20%20optional%7B%3Fitem%20wdt%3AP1365%20%3Freplaces%7D%20%0A%20%20%20optional%7B%3Fitem%20wdt%3AP1366%20%3Freplaced%7D%0A%20%20%20optional%7B%3Fitem%20wdt%3AP2669%20%3Fdiscontinued%7D%20%20%0A%20%20%20optional%7B%3Fitem%20wdt%3AP9745%20%3Ftranslation%7D%0A%20%20%20optional%20%7B%0A%20%20%20%20%20%3FarticleEN%20schema%3Aabout%20%3Fitem.%0A%20%20%20%20%20%3FarticleEN%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fen.wikipedia.org%2F%3E.%0A%20%20%20%20%20%3FarticleRU%20schema%3Aabout%20%3Fitem.%0A%20%20%20%20%20%3FarticleRU%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fru.wikipedia.org%2F%3E.%0A%20%20%20%20%7D%0A%7D"
target="_blank">отправить через Wikidata Query Service</a>

------------------------------------------------------------------------

### Все российские журналы в Wikidata

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**SPARQL**

``` r
SELECT DISTINCT ?journal ?name WHERE {
  VALUES ?type {wd:Q5633421 wd:Q737498}
  ?country wdt:P17 wd:Q159.
  ?journal wdt:P31/wdt:P279* ?type;  wdt:P495 ?country.     
  SERVICE wikibase:label {
    bd:serviceParam wikibase:language "en, ru".
    ?journal rdfs:label ?name .
  }
}
```

<a
href="https://query.wikidata.org/#SELECT%20DISTINCT%20%3Fjournal%20%3Fname%20WHERE%20%7B%0A%20%20VALUES%20%3Ftype%20%7Bwd%3AQ5633421%20wd%3AQ737498%7D%0A%20%20%3Fcountry%20wdt%3AP17%20wd%3AQ159.%0A%20%20%3Fjournal%20wdt%3AP31%2Fwdt%3AP279%2a%20%3Ftype%3B%20%20wdt%3AP495%20%3Fcountry.%20%20%20%20%20%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22en%2C%20ru%22.%0A%20%20%20%20%3Fjournal%20rdfs%3Alabel%20%3Fname%20.%0A%20%20%7D%0A%7D"
target="_blank">отправить через Wikidata Query Service</a>

------------------------------------------------------------------------

### Количество статей в Wikidata в российских журналах

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**SPARQL**

``` r
SELECT DISTINCT ?journal ?journal_title (count(?item) as ?count) 
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

<a
href="https://query.wikidata.org/#SELECT%20DISTINCT%20%3Fjournal%20%3Fjournal_title%20%28count%28%3Fitem%29%20as%20%3Fcount%29%20%0AWITH%20%7B%0A%20SELECT%20DISTINCT%20%3Fjournal%20%3Fjournal_title%20%0A%20%20WHERE%20%7B%0A%20%20%20%20VALUES%20%3Ftype%20%7Bwd%3AQ5633421%20wd%3AQ737498%7D.%0A%20%20%20%20%20%20%20%20%20%20%20%3Fjournal%20wdt%3AP31%2Fwdt%3AP279%20%3Ftype%3B%20wdt%3AP495%20wd%3AQ159.%0A%20%20%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%2Cru%22.%20%0A%20%20%20%20%20%20%3Fjournal%20rdfs%3Alabel%20%3Fjournal_title.%0A%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%7D%20as%20%25sss%20%0AWHERE%20%7B%0A%20%20INCLUDE%20%25sss%20.%0A%20%20%3Fitem%20wdt%3AP1433%20%3Fjournal%3B%20wdt%3AP31%20wd%3AQ13442814.%0A%20%20%7D%0AGROUP%20BY%20%3Fjournal%20%3Fjournal_title%0A"
target="_blank">отправить через Wikidata Query Service</a>

------------------------------------------------------------------------

### Извлечение источников заданного свойства

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**SPARQL**

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

<a
href="https://query.wikidata.org/#SELECT%20%3Fissn%20%3Fref%20%3FrefLabel%20%0AWHERE%20%7B%0A%20%20wd%3AQ3453517%20p%3AP236%20%5B%0A%20%20%20%20ps%3AP236%20%3Fissn%3B%20prov%3AwasDerivedFrom%20%5B%0A%20%20%20%20%20%20pr%3AP248%7Cpr%3AP143%20%3Fref%20%0A%20%20%20%20%5D%0A%20%20%5D.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22en%22.%20%7D%0A%7D%0A%0A"
target="_blank">отправить через Wikidata Query Service</a>

------------------------------------------------------------------------

### Статьи из выбранного журнала и цитирующие их журналы

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**SPARQL**

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

<a
href="https://query.wikidata.org/#SELECT%20DISTINCT%20%3Fdoi%20%3FitemLabel%20%3FcitingJournalLabel%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%28count%28distinct%28%3Fciting_pub%29%29%20as%20%3Fcount%29%0AWHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP1433%20wd%3AQ246955%3B%20%0A%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP356%20%3Fdoi.%20%0A%20%20optional%7B%20%0A%20%20%20%20%3Fciting_pub%20wdt%3AP2860%20%3Fitem%3B%20%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP1433%20%3FcitingJournal.%0A%20%20%7D%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2C%20en%2C%20ru%22.%0A%20%20%20%20%20%20%3Fitem%20rdfs%3Alabel%20%3FitemLabel%20.%0A%20%20%20%20%20%20%3FcitingJournal%20rdfs%3Alabel%20%3FcitingJournalLabel%20.%0A%20%20%7D%0A%7D%0AGROUP%20BY%20%3Fdoi%20%3FitemLabel%20%3FcitingJournalLabel%0AORDER%20BY%20%3FitemLabel%0A"
target="_blank">отправить через Wikidata Query Service</a>

------------------------------------------------------------------------

### Список авторов выбранного журнала, имеющих ORCID

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**SPARQL**

``` r
SELECT DISTINCT ?author_id ?orcid_ ?author
WHERE {
   ?item wdt:P1433 wd:Q246955.
   optional{
           ?item p:P50|p:P2093 ?author_statement .
           ?author_statement ps:P50|ps:P2093 ?author_id .
           ?author_id wdt:P496 ?orcid. }
  SERVICE wikibase:label {
    bd:serviceParam wikibase:language "[AUTO_LANGUAGE], en, ru".
    ?author_id rdfs:label ?author .
  }
}
```

<a
href="https://query.wikidata.org/#SELECT%20DISTINCT%20%3Fauthor_id%20%3Forcid_%20%3Fauthor%0AWHERE%20%7B%0A%20%20%20%3Fitem%20wdt%3AP1433%20wd%3AQ246955.%0A%20%20%20optional%7B%0A%20%20%20%20%20%20%20%20%20%20%20%3Fitem%20p%3AP50%7Cp%3AP2093%20%3Fauthor_statement%20.%0A%20%20%20%20%20%20%20%20%20%20%20%3Fauthor_statement%20ps%3AP50%7Cps%3AP2093%20%3Fauthor_id%20.%0A%20%20%20%20%20%20%20%20%20%20%20%3Fauthor_id%20wdt%3AP496%20%3Forcid.%20%7D%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2C%20en%2C%20ru%22.%0A%20%20%20%20%3Fauthor_id%20rdfs%3Alabel%20%3Fauthor%20.%0A%20%20%7D%0A%7D%0A"
target="_blank">отправить через Wikidata Query Service</a>

------------------------------------------------------------------------

### Женщины-ученые с наградами, цитировавшие выбранный журнал

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**SPARQL**

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

<a
href="https://query.wikidata.org/#SELECT%20%3FauthorLabel%20%3Forcid%20%3Fawards%0AWITH%20%7B%0A%20%20SELECT%20%3Fauthor%20%0A%20%20%20%20%28GROUP_CONCAT%28DISTINCT%28%3Faward%29%3B%20separator%3D%22%20%7C%20%22%29%20AS%20%3Fawards%29%0A%20%20WHERE%20%7B%0A%20%20%3Fwork%20wdt%3AP1433%20wd%3AQ4300349.%0A%20%20%3Freference_pub%20wdt%3AP2860%20%3Fwork.%0A%20%20%3Freference_pub%20wdt%3AP50%20%3Fauthor%20.%0A%20%20%3Fauthor%20p%3AP166%20%3Faward_statement.%0A%20%20%3Faward_statement%20ps%3AP166%20%3Faward_.%0A%20%20%3Fauthor%20wdt%3AP21%20wd%3AQ6581072%20.%0A%20%20%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22%20.%20%0A%20%20%20%20%20%20%3Faward_%20rdfs%3Alabel%20%3Faward.%0A%20%20%20%20%7D%20%0A%20%20%7D%0AGROUP%20BY%20%3Fauthor%20%20%0A%7D%20AS%20%25result%0AWHERE%20%7B%0A%20%20INCLUDE%20%25result%20%0A%20%20%20optional%7B%3Fauthor%20wdt%3AP496%20%3Forcid%20.%7D%0A%20%20%20%20SERVICE%20wikibase%3Alabel%20%7B%20%0A%09%20%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22%20.%0A%20%20%20%20%20%20%20%20%3Fauthor%20rdfs%3Alabel%20%3FauthorLabel.%09%0A%20%20%09%7D%0A%20%7D%0A"
target="_blank">отправить через Wikidata Query Service</a>

------------------------------------------------------------------------

### Российские ученые, имеющие ORCID и страницу в RU-Wikipedia

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**SPARQL**

``` r
SELECT DISTINCT ?author ?authorLabel ?orcid ?article
  WHERE {
    ?author wdt:P31 wd:Q5; 
            wdt:P27 wd:Q159;
            wdt:P496 ?orcid.      
    optional{?article schema:about ?author.
         ?article schema:isPartOf <https://ru.wikipedia.org/>.
           }
SERVICE wikibase:label { 
    bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en" . }
}
```

<a
href="https://query.wikidata.org/#SELECT%20DISTINCT%20%3Fauthor%20%3FauthorLabel%20%3Forcid%20%3Farticle%0A%20%20WHERE%20%7B%0A%20%20%20%20%3Fauthor%20wdt%3AP31%20wd%3AQ5%3B%20%0A%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP27%20wd%3AQ159%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP496%20%3Forcid.%20%20%20%20%20%20%0A%20%20%20%20optional%7B%3Farticle%20schema%3Aabout%20%3Fauthor.%0A%20%20%20%20%20%20%20%20%20%3Farticle%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fru.wikipedia.org%2F%3E.%0A%20%20%20%20%20%20%20%20%20%20%20%7D%0ASERVICE%20wikibase%3Alabel%20%7B%20%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22%20.%20%7D%0A%7D%0A"
target="_blank">отправить через Wikidata Query Service</a>

------------------------------------------------------------------------

### Исследователи младше 30 лет, имеющие статью в EN Wikipedia

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**SPARQL**

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

<a
href="https://query.wikidata.org/#SELECT%20%3Fsitelink%20%3FitemLabel%20WHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP106%20wd%3AQ901%3B%0A%20%20%20%20%20%20%20%20wdt%3AP31%20wd%3AQ5%3B%0A%20%20%20%20%20%20%20%20wdt%3AP569%20%3Fborn%20.%0A%20%20FILTER%20%28%3Fborn%20%3E%3D%20%221993-04-24T00%3A00%3A00Z%22%5E%5Exsd%3AdateTime%29.%20%0A%20%20%23%20exclude%20if%20there%20is%20a%20date%20of%20death%0A%20%20MINUS%20%7B%3Fitem%20wdt%3AP570%20%5B%5D%7D%20%20%20%20%0A%20%20%3Fsitelink%20schema%3Aabout%20%3Fitem%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fen.wikipedia.org%2F%3E.%20%20%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22en%22%0A%20%20%20%7D.%0A%7D%20%20%0AORDER%20BY%20%3FitemLabel%0A"
target="_blank">отправить через Wikidata Query Service</a>

------------------------------------------------------------------------

### Перечень университетов, расположенных в \<=500 метрах от метро

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**SPARQL**

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

<a
href="https://query.wikidata.org/index.html#%23defaultView%3AMap%0ASELECT%20%3Fplace%20%3FplaceLabel%20%3FsubwayLabel%20%3Flocation%20WHERE%0A%7B%20%0A%20%20%3Fsubway%20wdt%3AP131%2B%20wd%3AQ649%3B%0A%20%20%20%20%20%20%20%20%20%20wdt%3AP31%20wd%3AQ928830.%0A%20%20%3Fsubway%20wdt%3AP625%20%3FarcLoc%20.%0A%20%20SERVICE%20wikibase%3Aaround%20%7B%0A%20%20%20%20%20%20%3Fplace%20wdt%3AP625%20%3Flocation%20.%0A%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Acenter%20%3FarcLoc%20.%0A%20%20%20%20%20%20bd%3AserviceParam%20wikibase%3Aradius%20%220.5%22%20.%0A%20%20%7D%0A%20%20%20%20%3Fplace%20wdt%3AP31%20wd%3AQ3918.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22ru%22%20.%0A%20%20%7D%0A%7D%0A"
target="_blank">отправить через Wikidata Query Service</a>

------------------------------------------------------------------------

### Перечень организаций, цитировавших статьи из выбранного журнала

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**SPARQL**

``` r
SELECT DISTINCT ?citing_organizationLabel ?citing_countryLabel 
     (COUNT(DISTINCT ?doi) AS ?n_dois)
     (GROUP_CONCAT(DISTINCT ?doi; separator = "; ") as ?list_of_dois)
WHERE {
  ?item wdt:P1433 wd:Q246955;
        wdt:P356 ?doi. 
  ?citing_work wdt:P2860 ?item; 
        wdt:P50 ?citing_author . 
  ?citing_author (wdt:P108|wdt:P1416) ?citing_organization . 
  ?citing_organization wdt:P17 ?citing_country.
  SERVICE wikibase:label { 
    bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". 
    }      
  }
GROUP BY ?citing_organizationLabel ?citing_countryLabel
ORDER BY DESC(?n_dois)
```

<a
href="https://query.wikidata.org/index.html#SELECT%20DISTINCT%20%3Fciting_organizationLabel%20%3Fciting_countryLabel%20%0A%20%20%20%20%20%28COUNT%28DISTINCT%20%3Fdoi%29%20AS%20%3Fn_dois%29%0A%20%20%20%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fdoi%3B%20separator%20%3D%20%22%3B%20%22%29%20as%20%3Flist_of_dois%29%0AWHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP1433%20wd%3AQ246955%3B%0A%20%20%20%20%20%20%20%20wdt%3AP356%20%3Fdoi.%20%0A%20%20%3Fciting_work%20wdt%3AP2860%20%3Fitem%3B%20%0A%20%20%20%20%20%20%20%20wdt%3AP50%20%3Fciting_author%20.%20%0A%20%20%3Fciting_author%20%28wdt%3AP108%7Cwdt%3AP1416%29%20%3Fciting_organization%20.%20%0A%20%20%3Fciting_organization%20wdt%3AP17%20%3Fciting_country.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%0A%20%20%20%20%7D%20%20%20%20%20%20%0A%20%20%7D%0AGROUP%20BY%20%3Fciting_organizationLabel%20%3Fciting_countryLabel%0AORDER%20BY%20DESC%28%3Fn_dois%29%0A"
target="_blank">отправить через Wikidata Query Service</a>

------------------------------------------------------------------------

### Исследователи, цитировавшие статьи из журнала со списком цитирующих и процитированных статей

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**SPARQL**

``` r
SELECT DISTINCT ?citing_authorLabel ?orcid
     (COUNT(DISTINCT ?doi) AS ?n_dois)
     (GROUP_CONCAT(DISTINCT ?doi; separator = "; ") as ?list_of_cited_dois)
     (GROUP_CONCAT(DISTINCT ?citing_doi; separator = "; ") as ?list_of_citing_dois)
WHERE {
  ?item wdt:P1433 wd:Q246955;
        wdt:P356 ?doi. 
  ?citing_work wdt:P2860 ?item; 
        wdt:P50 ?citing_author;
        wdt:P356 ?citing_doi.
 optional{?citing_author wdt:P496 ?orcid.} 
  SERVICE wikibase:label { 
    bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". 
    }      
  }
GROUP BY ?citing_authorLabel ?orcid
ORDER BY DESC(?n_dois)
```

<a
href="https://query.wikidata.org/index.html#SELECT%20DISTINCT%20%3Fciting_authorLabel%20%3Forcid%0A%20%20%20%20%20%28COUNT%28DISTINCT%20%3Fdoi%29%20AS%20%3Fn_dois%29%0A%20%20%20%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fdoi%3B%20separator%20%3D%20%22%3B%20%22%29%20as%20%3Flist_of_cited_dois%29%0A%20%20%20%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fciting_doi%3B%20separator%20%3D%20%22%3B%20%22%29%20as%20%3Flist_of_citing_dois%29%0AWHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP1433%20wd%3AQ246955%3B%0A%20%20%20%20%20%20%20%20wdt%3AP356%20%3Fdoi.%20%0A%20%20%3Fciting_work%20wdt%3AP2860%20%3Fitem%3B%20%0A%20%20%20%20%20%20%20%20wdt%3AP50%20%3Fciting_author%3B%0A%20%20%20%20%20%20%20%20wdt%3AP356%20%3Fciting_doi.%0A%20optional%7B%3Fciting_author%20wdt%3AP496%20%3Forcid.%7D%20%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%0A%20%20%20%20%7D%20%20%20%20%20%20%0A%20%20%7D%0AGROUP%20BY%20%3Fciting_authorLabel%20%3Forcid%0AORDER%20BY%20DESC%28%3Fn_dois%29%0A%0A"
target="_blank">отправить через Wikidata Query Service</a>

------------------------------------------------------------------------

### Статьи из журнала и цитирующие их организации и страны

**[`^        back to top        ^`](#wikipedia-rest-api-wp)**

**SPARQL**

``` r
SELECT DISTINCT ?doi ?itemLabel 
    (COUNT(DISTINCT ?citing_work) AS ?n_cited)
    (GROUP_CONCAT(DISTINCT ?citing_organizationLabel; separator = "; ") as ?list_of_orgs)
    (GROUP_CONCAT(DISTINCT ?citing_countryLabel; separator = "; ") as ?list_of_countries)
WHERE {
  ?item wdt:P1433 wd:Q246955;
        wdt:P356 ?doi. 
  ?citing_work wdt:P2860 ?item; 
        wdt:P50 ?citing_author . 
  ?citing_author (wdt:P108|wdt:P1416) ?citing_organization . 
  ?citing_organization wdt:P17 ?citing_country.
  SERVICE wikibase:label { 
    bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". 
    ?citing_organization rdfs:label ?citing_organizationLabel.
    ?citing_country rdfs:label ?citing_countryLabel.
    ?item rdfs:label ?itemLabel.
   }      
 }
GROUP BY ?doi ?itemLabel
ORDER BY DESC(?n_cited)
```

<a
href="https://query.wikidata.org/index.html#SELECT%20DISTINCT%20%3Fdoi%20%3FitemLabel%20%0A%20%20%20%20%28COUNT%28DISTINCT%20%3Fciting_work%29%20AS%20%3Fn_cited%29%0A%20%20%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fciting_organizationLabel%3B%20separator%20%3D%20%22%3B%20%22%29%20as%20%3Flist_of_orgs%29%0A%20%20%20%20%28GROUP_CONCAT%28DISTINCT%20%3Fciting_countryLabel%3B%20separator%20%3D%20%22%3B%20%22%29%20as%20%3Flist_of_countries%29%0AWHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP1433%20wd%3AQ246955%3B%0A%20%20%20%20%20%20%20%20wdt%3AP356%20%3Fdoi.%20%0A%20%20%3Fciting_work%20wdt%3AP2860%20%3Fitem%3B%20%0A%20%20%20%20%20%20%20%20wdt%3AP50%20%3Fciting_author%20.%20%0A%20%20%3Fciting_author%20%28wdt%3AP108%7Cwdt%3AP1416%29%20%3Fciting_organization%20.%20%0A%20%20%3Fciting_organization%20wdt%3AP17%20%3Fciting_country.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20%0A%20%20%20%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%0A%20%20%20%20%3Fciting_organization%20rdfs%3Alabel%20%3Fciting_organizationLabel.%0A%20%20%20%20%3Fciting_country%20rdfs%3Alabel%20%3Fciting_countryLabel.%0A%20%20%20%20%3Fitem%20rdfs%3Alabel%20%3FitemLabel.%0A%20%20%20%7D%20%20%20%20%20%20%0A%20%7D%0AGROUP%20BY%20%3Fdoi%20%3FitemLabel%0AORDER%20BY%20DESC%28%3Fn_cited%29%0A"
target="_blank">отправить через Wikidata Query Service</a>

### Лицензия

Список распространяется по лицензии [Creative Commons
Attribution-ShareAlike 3.0 Unported](LICENSE).

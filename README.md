API-Викисервисов для академических издателей
================
Лутай А.В.
2023-05-18

-   [API и SPARQL интерфейсы](#api-и-sparql-интерфейсы)
    -   [Wikipedia REST API (WP)](#wikipedia-rest-api-wp)
    -   [Wikimedia REST API (WM)](#wikimedia-rest-api-wm)
    -   [MediaWiki Action API (MWA)](#mediawiki-action-api-mwa)
    -   [Wikidata API (WD)](#wikidata-api-wd)
    -   [SPARQL](#sparql)
-   [Перечень типовых задач](#перечень-типовых-задач)
    -   [Сведения о статье в Wikipedia](#сведения-о-статье-в-wikipedia)
    -   [Другие названия объекта
        статьи](#другие-названия-объекта-статьи)
    -   [Все языковые версии статьи в
        Wikipedia](#все-языковые-версии-статьи-в-wikipedia)
    -   [История правок статьи в
        Wikipedia](#история-правок-статьи-в-wikipedia)
    -   [Получить Wikidata ID по названию статьи в
        Wikipedia](#получить-wikidata-id-по-названию-статьи-в-wikipedia)
    -   [Найти страницы Wikipedia по Wikidata
        ID](#найти-страницы-wikipedia-по-wikidata-id)
    -   [Цитировать статью Wikipedia в формате
        bibtex](#цитировать-статью-wikipedia-в-формате-bibtex)
    -   [Разделы статьи в Wikipedia](#разделы-статьи-в-wikipedia)
-   [Материалы на русском языке](#материалы-на-русском-языке)

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
открывающими запрос в интерфейсе [Wikidata Query
Service](https://query.wikidata.org/). Их также можно отправлять
программными средствами с помощью специальных пакетов для R:
[WikidataR](https://github.com/TS404/WikidataR), для Python: пакет
[Wikidata](https://github.com/dahlia/wikidata), [другие
примеры](https://www.wikidata.org/wiki/Wikidata:Tools/For_programmers)).

-   [Руководство по использованию SPARQL (частично на русском
    языке)](https://www.wikidata.org/wiki/Wikidata:SPARQL_tutorial/ru)

-   <https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/queries/examples>

-   <https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/queries/examples/advanced>

-   <https://www.wikidata.org/wiki/User:MartinPoulter/queries>

-   <https://wdqs-tutorial.toolforge.org/>

-   [Архив SPARQL запросов 2015-2022 из еженедельных
    дайджестов)](https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/qotw)

------------------------------------------------------------------------

## Перечень типовых задач

### Сведения о статье в Wikipedia

**WP**

Возвращает json с ID последней правки и подробным wiki-text HTML
(infobox, ссылки с библиографическими деталями и т.д.).

> <https://en.wikipedia.org/w/rest.php/v1/page/The%20BMJ>

**MWA**

Возвращает в JSON текст, языковые версии, категории, ссылки на страницы
Wikipedia, ссылка на внешние страницы, перечень изображений, секций,
шаблонов, интер-вики ссылок и wikibase item (в properties)

> <https://en.wikipedia.org/w/api.php?action=parse&page=The%20BMJ&format=json>

**WM**

Возвращает namespace, Wikibase ID, название, thumbnail, original image,
последнюю правку с временной отметкой и ID, аннотацию (текст и HTML).

> <https://en.wikipedia.org/api/rest_v1/page/summary/The%20BMJ>

------------------------------------------------------------------------

### Другие названия объекта статьи

**MWA**

> <https://en.wikipedia.org/w/api.php?action=query&prop=pageterms&titles=The%20BMJ&format=json>

------------------------------------------------------------------------

### Все языковые версии статьи в Wikipedia

**WP**

возвращает только названия страниц

> <https://en.wikipedia.org/w/rest.php/v1/page/The_Lancet/links/language>

**MWA**

возвращает pageid для страниц объекта и полные URL на страницы языковых
версий

> <https://en.wikipedia.org/w/api.php?action=query&titles=The_Lancet&prop=langlinks&format=json&llprop=url&lllimit=500>

------------------------------------------------------------------------

### История правок статьи в Wikipedia

**WM**

возвращает последнюю правку и имя последнего пользователя

> <a href="https://ru.wikipedia.org/api/rest_v1/page/title/Доклады"
> class="uri">https://ru.wikipedia.org/api/rest_v1/page/title/Доклады</a>
> Академии наук

**WP**

возвращает историю правок с id изменения, временем правки, данными о
создателе (id, name) и размером правок (delta).

> <a
> href="https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history"
> class="uri">https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history</a>

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
> class="uri">https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history?older_than=97918317&amp;filter=anonymous</a>

**Количество правок**

> <a
> href="https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history/counts/edits"
> class="uri">https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history/counts/edits</a>
> <a
> href="https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history/counts/edits?from=88695017&amp;to=97918317"
> class="uri">https://ru.wikipedia.org/w/rest.php/v1/page/Доклады%20Академии%20наук/history/counts/edits?from=88695017&amp;to=97918317</a>

### Получить Wikidata ID по названию статьи в Wikipedia

**MWA**

возвращает Wikibase ID (aka Wikidata ID) и wikibase-shortdesc (если
есть)

> <a
> href="https://ru.wikipedia.org/w/api.php?action=query&amp;prop=pageprops&amp;format=json&amp;titles=Криосфера_Земли"
> class="uri">https://ru.wikipedia.org/w/api.php?action=query&amp;prop=pageprops&amp;format=json&amp;titles=Криосфера_Земли</a>

**WP**

возвращает информацию о странице, в которой есть поле wikibase_item

> <a
> href="https://ru.wikipedia.org/api/rest_v1/page/summary/Криосфера_Земли"
> class="uri">https://ru.wikipedia.org/api/rest_v1/page/summary/Криосфера_Земли</a>

**WD**

возвращает все запрошенные элементы Wikidata. При запросе русскоязычной
страницы необходимо заменить enwiki на ruwiki, можно также получать
заголовки на нескольких языках (en\|ru).

> [`https://www.wikidata.org/w/api.php?action=wbgetentities&format=json&sites=ruwiki&titles=Журнал_технической_физики&props=info|labels|descriptions|claims&languages=en|ru`](https://www.wikidata.org/w/api.php?action=wbgetentities&format=json&sites=ruwiki&titles=Журнал_технической_физики&props=info%7Clabels%7Cdescriptions%7Cclaims&languages=en%7Cru)

**SPARQL**

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

------------------------------------------------------------------------

### Найти страницы Wikipedia по Wikidata ID

**MWA**

> <https://www.wikidata.org/w/api.php?action=wbgetentities&format=xml&props=sitelinks&ids=Q3453517>

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

[отправить через Wikidata Query
Service](https://query.wikidata.org/#SELECT%20DISTINCT%20%3Farticle%20WHERE%20%7B%0A%20%20VALUES%20%3Fitem%20%7Bwd%3AQ3453517%7D%0A%20%20%3Farticle%20schema%3Aabout%20%3Fitem%3B%0A%20%20%20%20%20%20%20%20%20%20%20schema%3AisPartOf%20%3Chttps%3A%2F%2Fru.wikipedia.org%2F%3E%0A%7D%0A)

------------------------------------------------------------------------

### Цитировать статью Wikipedia в формате bibtex

**WM**

Сервис поддерживает также формат zotero и несколько других (mediawiki,
wikibase). Цитируемый URL включает параметр oldid – идентификатор
последней правки на момент цитирования! Обратите внимание на
необходимость URL-кодирования гиперссылки страницы Wikipedia.

> <a
> href="https://en.wikipedia.org/api/rest_v1/data/citation/bibtex/https%3A%2F%2Fru.wikipedia.org%2Fwiki%2FЖурнал_технической_физики"
> class="uri">https://en.wikipedia.org/api/rest_v1/data/citation/bibtex/https%3A%2F%2Fru.wikipedia.org%2Fwiki%2FЖурнал_технической_физики</a>

### Разделы статьи в Wikipedia

**MWA**

[Инструкция](https://www.mediawiki.org/wiki/API:Parsing_wikitext)

Возвращает перечень разделов страницы Wikipedia, их размер, порядковые
номера и названия внутренних ссылок.

> <https://en.wikipedia.org/w/api.php?action=parse&format=json&page=The%20BMJ&prop=sections>

Получив сведения из запроса выше, можно извлечь отдельные разделы в
форматах wikitext или parsetree

> <https://en.wikipedia.org/w/api.php?action=parse&page=The%20BMJ&prop=wikitext%7Cparsetree&section=5&format=json>

------------------------------------------------------------------------

## Материалы на русском языке

**Базовые сведения:**

-   <a
    href="https://ru.wikipedia.org/wiki/%D0%92%D0%B8%D0%BA%D0%B8%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5"
    target="_blank">Статья “Викиданные” в Википедии</a>

-   <a
    href="https://ru.wikisource.org/wiki/%D0%A1%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0:%D0%92%D0%B8%D0%BA%D0%B8%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5"
    target="_blank">Статья “Викиданные” в Викитеке</a>

**Популярным языком:**

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

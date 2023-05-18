Wiki Services for Academic Journals
================
Лутай А.В.
2023-05-18

-   [Справочники и руководства](#справочники-и-руководства)
    -   [Wikipedia REST API](#wikipedia-rest-api)
    -   [Wikimedia REST API](#wikimedia-rest-api)

## Справочники и руководства

### Wikipedia REST API

-   <https://www.mediawiki.org/wiki/API:REST_API>
-   <https://www.mediawiki.org/wiki/API:REST_API/Reference>

**Перелистывание результатов** -
<https://www.mediawiki.org/wiki/API:Continue>

### Wikimedia REST API

-   <https://en.wikipedia.org/api/rest_v1/#/>

**Спецификация API в JSON** -
<https://en.wikipedia.org/api/rest_v1/?spec>

------------------------------------------------------------------------

**Wikipedia REST API**

возвращает json с ID последней правки и подробным wiki-text HTML
(infobox, ссылки с библиографич. деталями и т.д.).

``` r
https://en.wikipedia.org/w/rest.php/v1/page/Earth
```

**MediaWiki Action API**

> <https://en.wikipedia.org/w/api.php?action=parse&page=Earth&format=json>

возвращает текст, языковые версии, категории, ссылки на страницы
Wikipedia, ссылка на внешние страницы, перечень изображений, секций,
шаблонов, интер-вики ссылок и wikibase item (в properties)

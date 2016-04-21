### 4.5  Знайомство з інструментами вилучення - екстракцією

Екстрактор пошукача WebMagic extraction  базується на використанні [Jsoup](http://jsoup.org/) і моїй власній розробки  [Xsoup](https://github.com/code4craft/xsoup).

#### 4.5.1 Jsoup

Jsoup це простий HTML-парсер, що підтримує використання CSS селекторів, як спосіб знайти елементи. Для цілей розробки WebMagic, проведено детальний аналіз з сирцевим кодом Jsoup конкретних статей см [Jsoup - нотатки дослідженнь](https://github.com/code4craft/jsoup-learning).

#### 4.5.2 Xsoup
[Xsoup](https://github.com/code4craft/xsoup) заснований на Jsoup, розроблявся як XPath аналізатор.
Раніше застосовувався для парсера WebMagic [HtmlCleaner](http://htmlcleaner.sourceforge.net/), у якого є деякі проблеми під час використання. Основна його проблема полягає в XPath - локалізація помилки не є точною, і у якого не резонна структура коду, це складно налаштувати. Я, нарешті, реалізувавXsoup, що робить необхідну розробити більш відповідною до пошукових сканерів. Приємно відзначити, що тестування показує, продуктивність Xsoup перевищує HtmlCleaner більше, аніж в два рази.
Розробка Xsoup продовжується і досі, зараз підтримується загальний синтаксис для парсингу, що приведено у таблиці нижче:

<table>
    <tr>
        <td>Назва</td>
        <td>Вираз</td>
        <td>Підтримка</td>
    </tr>
    <tr>
        <td>nodename</td>
        <td>nodename</td>
        <td>yes</td>
    </tr>
    <tr>
        <td>immediate parent</td>
        <td>/</td>
        <td>yes</td>
    </tr>
    <tr>
        <td>parent</td>
        <td>//</td>
        <td>yes</td>
    </tr>
    <tr>
        <td>attribute</td>
        <td>[@key=value]</td>
        <td>yes</td>
    </tr>
    <tr>
        <td>nth child</td>
        <td>tag[n]</td>
        <td>yes</td>
    </tr>
    <tr>
        <td>attribute</td>
        <td>/@key</td>
        <td>yes</td>
    </tr>
    <tr>
        <td>wildcard in tagname</td>
        <td>/*</td>
        <td>yes</td>
    </tr>
    <tr>
        <td>wildcard in attribute</td>
        <td>/[@*]</td>
        <td>yes</td>
    </tr>
    <tr>
        <td>function</td>
        <td>function()</td>
        <td>part</td>
    </tr>
    <tr>
        <td>or</td>
        <td>a | b</td>
        <td>yes since 0.2.0</td>
    </tr>
    <tr>
        <td>parent in path</td>
        <td>. or ..</td>
        <td>no</td>
    </tr>
    <tr>
        <td>predicates</td>
        <td>price>35</td>
        <td>no</td>
    </tr>
    <tr>
        <td>predicates logic</td>
        <td>@class=a or @class=b</td>
        <td>yes since 0.2.0</td>
    </tr>
</table>

Зазначу, що власні мої умовні визначення для особистого пошукочав, що дуже зручно використовують функції XPath. Зверніть увагу, проте, ці функції не є стандартами XPath.

| Вираз | Опис | XPath1.0 |
| -------- | ------- | ------- |
|text(n) | текст безпосередньо n-го дочірнього вузола, якщо 0 - тоді для всіх | тільки text()|
|allText() | всі прямі і непрямі тексти дочірніх вузлів | не підтримує |
|tidyText() | всі прямі і непрямі тексти дочірніх вузлів, а також замінити деякі мітки обгорок, так, щоб відображався очищенний звичайний текст | не підтримує |
| html() | внутрішній HTML, HTML теги не вміщати в себе | не підтримує |
| outerHtml() | внутрішній HTML, вміщувати в тому числі тегі HTML у себе | не підтримує |
| regex(@attr,expr,group)  | тут @attr і може бути вибраний з групи, за замовчуванням group0 | не підтримує |

#### 4.5.3 Saxon

Saxon є потужним аналізатор XPath з підтримкою XPath 2.0 синтаксису. `Webmagic-saxon` інтеграція з Saxon є попередніми, але тепер  схоже, синтакис XPath 2.0 є передовим, і здається, що його використовують у розробці не так багато пошукових сканерів.
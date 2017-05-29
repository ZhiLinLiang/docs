# Зміст

Це стислий зміст книги.

* [Огляд WebMagic](posts/ch1-overview/README.md)
	* [Філософія](posts/ch1-overview/philosophy.md)
	* [Архітектура](posts/ch1-overview/architecture.md)
	* [Компоненти](posts/ch1-overview/component.md)
* [Збирання](posts/ch2-install/README.md)
	* [з використанням `Maven`](posts/ch2-install/with-maven.md)
	* [Без `Maven`](posts/ch2-install/without-maven.md)
	* [Перший проет](posts/ch2-install/first-project.md)
* [Білд з сирцевого коду](posts/ch3-build-source/README.md)
	* [Отримати сирці](posts/ch3-build-source/git-repo.md)
	* [Імпорт проекту](posts/ch3-build-source/import-project.md)
	* [Білд та запуск на прикладах](posts/ch3-build-source/compile-code.md)
* [Основні функції у пошукового робота](posts/ch4-basic-page-processor/README.md)
	* [Імплементація `PageProcessor` -а](posts/ch4-basic-page-processor/pageprocessor.md)
	* [Послідовність селекторності з `API Selectable`](posts/ch4-basic-page-processor/selectable.md)
	* [Збереження результатів](posts/ch4-basic-page-processor/results.md)
	* [Конфігурація пошукача, запуск і зупинка](posts/ch4-basic-page-processor/spider-config.md)
	* [Знайомство з інструментами вилучення - екстракцією: Jsoup та Xsoup](posts/ch4-basic-page-processor/xsoup.md)
	* [Монітор з `JMX`](posts/ch4-basic-page-processor/monitor.md)
* [Використання анотацій при написанні пошукача](posts/ch5-annotation/README.md)
	* [Написання класу Model](posts/ch5-annotation/model.md)
	* [`TargetUrl` та `HelpUrl`](posts/ch5-annotation/targeturl.md)
	* [`@ExtractBy`](posts/ch5-annotation/extractby.md)
	* [Використання `@ExtractBy` у классі](posts/ch5-annotation/extractby-on-class.md)
	* [Форматування результатів](posts/ch5-annotation/formatter.md)
	* [Життєвий цикл](posts/ch5-annotation/lifecycle.md)
	* [`AfterExtractor`](posts/ch5-annotation/after-extractor.md)
* [Налаштування компонентів](posts/ch6-custom-componenet/README.md)
	* [Кастомизація конвееру `Pipeline`](posts/ch6-custom-componenet/pipeline.md)
	* [Планувальник `Scheduler`](posts/ch6-custom-componenet/scheduler.md)
	* [Завантажувач `Downloader`](posts/ch6-custom-componenet/downloader.md)
* [Навчальны приклади](posts/chx-cases/README.md)
    * [Основні комбінації сторінки та список деталей](posts/chx-cases/basic-list-target.md)
    * [Обробка пошукачем сторінок на JS рендерингу](posts/chx-cases/js-render-page.md)
    * Обробка пошукачем сторінки
    * Періодична обробка пошукачем
    * [Асинхронне завантаження з ajax](posts/chx-cases/ajax.md)
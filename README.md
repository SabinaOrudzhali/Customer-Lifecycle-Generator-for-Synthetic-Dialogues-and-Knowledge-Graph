# Customer Lifecycle Generator for Synthetic Dialogues and Knowledge Graph

## Customer Lifecycle Generator for Synthetic Dialogues

A script that generates a sequence of 5–7 interactions over several months for a fictional customer, including initial contact, complaints, product purchases, and repeat interactions. The generated data is suitable for testing a Knowledge Graph.

The notebook creates a synthetic dataset of customers, interactions, dialogues, and a Knowledge Graph. All data is fictional, and no external APIs are used.

## Project Objective

The objective of this project is to create a demonstration generator of customer lifecycles in synthetic banking dialogues.

The resulting dataset includes customers with different behavioral scenarios: brief interactions, purchases, complaints, repeat purchases, churn after a negative experience, and long interaction sequences spanning several months.

The generated data is used to build a Knowledge Graph, provide interactive visualization of customer journeys, and perform analytics across products, topics, interactions, and customer satisfaction.

## Library Installation and Imports

This cell checks whether the required libraries are installed. If a package is missing, it is automatically installed using pip.

## Reference Data and Generation Settings

Customer segments, communication channels, products, topics, lifecycle scenarios, and event-generation rules are defined.

## Synthetic Customer Generation

A `clients_df` DataFrame is created containing 50 fictional customers with assigned segments, communication channels, income levels, churn risk, and basic products.

Number of customers: **50**

## Generation of Different Customer Lifecycles

In this final version, customers do not follow a single common journey. Instead, they have different scenarios and different interaction sequence lengths.

The distribution is predefined to ensure that the dataset contains short, standard, and long customer journeys.

## Customer Interaction Generation

An `events_df` DataFrame is created.

Interaction dates are generated chronologically, with 7 to 45 days between events. The `previous_event_id` field links each event to the customer's previous interaction.

Total number of interactions: **243**

## Synthetic Dialogue Generation

For each customer interaction, 4–8 messages are generated in Russian.

The dialogues depend on the event type, product, topic, and customer sentiment.

Total number of messages: **1,444**

Messages per interaction: **4 to 8**

## Knowledge Graph Construction

The graph is built using `networkx.DiGraph()`.

It connects customers, interactions, messages, products, topics, lifecycle stages, scenarios, communication channels, sentiments, customer segments, and cities.

Number of nodes in the graph: **1,809**

Number of edges in the graph: **3,295**

## Interactive Customer Lifecycle Graph

The `show_client_lifecycle_graph(client_id)` function displays a customer, all of their interactions, the `EVENT_NEXT` sequence, products, topics, lifecycle stages, and the first messages associated with each event.

## Examples of Different Customer Graphs

Examples of different customer journeys are automatically selected below, including:

* a single interaction;
* a short journey;
* a standard journey;
* a long journey;
* a complaint;
* a purchase;
* a repeat purchase;
* a problematic customer journey.

## Interactive Product Graph

The `show_product_graph(product_name)` function displays a product along with related topics, customers, and interactions.

The size of each topic node depends on the number of associated customer interactions.

## Interactive Topic Interaction Graph

The `show_topic_graph(topic_name)` function displays a selected topic together with related customers, interactions, products, and scenarios.

Key performance indicators for the selected topic are displayed alongside the graph.

## Full Interactive Knowledge Graph

The `show_full_knowledge_graph(sample_size=200)` function builds the complete interactive Knowledge Graph.

If the graph is large, the visualization is limited to a sample of nodes.

Nodes displayed: **200 out of 1,809**

`WindowsPath('interactive_full_graph.html')`

## Interactive Analytics

Interactive Plotly visualizations are created, including distributions, trends over time, heatmaps, customer satisfaction, complaints, and repeat purchases.

## Data Export

At the end of the notebook, CSV files and the main HTML files containing interactive graphs are saved.

## Automated Quality Checks

An `assert` block verifies the dataset size, diversity of customer journeys, event connectivity, availability of dialogue messages, and the presence of the basic Knowledge Graph elements.

## Conclusion

This project implements a generator of synthetic customer lifecycles.

Customers follow different behavioral scenarios: some interact only once, some follow a standard journey consisting of 5–7 interactions, while others have long interaction sequences spanning several months.

The dataset also includes customers with complaints, repeat purchases, resolved issues, retention scenarios, and churn following negative experiences.

Synthetic Russian-language dialogues are generated for each customer interaction.

A Knowledge Graph is constructed to connect customers, interactions, products, topics, lifecycle stages, scenarios, and messages.

Interactive graphs make it possible to explore an individual customer's lifecycle, analyze products and their related topics, and examine customer interactions associated with a specific topic.

Analytical visualizations help evaluate complaints, purchases, repeat interactions, customer satisfaction, and monthly interaction trends.

This dataset can be used for testing **Knowledge Graphs, GraphRAG systems, and customer analytics solutions**.

# Генератор жизненного цикла клиента для синтетических диалогов и Knowledge Graph

## Генератор «жизненного цикла клиента» в синтетических диалогах

Скрипт, генерирующий для вымышленного клиента цепочку из 5–7 обращений за несколько месяцев (знакомство, жалоба, покупка продукта, повторное обращение), пригодную для тестирования графа знаний.

Ноутбук создает синтетический набор клиентов, обращений, диалогов и граф знаний. Все данные вымышленные, внешние API не используются.

## Цель работы

Цель работы — создать демонстрационный генератор жизненных циклов клиентов в синтетических банковских диалогах.

В итоговом наборе данных у клиентов разные сценарии поведения: короткие обращения, покупки, жалобы, повторные покупки, уход после негативного опыта и длинные цепочки взаимодействий на несколько месяцев.

Сгенерированные данные используются для построения **Knowledge Graph**, интерактивной визуализации клиентского пути и аналитики по продуктам, темам, обращениям и удовлетворенности.

## Установка и импорт библиотек

В ячейке проверяется наличие основных библиотек. Если какой-то пакет отсутствует, он устанавливается автоматически через `pip`.

## Справочники и настройки генерации

Задаются сегменты, каналы, продукты, темы, сценарии жизненного цикла и правила для генерации событий.

## Генерация синтетических клиентов

Создается `clients_df` на 50 вымышленных клиентов с сегментами, каналами, уровнем дохода, риском оттока и базовыми продуктами.

Количество клиентов: **50**

## Генерация разных жизненных циклов

В этой финальной версии у клиентов не один общий путь, а разные сценарии и разная длина цепочки обращений.

Распределение заранее задается так, чтобы гарантировать наличие коротких, обычных и длинных путей.

## Генерация обращений клиентов

Создается `events_df`.

Даты обращений идут по порядку, между событиями проходит от 7 до 45 дней, а `previous_event_id` связывает событие с предыдущим обращением клиента.

Всего обращений: **243**

## Генерация синтетических диалогов

Для каждого обращения генерируется 4–8 сообщений на русском языке.

Диалоги зависят от типа события, продукта, темы и настроения.

Всего сообщений: **1 444**

Сообщений на обращение: **от 4 до 8**

## Построение графа знаний

Граф строится через `networkx.DiGraph()`.

Он связывает клиентов, обращения, сообщения, продукты, темы, этапы жизненного цикла, сценарии, каналы, настроения, сегменты и города.

Узлов в графе: **1 809**

Ребер в графе: **3 295**

## Интерактивный граф жизненного пути одного клиента

Функция `show_client_lifecycle_graph(client_id)` показывает клиента, все его обращения, последовательность `EVENT_NEXT`, продукты, темы, этапы и первые сообщения по каждому событию.

## Фрагменты графов разных клиентов

Ниже автоматически выбираются примеры разных жизненных путей:

* один контакт;
* короткий путь;
* обычный путь;
* длинный путь;
* жалоба;
* покупка;
* повторная покупка;
* проблемный клиент.

## Интерактивный граф вокруг продукта

Функция `show_product_graph(product_name)` показывает продукт, связанные темы, клиентов и обращения.

Размер узла темы зависит от количества обращений.

## Интерактивный граф обращений по теме

Функция `show_topic_graph(topic_name)` показывает тему, клиентов, обращения, продукты и сценарии.

Рядом выводятся ключевые показатели по выбранной теме.

## Общий интерактивный Knowledge Graph

Функция `show_full_knowledge_graph(sample_size=200)` строит общий интерактивный граф.

Если граф большой, визуализация ограничивается выборкой узлов.

Показано узлов: **200 из 1 809**

`WindowsPath('interactive_full_graph.html')`

## Интерактивная аналитика

Построены интерактивные графики **Plotly**: распределения, динамика, heatmap, удовлетворенность, жалобы и повторные покупки.

## Экспорт данных

В конце сохраняются **CSV-файлы** и основные **HTML-файлы** с интерактивными графами.

## Автоматические проверки качества

Блок `assert` проверяет размер данных, разнообразие клиентских путей, связность событий, наличие сообщений и базовые элементы **Knowledge Graph**.

## Вывод

В работе создан генератор синтетических жизненных циклов клиентов.

У клиентов разные сценарии поведения: часть клиентов обращается один раз, часть проходит обычный путь из **5–7 обращений**, а часть имеет длинную цепочку взаимодействий на несколько месяцев.

Отдельно представлены клиенты с жалобами, повторными покупками, решением проблемы, удержанием и уходом после негативного опыта.

По каждому обращению сгенерированы синтетические русскоязычные диалоги.

Построен **граф знаний**, связывающий клиентов, обращения, продукты, темы, этапы жизненного цикла, сценарии и сообщения.

Интерактивные графы позволяют смотреть жизненный путь одного клиента, анализировать продукт и связанные с ним темы, а также изучать обращения клиентов по конкретной теме.

Аналитические графики помогают оценивать жалобы, покупки, повторные обращения, удовлетворенность и динамику обращений по месяцам.

Такой набор данных можно использовать для тестирования **Knowledge Graph, GraphRAG и клиентской аналитики**.


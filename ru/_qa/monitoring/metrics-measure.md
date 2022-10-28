# Метрики и единицы измерения

#### Что означает запятая? {#comma}

Запятая отделяет целую часть числа от дробной. Например, значение `123,456` следует трактовать как 123 целых 456 тысячных.

#### Почему cpu_usage более 100%? {#cpu-usage}

Вы используете виртуальную машину с [гарантированной долей](../../compute/concepts/performance-levels.md) ниже 100% vCPU. Например, гарантировано 20% производительности vCPU. Для системы мониторинга эта доля принимается за 100% ожидаемой нагрузки. Если на физическом ядре не окажется «соседей», вашей ВМ может быть выдано до 100% мощности vCPU, что в 5 раз больше гарантированной доли. На графике может отобразиться до 500%.

Если вы видите превышение верхней границы 100% на графиках длительное время, рекомендуем увеличить гарантированную долю vCPU. В любой момент на физическом ядре могут появиться «соседи», и реальное потребление vCPU может упасть до гарантированных 20% (около 400 МГц для платформы Intel Cascade Lake).

#### Где посмотреть описание метрик баз данных? {#metrics-description}

Описания метрик приведены в документации к сервисам, например:
* [{{ mpg-full-name }}](../../managed-postgresql/operations/monitoring.md).
* [{{ mmy-full-name }}](../../managed-mysql/operations/monitoring.md).
* [{{ mrd-full-name }}](../../managed-redis/operations/monitoring.md).

Важные метрики выведены на сервисные дашборды каждого сервиса. Полных список метрик для каждого сервиса доступен в разделе **Обзор метрик**. Выгрузить полный список метрик можно по [инструкции](../../monitoring/operations/metric/list.md).

#### Как настроить единицы измерения на графике? {#graph-units}

Единицы измерения настраиваются во вкладке **Оси** при редактировании графика. Можно выбрать тип единицы измерения, задать формат чисел, масштаб (линейный или логарифмический), максимальное и минимальное значения.

#### Как отображаются максимумы/пики на графиках? {#graph-peaks}

{{ monitoring-name }} получает метрики за определенный период времени группами и при создании точки усредняет значения. При уменьшении масштаба временного отрезка количество значений в выборке увеличивается, и пиковые значения на графике могут расти.

Это работает и в обратную сторону — при выборе большего интервала времени точечные пиковые значения сглаживаются и могут не быть видны на графике.

#### Почему график пропал или выглядит обрезанным? {#graph-lost}

Данные могли попасть за пределы установленных границ графика. Проверьте настройки масштаба, а также максимального и минимального значений на вкладке **Оси**.

#### Есть ли описание функций в языке запросов? {#function-description}

Описание функций приведено в [Справочнике](../../monitoring/concepts/querying.md#functions).

Вы можете протестировать функции в разделе **Обзор метрик**.
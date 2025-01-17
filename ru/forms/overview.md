# Обзор сервиса

{{ forms-full-name }} — это сервис, где вы можете проводить опросы, тесты и квизы, собирать отзывы и принимать заявки.

В {{ forms-full-name }} доступны разные типы вопросов, из которых легко составить любой опрос или тест. Форму можно разместить на сайте или поделиться с пользователями по ссылке. Ответы на вопросы можно посмотреть в интерфейсе {{ forms-name }} или получить на почту.

Используйте {{ forms-full-name }} в личных делах, например проведите опрос для друзей и составьте меню для новогодней вечеринки. Либо используйте формы для работы и бизнеса, например принимайте заказы для интернет-магазина.

Если вы хотите использовать {{ forms-name }} вместе с коллегами, создайте организацию в {{ yandex-cloud }} и подключите {{ forms-full-name }} для бизнеса. Вы сможете дать другим пользователям организации доступ к редактированию ваших форм и просмотру ответов, а также настроить интеграцию с сервисами {{ tracker-full-name }} и {{ wiki-full-name }}. Подробнее читайте в разделе [{#T}](forms-for-org.md).

## Как работает {{ forms-full-name }} {#how-to}

### Создание и настройка формы {#create}

С помощью конструктора на форму можно добавлять вопросы и настраивать их свойства. В {{ forms-full-name }} существуют разные типы вопросов, которые предполагают определенные ответы: выбор одного или нескольких вариантов из списка, текст, число, дата, адрес электронной почты и так далее. Вы можете написать текст вопроса, добавить варианты ответов (если они предусмотрены) и настроить другие параметры. 

Читайте подробнее:

- [{#T}](quick-guide.md)

- [{#T}](blocks-ref/blocks-reference.md)

### Логика вопросов и ответов {#restrictions}

В {{ forms-full-name }} можно настроить условия отображения вопросов и ограничения для ответов:

- [Сделать вопросы обязательными](add-questions.md#params) — без ответа на такие вопросы пользователь не сможет отправить форму.

- [Отображать или скрывать вопросы в зависимости от того, как пользователи отвечают на предыдущие вопросы](add-questions.md#conditions). Например, отображать поле для адреса электронной почты, если пользователь согласился подписаться на рассылку.

- [Ограничить возможность ответов на форму по времени или по количеству](restrictions.md).

### Публикация формы {#publish}

Форму можно [опубликовать несколькими способами](publish.md):

- По ссылке — ссылку на форму можно отправить в мессенджере или разместить в социальных сетях.

- Встроить на сайт с помощью HTML-кода. Например, добавить на сайт компании форму для обратной связи.

- Пользователи [организаций {{ yandex-cloud }}](forms-for-org.md) могут вставлять формы на страницы в сервисе {{ wiki-full-name }}.

### Получение ответов {#answers}

Ответы пользователей можно [получить несколькими способами](answers.md):

- Просмотреть в интерфейсе {{ forms-name }}.

- Скачать файл с ответами.

- Загрузить файл с ответами на Яндекс&#160;Диск.

- Настроить отправку ответов на почту.

## Подробнее о возможностях {{ forms-full-name }} {#details}

- [Как создать форму](new-form.md)

- [Как провести тест](tests.md)

- [Как настроить внешний вид формы](appearance.md)

- [Как настроить страницу, которую увидит пользователь после заполнения формы](success-page.md)

- [Как опубликовать форму](publish.md)

- [Как настроить интеграцию с почтой и другими сервисами](notifications.md)

- [Как настроить предзаполнение — автоматически подставлять в форму ответы](pre-fill.md)

- [Как посмотреть ответы](answers.md)
{% list tabs %}

* Консоль управления

    1. Перейдите на [страницу каталога]({{ link-console-main }}) и выберите сервис **{{ mms-name }}**.
    1. Нажмите на имя нужного кластера и выберите вкладку **Базы данных**.
    1. Нажмите кнопку ![image](../../../_assets/plus-sign.svg) **Импортировать**.
    1. Укажите параметры импорта:

        * **Имя новой базы данных** — имя базы данных, которая будет восстановлена в кластере из резервной копии. На момент восстановления в кластере не должно быть базы данных с таким именем.
        * **Имя бакета** — имя бакета в {{ objstorage-name }}, в котором хранится резервная копия базы данных.
        * **Директория в бакете** — путь к папке, в которой хранятся файлы резервной копии. Путь должен быть полным и начинаться с `/`.
        * **Список файлов бэкапа** — имя файла резервной копии в директории. Нажмите кнопку **Добавить** и укажите все имена файлов резервной копии, если их несколько. Все указанные файлы должны существовать.

    1. Нажмите кнопку **Импортировать**.

* CLI

    {% include [cli-install](../../cli-install.md) %}

    {% include [default-catalogue](../../default-catalogue.md) %}

    Выполните команду:

    ```bash
    {{ yc-mdb-ms }} database backup-import \
       --cluster-name=<имя кластера> \
       --bucket=<имя бакета> \
       --path=<полный путь к папке в бакете> \
       --files=<файл1>.bak,<файл2>.bak,... \
       <имя базы данных>
    ```

    Где:

    * `--cluster-name` — имя кластера {{ mms-name }}, в который импортируется база данных.
    * `--bucket` — имя бакета в {{ objstorage-name }}, в котором хранится резервная копия базы данных.
    * `--path` — путь к папке, в которой хранятся файлы резервной копии. Путь должен быть полным и начинаться с `/`.
    * `--files` — список файлов резервной копии в папке `--path`. Все указанные файлы должны существовать.
    * `<имя базы данных>` — имя базы данных, которая будет восстановлена в кластере из резервной копии. На момент восстановления в кластере не должно быть базы данных с таким именем.

        {% include [database-name-limits](../../mdb/mms/note-info-db-name-limits.md) %}

* API

    Воспользуйтесь методом API [importBackup](../../../managed-sqlserver/api-ref/Database/importBackup.md) и передайте в запросе:

    * Идентификатор кластера в параметре `clusterId`. Чтобы узнать идентификатор, [получите список кластеров в каталоге](../../../managed-sqlserver/operations/cluster-list.md#list-clusters).
    * Имя восстанавливаемой базы данных в параметре `databaseName`. На момент восстановления в кластере не должно быть базы данных с таким именем.

        {% include [database-name-limits](../../mdb/mms/note-info-db-name-limits.md) %}

    * Имя бакета в {{ objstorage-name }}, в котором хранится резервная копия базы данных, в параметре `s3Bucket`.
    * Путь к папке, в которой хранятся файлы резервной копии, в параметре `s3Path`. Путь должен быть полным и начинаться с `/`.
    * Список имен файлов резервной копии в массиве `files[]`.

{% endlist %}
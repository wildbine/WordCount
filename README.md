# WordCount на Java с использованием Hadoop

1. **Создание папки в HDFS**

    Выполните следующую команду, чтобы создать папку `1` в Hadoop Distributed File System (HDFS):

    ```bash
    hadoop fs -mkdir /1
    ```

2. **Загрузка данных в HDFS**

    Загрузите файл data.txt в созданную папку 1 в HDFS с помощью следующей команды:

    ```bash
    hadoop fs -put data.txt /1
    ```
3. **Сборка проекта с помощью Maven**

    Перед запуском WordCount убедитесь, что ваш проект скомпилирован и упакован в JAR-файл с помощью Maven. Выполните следующую команду в корневой директории вашего проекта:

    ```bash
    mvn clean install
    ```

    Это создаст JAR-файл WordCount-1.0-SNAPSHOT.jar в папке target.

4. **Запуск WordCount на кластере Hadoop**

    Теперь запустите приложение WordCount на кластере Hadoop, используя команду hadoop jar. Укажите полное имя класса WC_Runner, путь к вашему файлу данных и путь для сохранения результата:

    ```bash
    hadoop jar target/WordCount-1.0-SNAPSHOT.jar org.bine.WC_Runner /1/data.txt /output
    ```

    ## Замечание
    
    Не забывайте, что у Вас должен быть установлен и правильно настроен hadoop, а также правильно указаны пути к файлам.
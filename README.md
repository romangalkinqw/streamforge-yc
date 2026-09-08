# StreamForge YC

Учебный проект по потоковой обработке заказов интернет-магазина
в Yandex Cloud.

## Поток данных

Python → Kafka → Spark Structured Streaming → Object Storage → ClickHouse

## Задачи компонентов

- Python генерирует события заказов.
- Kafka сохраняет поток событий, из которого их читает обработчик.
- Spark проверяет и преобразует события.
- Object Storage хранит обработанные данные в файлах Parquet.
- ClickHouse загружает эти файлы и позволяет анализировать заказы через SQL.
- Airflow по расписанию запускает загрузку новых файлов из Object Storage
  в ClickHouse и проверки качества данных.

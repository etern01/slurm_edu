# Роль Ansible - FluentBit

Эта роль Ansible устанавливает и настраивает FluentBit, систему для сбора, обработки и пересылки журналов.

## Требования

- Операционная система: Ubuntu 22.04

## Параметры

В этой роли определены следующие параметры:

- `fluentbit_service_flush_seconds`: Интервал сброса буфера в секундах.
- `fluentbit_service_daemon`: Запускать FluentBit в режиме демона (true/false).
- `fluentbit_service_custom_parsers_file`: Путь к пользовательскому файлу парсеров.
- `fluentbit_service_log_level`: Уровень журналирования FluentBit.
- `fluentbit_service_enable_metrics`: Включить сбор метрик FluentBit (true/false).
- `fluentbit_service_metrics_listen_ip`: IP-адрес для прослушивания метрик FluentBit.
- `fluentbit_service_metrics_listen_port`: Порт для прослушивания метрик FluentBit.
- `fluentbit_apt_repo`: Репозиторий APT для установки FluentBit.

- `fluentbit_inputs`: Конфигурация входных источников FluentBit.
- `fluentbit_outputs`: Конфигурация выходных источников FluentBit.
- `fluentbit_additional_conf_files`: Дополнительные файлы конфигурации FluentBit.

- `es_user`: Имя пользователя Elasticsearch.
- `es_pass`: Пароль пользователя Elasticsearch.
- `es_host`: Хост Elasticsearch.

## Пример использования

```yaml
- name: Пример установки и настройки FluentBit
  hosts: fluentbit_servers
  roles:
    - fluentbit
  vars:
    fluentbit_service_flush_seconds: 5
    fluentbit_service_daemon: false
    fluentbit_service_custom_parsers_file: []
    fluentbit_service_log_level: info
    fluentbit_service_enable_metrics: false
    fluentbit_service_metrics_listen_ip: 0.0.0.0
    fluentbit_service_metrics_listen_port: 2020
    fluentbit_apt_repo: 'deb https://packages.fluentbit.io/debian/bullseye bullseye main'

    fluentbit_inputs: []

    fluentbit_outputs: []

    fluentbit_additional_conf_files: []

    es_user: elastic
    es_pass: RhkL8XO+zm9aorHlnbAi
    es_host: "127.0.0.1"

# Роль Ansible - ElasticSearch_Kibana

Эта роль Ansible устанавливает и настраивает ElasticSearch и Kibana, комбинированный стек для хранения и визуализации данных.

## Требования

- Операционная система: Linux

## Параметры

В этой роли определены следующие параметры:

- `elastic_config_file`: Путь к конфигурационному файлу ElasticSearch.
- `kibana_config_file`: Путь к конфигурационному файлу Kibana.
- `kibana_home`: Директория установки Kibana.
- `master_nodes_name`: Имя главных узлов ElasticSearch.
- `kibana_server_host`: IP-адрес для прослушивания сервера Kibana.
- `es_api_host`: Хост API ElasticSearch.
- `es_api_port`: Порт API ElasticSearch.
- `es_api_basic_auth_username`: Имя пользователя базовой аутентификации ElasticSearch API.
- `es_api_basic_auth_password`: Пароль пользователя базовой аутентификации ElasticSearch API.
- `es_user`: Имя пользователя Elasticsearch.
- `es_pass`: Пароль пользователя Elasticsearch.

## Пример использования

```yaml
- name: Пример установки и настройки ElasticSearch и Kibana
  hosts: elasticsearch_kibana_servers
  roles:
    - elasticsearch_kibana
  vars:
    elastic_config_file: /etc/elasticsearch/
    kibana_config_file: /etc/kibana/
    kibana_home: /usr/share/kibana
    master_nodes_name: Copy-of-VM-ubuntu2204-template
    kibana_server_host: 0.0.0.0
    es_api_host: 127.0.0.1
    es_api_port: 9200
    es_api_basic_auth_username: elastic
    es_api_basic_auth_password: RhkL8XO+zm9aorHlnbAi
    es_user: elastic
    es_pass: RhkL8XO+zm9aorHlnbAi

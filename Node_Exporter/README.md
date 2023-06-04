# Роль Ansible - Node_Exporter

Эта роль Ansible устанавливает и настраивает Node_Exporter, инструмент для сбора и экспорта метрик с узлов системы.

## Требования

- Операционная система: Linux

## Параметры

В этой роли определены следующие параметры:

- `node_exporter_version`: Версия Node_Exporter.
- `node_exporter_install_dir`: Директория установки Node_Exporter.
- `node_exporter_binary_url`: URL для загрузки бинарного файла Node_Exporter.
- `node_exporter_checksums_url`: URL для загрузки файла контрольных сумм Node_Exporter.
- `node_exporter_skip_install`: Флаг, указывающий пропустить установку Node_Exporter (по умолчанию `false`).
- `node_exporter_web_listen_address`: IP-адрес и порт для прослушивания веб-сервера Node_Exporter.
- `node_exporter_web_telemetry_path`: Путь для доступа к метрикам Node_Exporter.
- `node_exporter_textfile_dir`: Директория для текстовых файлов экспорта метрик Node_Exporter.
- `node_exporter_tls_server_config`: Конфигурация TLS-сервера Node_Exporter.
- `node_exporter_http_server_config`: Конфигурация HTTP-сервера Node_Exporter.
- `node_exporter_basic_auth_users`: Пользователи для базовой аутентификации Node_Exporter.
- `node_exporter_enabled_collectors`: Включенные коллекторы метрик Node_Exporter.
- `node_exporter_disabled_collectors`: Отключенные коллекторы метрик Node_Exporter.
- `node_exporter_binary_install_dir`: Директория установки бинарного файла Node_Exporter.
- `node_exporter_system_group`: Группа системного пользователя Node_Exporter.
- `node_exporter_system_user`: Имя системного пользователя Node_Exporter.
- `prometheus_hosts`: Хосты, на которых установлен Prometheus.
- `prometheus_config_dir`: Директория конфигурации Prometheus.
- `prometheus_targets`: Цели сбора метрик Prometheus.

## Пример использования

```yaml
- name: Пример установки и настройки Node_Exporter
  hosts: node_exporter_servers
  roles:
    - node_exporter
  vars:
    node_exporter_version: 1.1.2
    node_exporter_install_dir: /usr/local/bin
    node_exporter_binary_url: "https://github.com/prometheus/node_exporter/releases/download/v{{ node_exporter_version }}/node_exporter-{{ node_exporter_version }}.linux-amd64.tar.gz"
    node_exporter_checksums_url: "https://github.com/prometheus/node_exporter/releases/download/v{{ node_exporter_version }}/sha256sums.txt"
    node_exporter_web_listen_address: "0.0.0.0

# Роль Ansible - Prometheus

Эта роль Ansible устанавливает и настраивает Prometheus, систему мониторинга и сбора метрик.

## Требования

- Операционная система: ubuntu 22.04
- Версия Ansible 2.10 или выше

## Параметры

В этой роли определены следующие параметры:

- `prometheus_version` (обязательный): Версия Prometheus для установки.
- `prometheus_config_dir` (обязательный): Путь к каталогу конфигурации Prometheus.
- `prometheus_db_dir` (обязательный): Путь к каталогу базы данных Prometheus.
- `prometheus_install_dir` (обязательный): Путь для установки исполняемых файлов Prometheus.
- `prometheus_binary_url` (обязательный): URL для загрузки бинарного архива Prometheus.
- `prometheus_web_listen_address` (обязательный): IP-адрес и порт, на котором Prometheus будет прослушивать веб-интерфейс.
- `prometheus_web_external_url`: Внешний URL-адрес для доступа к веб-интерфейсу Prometheus.
- `prometheus_metrics_path`: Путь для доступа к метрикам Prometheus.
- `prometheus_config_file`: Имя файла конфигурации Prometheus.
- `prometheus_global`: Глобальные настройки Prometheus, такие как интервал сбора метрик и интервал оценки правил.
- `prometheus_web_config`: Настройки веб-интерфейса Prometheus, такие как TLS-конфигурация и аутентификация.
- `prometheus_storage_retention`: Время хранения данных в хранилище Prometheus.
- `prometheus_storage_retention_size`: Размер хранилища Prometheus.
- `prometheus_targets`: Цели для мониторинга Prometheus, такие как узлы, которые должны быть собраны метрики.
- `prometheus_scrape_configs`: Конфигурация сбора метрик Prometheus, включая задания и статические конфигурации.

## Пример использования

```yaml
- name: Пример установки и настройки Prometheus
  hosts: prometheus_servers
  roles:
    - prometheus
  vars:
    prometheus_version: 2.27.0
    prometheus_config_dir: /etc/prometheus
    prometheus_db_dir: /var/lib/prometheus
    prometheus_install_dir: /usr/local/bin
    prometheus_binary_url: "https://github.com/prometheus/prometheus/releases/download/v{{ prometheus_version }}/prometheus-{{ prometheus_version }}.linux-amd64.tar.gz"
    prometheus_web_listen_address: "0.0.0.0:9090"
    prometheus_storage_retention: "30d"
    prometheus_storage_retention_size: "30MB

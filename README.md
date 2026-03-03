# K8s Monitoring Stack

## 📌 Описание проекта

В рамках проекта был развернут полноценный стек мониторинга для Kubernetes-кластера.

Стек включает:

- Prometheus — сбор метрик
- Alertmanager — обработка и отправка алертов
- Grafana — визуализация метрик
- Loki — централизованный сбор логов
- Promtail — агент отправки логов

Мониторинг развернут через docker-compose.

---

## 🏗 Архитектура

```text
Kubernetes Cluster
        |
        v
+------------------+
|    Prometheus    |
+------------------+
        |
        v
+------------------+
|   Alertmanager   |
+------------------+
        |
        v
   Telegram Alerts

Logs Flow:
Pods -> Promtail -> Loki -> Grafana

Metrics Flow:
K8s -> Prometheus -> Grafana

1) Собирать логи будем с помощью loghouse:
https://github.com/flant/loghouse
Добавляем репозиторий:
```
helm repo add loghouse https://flant.github.io/loghouse/charts/  
```
Устанавливаем loghouse:
```
helm install --namespace loghouse --create-namespace -f --set global.dnsService=coredns --set spec.type=LoadBalancer monitor/loghouse/loghouse-values.yml loghouse loghouse/loghouse
```
Заходим по адресу: {{ ip_cluster }}:8080 создаём дашборд и смотрим логи:


2)Для мониторинга кластера и приложения будем использовать Prometheus stack: https://artifacthub.io/packages/helm/prometheus-community/prometheus?modal=install
В каталоге prometheus_stack рядом с файлом docker-compose.yml запускаем:
```
docker compose up -d 
```
Потом смотрим контейнеры:

Из готовых дашбордов ставим нужные нам: https://grafana.com/grafana/dashboards/


3)В файле docker-compose.yml подставляем данные для подключения к нашему telegram боту.
Получаем уведомление:

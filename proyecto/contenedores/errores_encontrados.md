 ================ ERRORES ENCONTRADOS EN DOCKER-COMPOSE ====================

1_ El primer Error que se pudo visualizar, fue el nombre de volumes de grafana, el cual en la configuracion del servicio, se 
indicaba como grafana-data. Mientras que en la declaracion de dicho nombre, se inducia como grafana-storage. Por ende, al
ejecutar docker-compose up, buscaba una direccion que no se encontraba.
*Se corrigio reemplazando el nombre de grafana-storage, por el de grafana-data.*

2_El segundo error fue durante la configuracion del servicio de Redis, dado que en la parte de redes, se menciona
la red como monitoring-network, mientras que, analizando el resto de los servicios, dicha red tenia el nombre de monitoring.
*Se reemplazo el nombre de monitoring-network por el de monitoring para que coincida el nombre de la red con el nombre general*

3_ El tercer y ultimo error se encontraba en el archivo de prometheus.yml, dado que aparecia el data source de ngix, pero en
prometheus dicho target, figura como "DOWN", esto se debe a que ngix por defecto, no expone metricas, por ende, se debe
eliminar dicho job. O si se requiere dicho monitoreo, se debe utilizar NGINX Prometheus Exporter, para que sean
compatibles entre si (nginx-prometheus).


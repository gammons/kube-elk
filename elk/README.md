# ELK stack setup

1. Create `analytics` namespace: `kc apply -f namespace.yml`
2. Install ES `helm install elasticsearch elastic/elasticsearch -f ./es-values.yml -n analytics`
3. Install kibana `helm install kibana elastic/kibana -n analytics`
4. install filebeat `helm install filebeat elastic/filebeat -n analytics`
5. Install apm server: `helm install apm-server stable/apm-server -f ./apm-values.yml -n analytics`
6. Ensure you created the metalLLB service - go to metallb dir and run `kc apply -f kibana-service.yml`


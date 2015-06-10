# Consul-template haproxy image

Based on https://registry.hub.docker.com/u/cargonauts/consul-haproxy/

consul-template 0.10.0

## How to use
```
docker run --name haproxy --dns 172.17.42.1 --dns 8.8.8.8 --dns-search service.consul -e SERVICE_IGNORE=true -v /haproxy.ctmpl:/haproxy.ctmpl leandrocp/consul-haproxy -consul $HOST_IP:8500 -template /haproxy.ctmpl:/haproxy.cfg
```

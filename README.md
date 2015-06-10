# Consul-template haproxy image

Based on [cargonauts/consul-haproxy](https://registry.hub.docker.com/u/cargonauts/consul-haproxy/)

Updated to consul-template [0.10.0](https://github.com/hashicorp/consul-template/releases/tag/v0.10.0)

## How to use

* Create your HAProxy template file at /haproxy.ctmpl

* Execute:
```
docker run --name haproxy \
--dns 172.17.42.1 \
--dns 8.8.8.8 \
--dns-search service.consul \
-e SERVICE_IGNORE=true \
-v /haproxy.ctmpl:/haproxy.ctmpl \
leandrocp/consul-haproxy \
-consul $CONSUL_IP:8500 \
-template /haproxy.ctmpl:/etc/haproxy/haproxy.cfg:service haproxy reload || true
```

## Reference
* https://github.com/hashicorp/consul-template
* http://golang.org/pkg/text/template/

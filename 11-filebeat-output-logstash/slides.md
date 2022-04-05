%title: ELK
%author: xavki


# Filebeat : Output Logstash

<br>


* loadbalancing

```
output.logstash:
  hosts: ["192.168.20.102:5044", "192.168.20.106:5044"]
  loadbalance: true
```

<br>


* compression_level

* worker: number of workers per host

* escape_html: escape html

* pipelining: number of batch launched without waiting for the ACK

* index: index name

* timeout

* max_retries

*ssl

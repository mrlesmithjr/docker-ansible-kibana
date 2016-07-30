Repository Information
======================
Builds a [Docker] container running [Kibana] ready for use. Provisioning provided via [Ansible].

How-To
------
Build
```
docker build -t ansible-kibana .
```

Consume
* Requires a running [Elasticsearch] instance
  * `docker run --name elasticsearch -d mrlesmithjr/elasticsearch`

`Default`
```
docker run -d -p 5601:5601 --link elasticsearch:elasticsearch mrlesmithjr/kibana
```
`Define an external elasticsearch url`
```
docker run -d -p 5601:5601 -e ELASTICSEARCH_URL=http://some-elasticsearch:9200 mrlesmithjr/kibana
```

Consume using docker-compose (Spins up [Elasticsearch] with persistent volume/data and a working [Kibana] link)
```
docker-compose up -d
```

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- [@mrlesmithjr]
- [everythingshouldbevirtual.com]
- [mrlesmithjr@gmail.com]


[Kibana]: <https://elastic.co/kibana>
[Elasticsearch]: <https://elastic.co>
[Docker]: <https://www.docker.com>
[Ansible]: <https://www.ansible.com/>
[@mrlesmithjr]: <https://twitter.com/mrlesmithjr>
[everythingshouldbevirtual.com]: <http://everythingshouldbevirtual.com>
[mrlesmithjr@gmail.com]: <mailto:mrlesmithjr@gmail.com>

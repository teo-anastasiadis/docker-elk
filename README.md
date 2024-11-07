# Netlink ELK Stack

Basic configuration of Elasticsearch + Kibana + Logstash + Curator. Mostly copies from [original repo](https://github.com/deviantony/docker-elk). Original instructions retained [here](./INSTRUCTIONS.md)

## Usage

First time spin up

`docker compose up setup`

This will create basic credentials from .env.
To change credentials follow [instructions](./INSTRUCTIONS.md).

After that

`docker compose up -d`

Shut down

`docker compose down`

## Features included

### 1. Kibana

UI available at [localhost:5601](http://localhost:5601/)

### 2. Logstash

Send logs in JSONL format at 

`localhost:50001/<random-tag>` (http) or 

`localhost:50000` (tcp). 

See config [here](./logstash/pipeline/logstash.conf)

### 3. Curator

Logs are deleted after **6 months**. 
See config [here](./curator/config/delete_log_files_curator.yml)

## License

Run elastic using basic license. See config [here](./elasticsearch/config/elasticsearch.yml). Read more about [here](https://www.elastic.co/licensing/elastic-license).

## Filebeat and other extensions

Original base configuration for extra extensions kept under /extensions.

See original instruction inside each folder.
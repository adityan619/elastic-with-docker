# Elastic on Docker

This is a small example of how to use [Elastic](https://github.com/olivere/elastic),
the Elasticsearch client for Go, with [Docker](https://docs.docker.com/) and
[Docker Compose](https://docs.docker.com/compose/).

Docker Compose orchestrates two containers.

First, there is the
[Elasticsearch container](https://hub.docker.com/_/elasticsearch/). We use
the default configuration, but we mount the data directory on `/tmp/esdata`.
[See here](https://github.com/docker-library/elasticsearch/issues/74)
why we do this.

Second, we host a simple app in a container that will connecto to the
Elasticsearch container and will periodically call the Nodes Info API.

To start everything up, run `docker-compose up`, then watch `docker-compose logs`
in another shell.

## FAQ

In case you are wondering why we are mounting Elasticsearch data on `/tmp/esdata`,
refer to [this issue](https://github.com/docker-library/elasticsearch/issues/74).

## LICENSE

MIT
# Docker image for exposing in Rancher healthchecks the ElasticSearch cluster health 

Docker image to use in rancher healthchecks to expose a port if  ElasticSearch cluster health is GREEN and not expose it if it's not.

## Variables

* ES_URL - ElasticSearch URL, mandatory
* ES_USER - ElasticSearch read only user, if needed
* ES_PASSWORD - ElasticSearch password, if  needed
* PORT - Port that will be UP when cluster is healthy and DOWN when it's not, default 12345
* CHECK_PERIOD - How often the check is done, seconds , default 10
* YELLOW_WAIT - seconds to wait before stopping the port when cluster is YELLOW, default 60
* CLIENT_WAIT - seconds to wait before stopping the port when  ES url is not responding, default 60


## Usage

To test:

    docker run -it --rm -e ES_URL=http://es-client:9200 -e ES_USER=ro -e ES_PASSWORD=ropass  --name health eeacms/esclusterhealth

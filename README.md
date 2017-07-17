# Kibana 5.3 exportable

docker-compose with export patch

Ref: https://github.com/elastic/kibana/issues/1992#issuecomment-313947405

## How to Use
0. (Prerequirement) Docker + Docker-Compose Installation
1. Clone this repository
2. Adjust paramaters on `kibana_5.3/config/etc/kibana.yml`
3. Adjust bind port on `docker-compose.yml`
4. Run `docker-compose build`
5. Run `docker-compose up -d`
6. Access to `http://<server>:<port>`

In Discover tab, you'll see **Export** icons.

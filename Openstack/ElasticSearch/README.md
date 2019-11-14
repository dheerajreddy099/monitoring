
# ElasticSearch Configuration
Compose file to run the Elastic container

* In Openstack, if external volume is mounted (in Openstack navigate to compute -> volumes, and verify if they are attached)
* Mount the attached volume

`$ sudo mkdir /mnt/volume`

`$ sudo mkfs.ext4 /dev/disk/by-id/virtio-b0672cee-e4cd-4e9e-9`

`$ sudo mount /dev/disk/by-id/virtio-b0672cee-e4cd-4e9e-9 /mnt/volume`


Add the following to .bash_profile

`export DOCKER_COMPOSE_MOUNT=/mnt/volume/var`

* Change the working directory to elasticsearch

`cd elasticsearch`

* Assuming docker-compose was installed

`docker-compose up -d`

* To install Head plugin for Elastic Search

`docker-compose ps`

`docker exec -it <name of container> bash`

`/usr/share/elasticsearch/bin/plugin install mobz/elasticsearch-head`

* Elastic search GUI can be accessed at `http://<Ip_address>:9200/_plugin/head/`

* To destroy the containers

`docker-compose down`

8. For data to be sent to elasticsearch, install logstash on the machine from which data needs to be sent to the elasticsearch. Place the logstash configration at /etc/logstash/conf.d/
Examples could be found on
https://www.elastic.co/guide/en/logstash/current/config-examples.html

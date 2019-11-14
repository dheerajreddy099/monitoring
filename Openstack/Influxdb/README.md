# Influxdb Configuration
Compose file to run the Influxdb container

* In Openstack, if external volume is mounted (in Openstack navigate to compute -> volumes, and verify if volume is attached)

* Mount the attached volume

`$ sudo mkdir /mnt/volume`

`$ sudo mkfs.ext4 /dev/disk/by-id/virtio-b0672cee-e4cd-4e9e-9`

`$ sudo mount /dev/disk/by-id/virtio-b0672cee-e4cd-4e9e-9 /mnt/volume`


Add the following to .bash_profile

`export DOCKER_COMPOSE_MOUNT=/mnt/volume/`


* Change Working directory to Influxdb

`cd Influxdb`

* Assuming docker-compose was installed

`docker-compose up -d`

* Influxdb, in browser(container running on mac)  http://localhost:8083

* Destroy the running containers

`docker-compose down`

* Install "collectd" on the machine from which the metrics needs to be sent to Influxdb
Example for Collectd.conf file
https://github.com/Shopify/collectd/blob/master/debian/collectd.conf

enable the plugin for influxdb and point to the appropraite influxdb Ip. Enable the loadPlugins with the metrics that needs to be pushed to influxdb.

# Grafana Configuration
Compose file to run the Grafana container

* In Openstack, if external volume is mounted (in Openstack navigate to compute -> volumes, and verify if volume is attached)

* Mount the attached volume

`$ sudo mkdir /mnt/volume`

`$ sudo mkfs.ext4 /dev/disk/by-id/virtio-b0672cee-e4cd-4e9e-9`

`$ sudo mount /dev/disk/by-id/virtio-b0672cee-e4cd-4e9e-9 /mnt/volume`

Add the following to .bash_profile

`export DOCKER_COMPOSE_MOUNT=/mnt/volume`


* Change the working directory to Grafana

`cd Grafana`

Assuming docker-compose was installed

`docker-compose up -d`

* Grafana UI, in a browser(container running on mac) http://<instance ip>:3000


* The data sources needs to be configured at Grafana in Datasources.

* Destroy the running containers

`docker-compose down`

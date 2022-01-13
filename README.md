
# Software reliability in the Big Data era with an industry‐minded focus

This code has been updated to use latest versions of all the components on may 2021.

## Usage via WSL 2

1. Install WSL 2 and install an Ubuntu 20.04 image.
2. Install docker desktop and enable the WSL 2 backend (docker & docker-compose commands must be installed).
3. ```git clone```
4. ```docker-compose up -d```
5. Open Zeppelin at http://your-docker-machine-ip:8080 
6. Enjoy!


## Usage via Ubuntu (virtual machine)
If you use a linux computer or a virtual machine just install follow these steps (use Ubuntu 20.04 preferably):
 
1. Install the latest [Docker](https://docs.docker.com/engine/install/ubuntu/) and [docker-compose](https://docs.docker.com/compose/install/) versions on your computer.
2. Install the latest version of Git. Check the [guide](https://www.atlassian.com/git/tutorials/install-git#linux) to install it.
3. ```git clone```
4. ```cd ada_2021```
5. ```docker-compose up -d```
6. Open Zeppelin at http://your-docker-machine-ip:8080 
7. Enjoy!

## Architecture

<a>
  <img src="https://github.com/Neuw84/bds2k17/blob/master/architecture.png" width="100%" height="400">
</a>

## Details

* Spark UI can be accesed at http://your-docker-machine-ip:4040
* Nifi UI can be accesed at http://your-docker-machine-ip:8090
* A Java MQTT producer is at "producer" folder: ```java -jar mqtt-producer.jar tcp://your-docker-machine-ip:1883 150```
* Nifi XML template: ```mqtt-json-kafka.xml```


*Note*: you can use the folowing command to check the IP addresses of each Docker container (use double quotes if your are on Windows): ```docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' container_name_or_id```
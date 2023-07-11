# JB-monitoring-test

Repo contains code for monitoring services deploy - JB test task. Services for monitoring:

        - http://wp-0.iurii.test.monitoring.intellij.net/
        - http://wp-1.iurii.test.monitoring.intellij.net/
        - http://wp-2.iurii.test.monitoring.intellij.net/
        - http://wp-3.iurii.test.monitoring.intellij.net/
        - http://wp-4.iurii.test.monitoring.intellij.net/
        - http://wp-5.iurii.test.monitoring.intellij.net/
        - http://wp-6.iurii.test.monitoring.intellij.net/
        - http://wp-7.iurii.test.monitoring.intellij.net/
        - http://wp-8.iurii.test.monitoring.intellij.net/
        - http://wp-9.iurii.test.monitoring.intellij.net/

## How to deploy

Deploy must be performed by using Docker Compose
1. Install [Docker Engine and Docker Compose](https://docs.docker.com/engine/install/ubuntu/)
```
 sudo apt-get update
 sudo apt-get install ca-certificates curl gnupg lsb-release
 curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
 echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
 sudo apt-get update
 sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
2. Copy the repository
3. Move to the repository folder
4. Run the docker compose

```
docker compose up --build -d
```
5. Check the containers' status ("Status" == up)
```
docker ps -a
```

## How to access services

1. Prometeus  - running on the 9090 port on the host
2. Grafana - running on the 9110 port on the host
3. Node Exporter - running on the 9100 port on the host
4. BlackBox Exporter - running on the 9115 port on the host

Grafana available with default credentials (first run) - admin/admin

## How to stop and remove running containers
```
docker compose stop
docker compose rm -f
```  

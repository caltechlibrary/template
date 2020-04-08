
# Elasticsearch v7.x

You can go to Elasticsearch's website and download the appropriate
elastic search.

    https://www.elastic.co/start

Elasticsearch needs to be running locally to use Observatory. Observatory
expects to connect to Elasticsearch on port 9200 of localhost.

## Example Debian style system setup

Managing and installing Elasticsearch on a Debian style Linux or
on macOS varies slightly. These instructions describe installing
Elasticsearch community edition on a Debian/Ubuntu based Linux.

### Installing Elasticsearch v7.5

+ Elasticsearch
    + https://www.elastic.co/guide/en/elasticsearch/reference/7.5/deb.html

Steps I took to install Elasticsearch v7.5 under Ubuntu 18.04 LTS

```shell
    sudo apt install apt-transport-https # Already had the newest 
    sudo apt install openjdk-11-jdk
    # Import Elastic Search GPG Key
    wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch |\
        sudo apt-key add -
    echo "deb https://artifacts.elastic.co/packages/oss-7.x/apt stable main" |\
        sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list
    sudo apt update
    sudo apt install elasticsearch-oss
```

Setup up for systemd for auto start on boot. NOTE: If you want manual
restart just do daemon-reload, then use the usual systemd start
and stop verbs with elasticsearch.service.

```shell
    sudo systemctl daemon-reload
    sudo systemctl enable elasticsearch.service
```

Checking to see if Elasticsearch is running.

```shell
    sudo systemctl status elasticsearch.service
```

Starting Elasticsearch

```shell
    sudo systemctl start elasticsearch.service
```

Stopping Elasticsearch

```shell
    sudo systemctl stop elasticsearch.service
```

To remove elasticsearch from auto start use the usually systemd
disable.

```shell
    sudo systemctl disable elasticsearch.service
```


### Installing Elasticsearch, macOS using ports

Homebrew is the documented way on the Elasticsearch website for
installing on macOS. You can also install via MacPorts. 
My quick notes for [install elasticsearch using MacPorts](macOS-elasticsearch.html). 

If you are using MacPorts you can start elasticsearch
with

```
    sudo port load elasticsearch
```

and stop it with

```
    sudo port unload elasticsearch
```

or if you want to restart Elasticsearch

```
    sudo port reload elasticsearch
```


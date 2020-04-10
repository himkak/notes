# Elastic Stack

## Introduction

ELK :  Built on an open source foundation, the Elastic Stack lets you reliably and securely take data from any source, in any format, and search, analyze, and visualize it in real time.
-	E: Elastic Search: Elasticsearch is a distributed, JSON-based search and analytics engine designed for horizontal scalability, maximum reliability, and easy management.

-	L: LogStash: Logstash is a dynamic data collection pipeline with an extensible plugin ecosystem and strong Elasticsearch synergy. It provides functionality to filter, aggregate data.

-	K: Kibana: Visualize your data. Navigate the Elastic Stack. : Kibana gives shape to your data and is the extensible user interface for configuring and managing all aspects of the Elastic Stack.

-   B: Beats: Beats is the platform for single-purpose data shippers. They send data from hundreds or thousands of machines and systems to Logstash or Elasticsearch. Small, lightweight utilities for reading logs from a variety of sources. Usually sends data to logstash. Filebeat(text log files), metricbeat(os and applications), packetbeat(network monitoring), winlobeat(windows event log), libbeat(write your own loag beat)

![Elastic Stack](https://github.com/himkak/my-notes/blob/master/ElasticStack/ElasticStack.PNG)


### How log flows in this stack
![ELK](https://github.com/himkak/my-notes/blob/master/ElasticStack/ELK.png)

-------------------------------------------------------
-------------------------------------------------------

### Elastic Search

#### Installation

##### Docker

Pull the image:
```
docker pull docker.elastic.co/ElasticStack/elasticsearch:6.6.2
```

Run the container: `docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/ElasticStack/elasticsearch:6.6.2`

Elastic search by default runs on 9200 port.  
Elastic search configuration file is config/elasticsearch.yml
![Sample Elastic Search Queries](https://github.com/himkak/my-notes/blob/master/ElasticStack/ElasticSearch_SampleQueries.md)

#### Alerting with watchers

Watcher is part of xpack plugin.  
Install xpack plugin in elasticsearch : `elasticsearch-plugin install x-pack`  
TO send email configure elasticsearch.yml with

![Watcher Overview](https://github.com/himkak/my-notes/blob/master/ElasticStack/ElasticSearch_Watcher.PNG)


![Watcher workflow](https://github.com/himkak/my-notes/blob/master/ElasticStack/WatcherWorkflow.PNG)



-------------------------------------------------------
-------------------------------------------------------

### Kibana
pull the image: 
`docker pull docker.elastic.co/kibana/kibana:6.6.2`

docker run -e "SERVER_NAME=kibana.example.org" -e "ELASTICSEARCH_HOSTS=http://localhost:9200" --link 26461b1d4da7 -itd docker.elastic.co/kibana/kibana:6.6.2 bash


Kibana runs on 5601

Kibana configuration file is config/kibana.yml
It contains the elastic search url.

#### Index Pattern
In order to view the logs you have to create index pattern in Kibana UI.
To create index pattern some sample format logs should have been already pushed into elastic search.  
**To create index pattern**: Kibana UI -> Management -> Index Patterns -> Create Index pattern -> You will see list of ElasticSearch indices -> In the index pattern box enter a pattern that matches at leats one of those indices -> Next Step -> If reqd select the time filter -> create index pattern  

#### Discover
used to view the logs  
**To view logs**: Kibana UI -> Discover -> Select the index pattern in the left side -> From available fields, add the fields you want to view.

#### Visualization
To generate some charts from the logs, charts like pie chart, graph, gauge etc..

#### Dashboard  
TO view the visualization charts, you can create a dashboard and add the visualizations there, and save your dashboard.


-------------------------------------------------------
-------------------------------------------------------

### LogStash

![Logstash Input](https://github.com/himkak/my-notes/blob/master/ElasticStack/LogstashIntro.PNG)


#### Configuration

logstash.conf : It contains the pipeline stages (input, filter, output)

![Logstash Input](https://github.com/himkak/my-notes/blob/master/ElasticStack/LogstashConfig.PNG)

#### Execution
To test if logs are being pushed from logstash to elasticsearch. Execute this below command and write in the cmd:    
`logstash -e "input { stdin { } } output { elasticsearch { hosts => ['localhost:9200'] } }"`

To execute with config file:  
`logstash -f <path to logstash config file>`

Sample logstash.conf file
```json
# #####################COnfig where input comes from beats on 5044 port ##########
# input {
#  beats {
#    port => 5044
#  }
# }
#
# ##################Input comes from logstash command prompt, write any line there and that data will be pushed to elastic search server
 input { 
	stdin { 
	} 
 }
	
# #################Output configuration
output {
  
# ###prints the log line in the console
  stdout {
    codec => rubydebug
  }
 
# ### Sending properly parsed log events to elasticsearch
  elasticsearch {
    hosts => ['localhost:9200']
#    index => "%{[@metadata][beat]}-%{+YYYY.MM.dd}"
#    document_type => "%{[@metadata][type]}"
  }
}

```

-------------------------------------------------------
-------------------------------------------------------

### Beats

#### filebeat
`filebeat -e -c <path to filebeat yml file>`

Filebeat yml content:
```yml
filebeat.inputs:
- type: log
  enabled: true
  paths:
   - C:\Users\hmnsh\Documents\eclipse workspaces\workspace1_poc\SpringMysql\logs\*.log

output.logstash:
  hosts: ["127.0.0.1:5044"]
```

This config file contains, from where the filebeat takes the input and where it sends the output.

## References:
### Getting Started Video:
Elastic Search video: https://www.elastic.co/webinars/getting-started-elasticsearch  
LogStash video https://www.elastic.co/webinars/getting-started-logstash?baymax=rtp&elektra=docs&storm=top-video&iesrc=ctr

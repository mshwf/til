
logs-*,filebeat-*,kibana_sample_data_logs*
index => "%{[@metadata][beat]}-%{[@metadata][version]}-%{+YYYY.MM.dd}"

elasticsearch


account pluralsightt>>>

kibana: localhost:5601 v
elastic: localhost:9200 v
logstach: localhost:9600 X
filebeats: localhost:5044

================installation progress================

- download (jdk-11.0.3_windows-x64_bin.exe): https://www.oracle.com/java/technologies/javase/jdk11-archive-downloads.html


========Configs=========

>>Filebeat:

cd "C:\Program Files\filebeat-7.13.4-windows-x86_64"
.\filebeat.exe -e


>>Logstach:

cd "C:\logstash-7.13.4"
.\bin\logstash.bat -f .\bin\logstash.conf


>>Elasticsearch
cd "C:\Users\mshawaf\Downloads\elk_7.13.4\elasticsearch-7.13.4\bin"
.\elasticsearch.bat

>>Kibana

cd "D:\Work\elk\Kibana\bin"
.\kibana.bat

edit kibana.yml => elasticsearch.hosts: ["http://localhost:9200"]

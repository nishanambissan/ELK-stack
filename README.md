# ELK-stack
ELK Stack simplest implementation

*INTRODUCTION*
If you have not covered the basics before coming to this repository, don't worry. 
Here's the briefest simplest description:

You are using Logstash to do log analysis (converting or applying algorithms using grok patterns in your logstash config file)
Logtsash listens to file inputs (basically can watch an input stream say it watches a folder for log files to be written to, and sends the output to elastic search) You can use Filebeats too which is part of the ELK stack now.

Elastic Search listens to logstash and gets the shipped logs and stores it in an internal DB which can be queried easily

Kibana visualises your logstash data but listening to the default port for inputs (which is generally Elastic search that runs on default port 9200.) 

*SETUP*

To start off with setting up the ELK stack locally, you need 3 things:

Logstash
Elastic Search
Kibana

1. Download the latest version of them all from these links:

https://www.elastic.co/downloads/logstash
https://www.elastic.co/downloads/elasticsearch
https://www.elastic.co/downloads/kibana

I place the unzipped folders on my C drive. You can place them anywhere you like, but I have encountered issues when the directory it lies in has a space (like Program Files for instance). 

*LOGSTASH BIT*

1. Copy over the config file that is in this repo to your logstash

2. Run this command from Git bash or any command shell you prefer from the logstash directory

bin/logstash -f logstash-file-input.conf --config.reload.automatic --debug

The debug mode helps you to see which files are being globbed and if your file input plugin is not working, then you can troubleshoot why its not reading from your log files and shipping to Elastic Search

*ELASTIC SEARCH BIT*

1. Run this command from the Elastic search installation directory:

bin/elasticsearch.bat

*KIBANA BIT*

1. Run this command from the Kibana installation directory:

bin/kibana.bat

Now go browse http://localhost:5601
And you should see the kibana GUI.
Go to Discover and it prompts you to create an index pattern. Search for the same index that you right logs into looking into your logstash config file.
And then when you do a search on that index back on Discover panel, you should the see the logs flowing in.






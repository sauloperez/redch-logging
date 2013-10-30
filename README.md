# Redch-logging

Redch-logging uses [logstash](http://logstash.net/) to manage events and logs. It collects, parses and stores them in a central place


## Installation

First of all, install logstash and elasticsearch in Mac OS X via Homebrew.

Let's start with logstash:
    
    brew install logstash

and then install elasticsearch version 0.90.3 (as the [logstash documentation](http://logstash.net/docs/1.2.2/tutorials/getting-started-centralized) states).

Search for available versions of the homebrew elasticsearch formula:

    brew versions elasticsearch   
    0.90.5   git checkout 7a522af /usr/local/Library/Formula/elasticsearch.rb
    0.90.3   git checkout c2fd809 /usr/local/Library/Formula/elasticsearch.rb
    0.90.2   git checkout f1d6b2a /usr/local/Library/Formula/elasticsearch.rb
    0.90.1   git checkout 834d035 /usr/local/Library/Formula/elasticsearch.rb
    0.90.0   git checkout c005107 /usr/local/Library/Formula/elasticsearch.rb

Change directory to /usr/local and checkout 0.90.3 version:

    git checkout c2fd809 /usr/local/Library/Formula/elasticsearch.rb

and finally install elasticsearch:

    brew install elasticsearch


## Usage

Once installed run elasticsearch specifying the right config file:

    elasticsearch -f -D es.config=/usr/local/opt/elasticsearch/config/elasticsearch.yml

and then run the logstash agent:

    logstash agent -f sos.conf 



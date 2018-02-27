# GROK

## WHAT IS GROK

Predefined Regex,Cutting strings into JSON
Detail Grok Pattern Sees:
https://github.com/elastic/logstash/blob/v1.4.2/patterns/grok-patterns

## DEBUG

May Test Ur Grok Pattern with Ur Test Strings
https://grokdebug.herokuapp.com/


## HOW TO CONFIG

Here is the Example:
For Now We Just Use the First Pattern
filebeat.yml:
	filebeat.prospectors:

	# Each - is a prospector. Most options can be set at the prospector level, so
	# you can use different prospectors for various configurations.
	# Below are the prospector specific configurations.

	- input_type: log

	  # Paths that should be crawled and fetched. Glob based paths.
	  paths:
	    - /var/log/nginx/access.log
	    #- /var/log/*.log
	    #- c:\programdata\elasticsearch\logs\*
	  grok_pattern: ["%{WORD:msg_type}\\|%{DATA:time}\\|%{NUMBER:ts}\\|%{DATA:process}\\|%{DATA:device}\\|%{WORD:rest_content}"]



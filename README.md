haproxy-statsd
--------------
This script reports stats to statsd using [haproxy's stats interface](https://code.google.com/p/haproxy-docs/wiki/StatisticsMonitoring).

Usage
-----

	usage: haproxy-statsd.py [-h] [-c CONFIG]

	Report haproxy stats to statsd

	optional arguments:
	  -h, --help            show this help message and exit
	  -c CONFIG, --config CONFIG
	                        Config file location


Config file
-----------
Default location is ./haproxy-statsd.conf.

	[haproxy-statsd]
	haproxy_url = http://127.0.0.1:1936/;csv
	haproxy_user =
	haproxy_password =
	statsd_host = 127.0.0.1
	statsd_port = 8125
	statsd_namespace = haproxy.(HOSTNAME)

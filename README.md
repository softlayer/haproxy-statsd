haproxy-statsd
--------------
This script reports stats to statsd using [haproxy's](http://haproxy.1wt.eu/) stats interface. [See Stats Interface Demo](http://demo.1wt.eu/) ([CSV](http://demo.1wt.eu/;csv)).

Supported with Python 2.6 and Python 2.7.

Usage
-----
```
usage: report_haproxy.py [-h] [-c CONFIG] [-1]

Report haproxy stats to statsd

optional arguments:
  -h, --help            show this help message and exit
  -c CONFIG, --config CONFIG
                        Config file location
  -1, --once        Run once and exit
```

Config file
-----------
Default location is ./haproxy-statsd.conf.

```
[haproxy-statsd]
haproxy_url = http://127.0.0.1:1936/;csv
haproxy_user =
haproxy_password =
statsd_host = 127.0.0.1
statsd_port = 8125
statsd_namespace = haproxy.(HOSTNAME)
interval = 5
```

Statsd Paths
------------
All metrics are reported with paths matching this format:

    stats.gauges.[namespace].[pxname].[svname].[statname]

The following stats are monitored: scur, smax, ereq, econ, rate, bin, bout, hrsp_1xx, hrsp_2xx, hrsp_3xx, hrsp_4xx, hrsp_5xx, qtime, ctime, rtime, ttime.

For more information about those metrics please refer to: [HAProxy' stats](http://cbonte.github.io/haproxy-dconv/configuration-1.5.html#9.1) documentation.

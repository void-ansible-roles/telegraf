# telegraf
Role to perform base configuration of a telegraf daemon

What does this role do?
-----------------------

This role installs and configures telegraf on a host.

Meta
----

Files Managed:
  * /etc/telegraf/telegraf.conf
  * /etc/telegraf/telegraf.d/host.conf

Optional Variables:
  * telegraf:
    * remotes: list of tsdb servers in host:port format
    * global_tags: list of tags to be applied from this host 'key=value' formatted list
    * agent:
      * interval: metric collection interval
      * round_interval: quantize to aligned intervals
      * metric_batch_size: number of metrics to submit at one time
      * metric_buffer_limit: number of metrics to buffer temporarily
      * collection_jitter: add artificial plugin jitter to avoid loading the host with monitoring
      * flush_interval: interval to try and flush the buffers
      * flush_jitter: artificial jitter to prevent flush from spiking
      * precision: time precision reported
    * output:
      * influxdb:
        * urls: string containing a list of urls
        * database: database to write metrics to
        * retention_policy: policy to write metrics with
        * write_consistency: consistency to require before metrics are considered written
        * timeout: time to wait for metrics to be written
        * username: username to authenticate to the database
        * password: password to authenticate to the database

Files Required:
  * None

Optional Files:
  * None

Conflicting Roles:
  * None

Depends on:
  * network

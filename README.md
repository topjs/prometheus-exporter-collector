# Prometheus-exporter-collector
作为Nightingale的插件，用于收集prometheus的指标

prometheus作为优秀的开源监控产品，本身不仅完整的指标体系，还拥有丰富的指标采集解决方案。通过各种exporter可以覆盖中间件，操作系统，开发语言等等方面的监控指标采集

Prometheus-exporter-collector以插件形式集成在collector中，通过Nightingale插件采集，collector采集目标exporter指标并上报

## 快速构建 

    $ mkdir -p $GOPATH/src/github.com/n9e
    $ cd $GOPATH/src/github.com/n9e
    $ git clone https://github.com/n9e/prometheus-exporter-collector.git
    $ cd prometheus-exporter-collector
    $ go build
    $ cat plugin.test.json | ./prometheus-exporter-collector 


 ### 配置参数
 Name                             |  type     | Description
 ---------------------------------|-----------|--------------------------------------------------------------------------------------------------
 exporter_urls                    | array     | Address to collect metric for prometheus exporter.
 append_tags                      | array     | Append tags for n9e metric default empty
 endpoint                         | string    | Field endpoint for n9e metric default empty
 ignore_metrics_prefix            | array     | Ignore metric prefix default empty
 timeout                          | int       | Timeout for access a exporter url default 500ms
 metric_prefix                    | string    | append metric prefix when push to n9e. e.g. 'xx_exporter.'
 metric_type                      | map       | specify metric type
 default_mapping_metric_type      | string    | Default conversion rule for Prometheus cumulative metrics. support COUNTER and SUBTRACT. default SUBTRACT
 ###
 
 ###

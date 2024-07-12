# 监控k3s集群和Pods

# Prometheus 模版和配置文件

[alert 通知指标规则汇总](https://samber.github.io/awesome-prometheus-alerts/)

## 使用psql-exporter

[docs](https://github.com/prometheus-community/postgres_exporter)

[download](https://github.com/prometheus-community/postgres_exporter/releases)

### 为了PG的安全这里使用的是本地("local" is for Unix),需要加上host代表

#### 这里用临时环境变量运行,不把超级管理密码记录到history

```shell
export DATA_SOURCE_NAME="postgresql://postgres:password@:48885/postgres?sslmode=disable&host=/var/run/postgresql"
```

#### 运行

```shell
./postgres_exporter --web.listen-address :1111
```
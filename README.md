# chronix.ops
Repository for Helm charts, docker-compose etc.

## Helm Charts

The following helm charts do exist:

| Chart                                   | Description                                                                           |
| --------------------------------------- | ------------------------------------------------------------------------------------- |
| [ingester](./helm/charts/ingester)      | Installation of the [chronix.ingester](https://github.com/ChronixDB/chronix.ingester) |


For using any of the provided charts add the following helm repository:

```console
$ helm repo add https://raw.githubusercontent.com/ChronixDB/chronix.ops/master/helm/repo/
```

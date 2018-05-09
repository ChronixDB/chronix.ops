# chronix.ingester

The Chronix Ingester batches up sample data from various sources and
stores it as chunks in Chronix. 

## TL;DR;

```console
$ helm repo add https://raw.githubusercontent.com/ChronixDB/chronix.ops/master/helm/repo/
$ helm install chronix/ingester
```

## Installing the Chart

To install the chart with the release name `my-release` in namespace `my-space`:

```console
$ helm repo add https://raw.githubusercontent.com/ChronixDB/chronix.ops/master/helm/repo/
$ helm install chronix/ingester --name my-release --namespace my-space
```

The command deploys the chronix.ingester into the Kubernetes cluster in the default configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.
There is a zero percent chance that you will want the default configuration because it just prints out the help page.

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```console
$ helm delete --purge my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

The following table lists the configurable parameters of the helm chart and their default values.

Parameter | Description | Default
--- | --- | ---
`affinity` | node/pod affinities | None
`image.pullPolicy` | Image pull policy | `IfNotPresent`
`image.repository` | Image repository | `chronix/chronix.ingester`
`image.tag` | Image tag | `latest`
`ingester.args` | Customized program arguments | `{}`
`ingester.command` | Customized command | None
`ingester.containerPort` | Port on which the chronix.ingester is waiting for connections | 8080
`nodeSelector` | node labels for pod assignment | `{}`
`resources` | pod resource requests & limits | `{}`
`tolerations` | List of node taints to tolerate | `[]`

The `ingester.args` parameter must be adjusted to pass the chronix.ingester parameters of your choice.
See [chronix.ingester documentation](https://github.com/ChronixDB/chronix.ingester) for help!


Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example,

```console
$ helm install chronix/ingester --name my-release \
  --set=resources.limits.cpu=200m
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart. For example,

```console
$ helm install chronix/ingester --name my-release -f values.yaml
```

> **Tip**: You can use the default [values.yaml](values.yaml) as a reference

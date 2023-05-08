# Agent Helm Chart

## Installing the Chart

Add the `scalr-agent` repo to [Helm](https://helm.sh/).

```shell
helm repo add scalr-agent https://scalr.github.io/agent-helm/
```

After that you can install the chart.

```shell
helm upgrade --install scalr-agent scalr-agent/scalr-agent \
    --set agent.url=... \
    --set agent.token=...
```

## Releasing 

Bump the version in [Chart.yaml](./charts/scalr-agent/Chart.yaml), commit and push.

> **Warning** 
> do not create a tag yourself!

GitHub Action release workflow will then using [Helm chart releaser](https://github.com/helm/chart-releaser-action)

* create a tag `scalr-agent-<version>`
* create a [release](https://github.com/Scalr/agent-helm/releases) associated with the new tag
* commit an updated index.yaml with the new release
* redeploy the GitHub pages to serve the new index.yaml

> **Note** 
> there might be a slight delay between the release and the `index.yaml` update, as GitHub pages have to be re-deployed.


## TODO

- Pre-commit hooks(lint, docs)

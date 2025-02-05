## This is a fork of the temporal-ui repo, with certain svelte configs disabled
## as they don't work well with CF argo tunnels

To publish the docker image, first ensure you're logged into docker hub, using `docker login`
- If this fails, you might need to get rid of the `creds` field from your `config.json` file in the Docker directory

Setup buildx using `docker buildx create --use`

Build, tag, and push the image:

```
docker buildx build \
    --platform linux/amd64,linux/arm64 \
    -t bryantandersonvapi/temporal-ui:latest \
    -t bryantandersonvapi/temporal-ui:0.0.2 \
    --push \
    .
```

# ui-server

[![Publish Docker image](https://github.com/temporalio/ui-server/actions/workflows/docker.yml/badge.svg)](https://github.com/temporalio/ui-server/actions/workflows/docker.yml)

## Development

For contributions follow UI's development guide https://github.com/temporalio/ui


## To View gRPC routes:
[Temporal API Workflowservice](https://github.com/temporalio/api/blob/master/temporal/api/workflowservice/v1/service.proto)

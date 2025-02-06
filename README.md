# Docker image for running Azure CLI commands in an Azure Pipelines container job

<!-- markdownlint-disable MD013 -->
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://github.com/swissgrc/docker-azure-pipelines-azurecli-net8/blob/main/LICENSE) [![Build](https://img.shields.io/github/actions/workflow/status/swissgrc/docker-azure-pipelines-azurecli-net8/publish.yml?branch=develop&style=flat-square)](https://github.com/swissgrc/docker-azure-pipelines-azurecli-net8/actions/workflows/publish.yml) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=swissgrc_docker-azure-pipelines-azurecli-net8&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=swissgrc_docker-azure-pipelines-azurecli-net8) [![Pulls](https://img.shields.io/docker/pulls/swissgrc/azure-pipelines-azurecli.svg?style=flat-square)](https://hub.docker.com/r/swissgrc/azure-pipelines-azurecli) [![Stars](https://img.shields.io/docker/stars/swissgrc/azure-pipelines-azurecli.svg?style=flat-square)](https://hub.docker.com/r/swissgrc/azure-pipelines-azurecli)
<!-- markdownlint-restore -->

Docker image to run Azure CLI commands in [Azure Pipelines container jobs].

## Usage

This image can be used to run Azure CLI commands in [Azure Pipelines container jobs].

### Azure Pipelines Container Job

To use the image in an Azure Pipelines Container Job, add one of the following example tasks and use it with the `container` property.

The following example shows the container used for a deployment step with a Azure CLI command:

```yaml
  - stage: deploy
    jobs:
      - deployment: runAzureCLI
        container: swissgrc/azure-pipelines-azurecli:latest-net8
        environment: smarthotel-dev
        strategy:
          runOnce:
            deploy:
              steps:
                - bash: |
                    az version
```

### Included Software
- Azure CLI

### Tags

| Tag           | Description                                             | Size                                                                                                                                   |
|---------------|---------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| latest-net8   | Latest stable release (from `main` branch)              | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-azurecli/latest?style=flat-square)        |
| unstable-net8 | Latest unstable release (from `develop` branch)         | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-azurecli/unstable?style=flat-square)      |
| x.y.z-net8    | Image for a specific version ofAzure CLI                |                                                                                                                                        |

[Azure Pipelines container jobs]: https://docs.microsoft.com/en-us/azure/devops/pipelines/process/container-phases

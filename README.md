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

### Tags

| Tag           | Description                                                                                               | Base Image                                | Azure CLI | Size                                                                                                                                   |
|---------------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------|
| latest        | Latest stable release (from `main` branch)                                                                | swissgrc/azure-pipelines-dotnet:8.0.303   | 2.62.0    | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-azurecli/latest?style=flat-square)        |
| latest-net8   | Identical to `latest` tag                                                                                 |                                           |           | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-azurecli/latest-net8?style=flat-square)   |
| unstable      | Latest unstable release (from `develop` branch)                                                           | swissgrc/azure-pipelines-dotnet:8.0.303   | 2.62.0    | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-azurecli/unstable?style=flat-square)      |
| unstable-net8 | Identical to `unstable` tag                                                                               |                                           |           | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-azurecli/unstable-net8?style=flat-square) |
| 2.55.0-net8   | [Azure CLI 2.55.0](https://learn.microsoft.com/en-us/cli/azure/release-notes-azure-cli#december-05-2023)  | swissgrc/azure-pipelines-dotnet:8.0.100   | 2.55.0    | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-azurecli/2.55.0-net8?style=flat-square)   |
| 2.56.0-net8   | [Azure CLI 2.56.0](https://learn.microsoft.com/en-us/cli/azure/release-notes-azure-cli#january-09-2024)   | swissgrc/azure-pipelines-dotnet:8.0.101   | 2.56.0    | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-azurecli/2.56.0-net8?style=flat-square)   |
| 2.57.0-net8   | [Azure CLI 2.57.0](https://learn.microsoft.com/en-us/cli/azure/release-notes-azure-cli#february-06-2024)  | swissgrc/azure-pipelines-dotnet:8.0.200   | 2.57.0    | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-azurecli/2.57.0-net8?style=flat-square)   |
| 2.58.0-net8   | [Azure CLI 2.58.0](https://learn.microsoft.com/en-us/cli/azure/release-notes-azure-cli#march-05-2024)     | swissgrc/azure-pipelines-dotnet:8.0.202   | 2.58.0    | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-azurecli/2.58.0-net8?style=flat-square)   |
| 2.59.0-net8   | [Azure CLI 2.59.0](https://learn.microsoft.com/en-us/cli/azure/release-notes-azure-cli#april-02-2024)     | swissgrc/azure-pipelines-dotnet:8.0.204   | 2.59.0    | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-azurecli/2.59.0-net8?style=flat-square)   |
| 2.60.0-net8   | [Azure CLI 2.60.0](https://learn.microsoft.com/en-us/cli/azure/release-notes-azure-cli#april-30-2024)     | swissgrc/azure-pipelines-dotnet:8.0.300   | 2.60.0    | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-azurecli/2.60.0-net8?style=flat-square)   |
| 2.61.0-net8   | [Azure CLI 2.61.0](https://learn.microsoft.com/en-us/cli/azure/release-notes-azure-cli#may-21-2024)       | swissgrc/azure-pipelines-dotnet:8.0.301   | 2.61.0    | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-azurecli/2.61.0-net8?style=flat-square)   |
| 2.62.0-net8   | [Azure CLI 2.62.0](https://learn.microsoft.com/en-us/cli/azure/release-notes-azure-cli#july-09-2024)      | swissgrc/azure-pipelines-dotnet:8.0.303   | 2.62.0    | ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/swissgrc/azure-pipelines-azurecli/2.62.0-net8?style=flat-square)   |

[Azure Pipelines container jobs]: https://docs.microsoft.com/en-us/azure/devops/pipelines/process/container-phases

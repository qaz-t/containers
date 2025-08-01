# Bitnami package for OpenSearch Dashboards

## What is OpenSearch Dashboards?

> OpenSearch Dashboards is a visualization tool for OpenSearch installations. OpenSearch is a scalable open-source solution for search, analytics, and observability.

[Overview of OpenSearch Dashboards](https://opensearch.org/)
Trademarks: This software listing is packaged by Bitnami. The respective trademarks mentioned in the offering are owned by the respective companies, and use of them does not imply any affiliation or endorsement.

## TL;DR

```console
docker run -it --name opensearch-dashboards bitnami/opensearch-dashboards:latest
```

## ⚠️ Important Notice: Upcoming changes to the Bitnami Catalog

Beginning August 28th, 2025, Bitnami will evolve its public catalog to offer a curated set of hardened, security-focused images under the new [Bitnami Secure Images initiative](https://news.broadcom.com/app-dev/broadcom-introduces-bitnami-secure-images-for-production-ready-containerized-applications). As part of this transition:

- Granting community users access for the first time to security-optimized versions of popular container images.
- Bitnami will begin deprecating support for non-hardened, Debian-based software images in its free tier and will gradually remove non-latest tags from the public catalog. As a result, community users will have access to a reduced number of hardened images. These images are published only under the “latest” tag and are intended for development purposes
- Starting August 28th, over two weeks, all existing container images, including older or versioned tags (e.g., 2.50.0, 10.6), will be migrated from the public catalog (docker.io/bitnami) to the “Bitnami Legacy” repository (docker.io/bitnamilegacy), where they will no longer receive updates.
- For production workloads and long-term support, users are encouraged to adopt Bitnami Secure Images, which include hardened containers, smaller attack surfaces, CVE transparency (via VEX/KEV), SBOMs, and enterprise support.

These changes aim to improve the security posture of all Bitnami users by promoting best practices for software supply chain integrity and up-to-date deployments. For more details, visit the [Bitnami Secure Images announcement](https://github.com/bitnami/containers/issues/83267).

## Why use Bitnami Secure Images?

- Bitnami Secure Images and Helm charts are built to make open source more secure and enterprise ready.
- Triage security vulnerabilities faster, with transparency into CVE risks using industry standard Vulnerability Exploitability Exchange (VEX), KEV, and EPSS scores.
- Our hardened images use a minimal OS (Photon Linux), which reduces the attack surface while maintaining extensibility through the use of an industry standard package format.
- Stay more secure and compliant with continuously built images updated within hours of upstream patches.
- Bitnami containers, virtual machines and cloud images use the same components and configuration approach - making it easy to switch between formats based on your project needs.
- Hardened images come with attestation signatures (Notation), SBOMs, virus scan reports and other metadata produced in an SLSA-3 compliant software factory.

Only a subset of BSI applications are available for free. Looking to access the entire catalog of applications as well as enterprise support? Try the [commercial edition of Bitnami Secure Images today](https://www.arrow.com/globalecs/uk/products/bitnami-secure-images/).

## Supported tags and respective `Dockerfile` links

Learn more about the Bitnami tagging policy and the difference between rolling tags and immutable tags [in our documentation page](https://techdocs.broadcom.com/us/en/vmware-tanzu/application-catalog/tanzu-application-catalog/services/tac-doc/apps-tutorials-understand-rolling-tags-containers-index.html).

You can see the equivalence between the different tags by taking a look at the `tags-info.yaml` file present in the branch folder, i.e `bitnami/ASSET/BRANCH/DISTRO/tags-info.yaml`.

Subscribe to project updates by watching the [bitnami/containers GitHub repo](https://github.com/bitnami/containers).

## Get this image

The recommended way to get the Bitnami OpenSearch Dashboards Docker Image is to pull the prebuilt image from the [Docker Hub Registry](https://hub.docker.com/r/bitnami/opensearch-dashboards).

```console
docker pull bitnami/opensearch-dashboards:latest
```

To use a specific version, you can pull a versioned tag. You can view the [list of available versions](https://hub.docker.com/r/bitnami/opensearch-dashboards/tags/) in the Docker Hub Registry.

```console
docker pull bitnami/opensearch-dashboards:[TAG]
```

If you wish, you can also build the image yourself by cloning the repository, changing to the directory containing the Dockerfile and executing the `docker build` command. Remember to replace the `APP`, `VERSION` and `OPERATING-SYSTEM` path placeholders in the example command below with the correct values.

```console
git clone https://github.com/bitnami/containers.git
cd bitnami/APP/VERSION/OPERATING-SYSTEM
docker build -t bitnami/APP:latest .
```

## Maintenance

### Upgrade this image

Bitnami provides up-to-date versions of OpenSearch Dashboards, including security patches, soon after they are made upstream. We recommend that you follow these steps to upgrade your container.

#### Step 1: Get the updated image

```console
docker pull bitnami/opensearch-dashboards:latest
```

#### Step 2: Remove the currently running container

```console
docker rm -v opensearch-dashboards
```

#### Step 3: Run the new image

Re-create your container from the new image.

```console
docker run --name opensearch-dashboards bitnami/opensearch-dashboards:latest
```

## Configuration

### Environment variables

#### Customizable environment variables

| Name                                                     | Description                                                                                     | Default Value                                                   |
|----------------------------------------------------------|-------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|
| `OPENSEARCH_DASHBOARDS_OPENSEARCH_URL`                   | Opensearch URL. Provide Client node url in the case of a cluster                                | `opensearch`                                                    |
| `OPENSEARCH_DASHBOARDS_OPENSEARCH_PORT_NUMBER`           | Elasticsearch port                                                                              | `9200`                                                          |
| `OPENSEARCH_DASHBOARDS_HOST`                             | Opensearch Dashboards host                                                                      | `0.0.0.0`                                                       |
| `OPENSEARCH_DASHBOARDS_PORT_NUMBER`                      | Opensearch Dashboards port                                                                      | `5601`                                                          |
| `OPENSEARCH_DASHBOARDS_WAIT_READY_MAX_RETRIES`           | Max retries to wait for Opensearch Dashboards to be ready                                       | `30`                                                            |
| `OPENSEARCH_DASHBOARDS_INITSCRIPTS_START_SERVER`         | Whether to start the Opensearch Dashboards server before executing the init scripts             | `yes`                                                           |
| `OPENSEARCH_DASHBOARDS_FORCE_INITSCRIPTS`                | Whether to force the execution of the init scripts                                              | `no`                                                            |
| `OPENSEARCH_DASHBOARDS_DISABLE_STRICT_CSP`               | Disable strict Content Security Policy (CSP) for Opensearch Dashboards                          | `no`                                                            |
| `OPENSEARCH_DASHBOARDS_CERTS_DIR`                        | Path to certificates folder.                                                                    | `${SERVER_CONF_DIR}/certs`                                      |
| `OPENSEARCH_DASHBOARDS_SERVER_ENABLE_TLS`                | Enable TLS for inbound connections via HTTPS.                                                   | `false`                                                         |
| `OPENSEARCH_DASHBOARDS_SERVER_KEYSTORE_LOCATION`         | Path to Keystore                                                                                | `${SERVER_CERTS_DIR}/server/opensearch-dashboards.keystore.p12` |
| `OPENSEARCH_DASHBOARDS_SERVER_KEYSTORE_PASSWORD`         | Password for the Opensearch keystore containing the certificates or password-protected PEM key. | `nil`                                                           |
| `OPENSEARCH_DASHBOARDS_SERVER_TLS_USE_PEM`               | Configure Opensearch Dashboards server TLS settings using PEM certificates.                     | `false`                                                         |
| `OPENSEARCH_DASHBOARDS_SERVER_CERT_LOCATION`             | Path to PEM node certificate.                                                                   | `${SERVER_CERTS_DIR}/server/tls.crt`                            |
| `OPENSEARCH_DASHBOARDS_SERVER_KEY_LOCATION`              | Path to PEM node key.                                                                           | `${SERVER_CERTS_DIR}/server/tls.key`                            |
| `OPENSEARCH_DASHBOARDS_SERVER_KEY_PASSWORD`              | Password for the Opensearch node PEM key.                                                       | `nil`                                                           |
| `OPENSEARCH_DASHBOARDS_PASSWORD`                         | Opensearch Dashboards password.                                                                 | `nil`                                                           |
| `OPENSEARCH_DASHBOARDS_OPENSEARCH_ENABLE_TLS`            | Enable TLS for Opensearch communications.                                                       | `false`                                                         |
| `OPENSEARCH_DASHBOARDS_OPENSEARCH_TLS_VERIFICATION_MODE` | Opensearch TLS verification mode.                                                               | `full`                                                          |
| `OPENSEARCH_DASHBOARDS_OPENSEARCH_TRUSTSTORE_LOCATION`   | Path to Opensearch Truststore.                                                                  | `${SERVER_CERTS_DIR}/opensearch/opensearch.truststore.p12`      |
| `OPENSEARCH_DASHBOARDS_OPENSEARCH_TRUSTSTORE_PASSWORD`   | Password for the Opensearch truststore.                                                         | `nil`                                                           |
| `OPENSEARCH_DASHBOARDS_OPENSEARCH_TLS_USE_PEM`           | Configure Opensearch TLS settings using PEM certificates.                                       | `false`                                                         |
| `OPENSEARCH_DASHBOARDS_OPENSEARCH_CA_CERT_LOCATION`      | Path to Opensearch CA certificate.                                                              | `${SERVER_CERTS_DIR}/opensearch/ca.crt`                         |

#### Read-only environment variables

| Name                                        | Description                                                                                   | Value                                          |
|---------------------------------------------|-----------------------------------------------------------------------------------------------|------------------------------------------------|
| `SERVER_FLAVOR`                             | Server flavor. Valid values: `kibana` or `opensearch-dashboards`.                             | `opensearch-dashboards`                        |
| `BITNAMI_VOLUME_DIR`                        | Directory where to mount volumes                                                              | `/bitnami`                                     |
| `OPENSEARCH_DASHBOARDS_VOLUME_DIR`          | Opensearch Dashboards persistence directory                                                   | `${BITNAMI_VOLUME_DIR}/opensearch-dashboards`  |
| `OPENSEARCH_DASHBOARDS_BASE_DIR`            | Opensearch Dashboards installation directory                                                  | `${BITNAMI_ROOT_DIR}/opensearch-dashboards`    |
| `OPENSEARCH_DASHBOARDS_CONF_DIR`            | Opensearch Dashboards configuration directory                                                 | `${SERVER_BASE_DIR}/config`                    |
| `OPENSEARCH_DASHBOARDS_DEFAULT_CONF_DIR`    | Opensearch Dashboards default configuration directory                                         | `${SERVER_BASE_DIR}/config.default`            |
| `OPENSEARCH_DASHBOARDS_LOGS_DIR`            | Opensearch Dashboards logs directory                                                          | `${SERVER_BASE_DIR}/logs`                      |
| `OPENSEARCH_DASHBOARDS_TMP_DIR`             | Opensearch Dashboards temporary directory                                                     | `${SERVER_BASE_DIR}/tmp`                       |
| `OPENSEARCH_DASHBOARDS_BIN_DIR`             | Opensearch Dashboards executable directory                                                    | `${SERVER_BASE_DIR}/bin`                       |
| `OPENSEARCH_DASHBOARDS_PLUGINS_DIR`         | Opensearch Dashboards plugins directory                                                       | `${SERVER_BASE_DIR}/plugins`                   |
| `OPENSEARCH_DASHBOARDS_DEFAULT_PLUGINS_DIR` | Opensearch Dashboards default plugins directory                                               | `${SERVER_BASE_DIR}/plugins.default`           |
| `OPENSEARCH_DASHBOARDS_DATA_DIR`            | Opensearch Dashboards data directory                                                          | `${SERVER_VOLUME_DIR}/data`                    |
| `OPENSEARCH_DASHBOARDS_MOUNTED_CONF_DIR`    | Directory for including custom configuration files (that override the default generated ones) | `${SERVER_VOLUME_DIR}/conf`                    |
| `OPENSEARCH_DASHBOARDS_CONF_FILE`           | Path to Opensearch Dashboards configuration file                                              | `${SERVER_CONF_DIR}/opensearch_dashboards.yml` |
| `OPENSEARCH_DASHBOARDS_LOG_FILE`            | Path to the Opensearch Dashboards log file                                                    | `${SERVER_LOGS_DIR}/opensearch-dashboards.log` |
| `OPENSEARCH_DASHBOARDS_PID_FILE`            | Path to the Opensearch Dashboards pid file                                                    | `${SERVER_TMP_DIR}/opensearch-dashboards.pid`  |
| `OPENSEARCH_DASHBOARDS_INITSCRIPTS_DIR`     | Path to the Opensearch Dashboards container init scripts directory                            | `/docker-entrypoint-initdb.d`                  |
| `OPENSEARCH_DASHBOARDS_DAEMON_USER`         | Opensearch Dashboards system user                                                             | `opensearch-dashboards`                        |
| `OPENSEARCH_DASHBOARDS_DAEMON_GROUP`        | Opensearch Dashboards system group                                                            | `opensearch-dashboards`                        |

### Running commands

To run commands inside this container you can use `docker run`, for example to execute `opensearch-dashboards --help` you can follow the example below:

```console
docker run --rm --name opensearch-dashboards bitnami/opensearch-dashboards:latest --help
```

Check the [official OpenSearch Dashboards documentation](https://opensearch.org/docs/) for more information about how to use OpenSearch Dashboards.

## Notable Changes

### Starting January 16, 2024

- The `docker-compose.yaml` file has been removed, as it was solely intended for internal testing purposes.

## Contributing

We'd love for you to contribute to this Docker image. You can request new features by creating an [issue](https://github.com/bitnami/containers/issues) or submitting a [pull request](https://github.com/bitnami/containers/pulls) with your contribution.

## Issues

If you encountered a problem running this container, you can file an [issue](https://github.com/bitnami/containers/issues/new/choose). For us to provide better support, be sure to fill the issue template.

## License

Copyright &copy; 2025 Bitnami

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

<http://www.apache.org/licenses/LICENSE-2.0>

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

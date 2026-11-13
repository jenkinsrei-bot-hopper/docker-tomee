# What is TomEE?

Apache TomEE, pronounced "Tommy", combines Apache Tomcat with enterprise Java technologies.
We start with Apache Tomcat, add the TomEE components, and package the result as a ready-to-run server.

%%LOGO%%

## Dockerfile versions

| Source directory | Apache TomEE release | Release line |
| --- | --- | --- |
| `TomEE-10.3/` | `10.3.0` | Current stable 10.x source |
| `TomEE-10.2/` | `10.2.0` | Previous stable 10.x source |
| `TomEE-11.0/` | `11.0.0-M2` | 11.0 milestone (pre-release) |

Each release line provides JRE 17, 21, and 25 variants, with Eclipse Temurin on Ubuntu or Alpine and IBM Semeru on Ubuntu. Each runtime/base combination has `webprofile`, `microprofile`, `plus`, and `plume` flavors. See the [Apache TomEE downloads page](https://tomee.apache.org/download.html) for release information.

The Dockerfiles verify a release-specific, pinned SHA512 digest and the detached GPG signature. The signing key is selected by its full fingerprint from the official Apache TomEE `KEYS` file. The 10.2 Dockerfiles are retained unchanged.

## Versions and tags

The complete, authoritative list of published tags is maintained separately in the Docker Official Images [`library/tomee` file](https://github.com/docker-library/official-images/blob/master/library/tomee). A source update here does not itself publish or move Docker Hub tags, so this repository may be ahead of the registry.

Explicit tags follow this pattern (vendor names are case-sensitive):

```text
<tomee-version>-jre<java-version>-<vendor>-<os>-<flavor>
```

Examples for the new source releases are `10.3.0-jre17-Temurin-alpine-webprofile` and `11.0.0-M2-jre21-Semeru-ubuntu-microprofile`. Short release aliases and aliases that omit default components are defined in `library/tomee`, not by directory names. Stable `latest`/unversioned aliases must not select an 11.0 milestone.

## How to use this image

To try the new 10.3.0 source before its corresponding official tags are published, build and run it locally:

```sh
docker build -t local/tomee:10.3.0-jre17-Temurin-alpine-webprofile \
  TomEE-10.3/jre17/Temurin/alpine/webprofile
docker run -it --rm -p 8888:8080 \
  local/tomee:10.3.0-jre17-Temurin-alpine-webprofile
```

For the 11.0.0-M2 milestone, choose the equivalent path under `TomEE-11.0/` and tag the local image accordingly. Once the desired official tag is present in `library/tomee`, use `tomee:<tag>` instead of the local image name.

The default command is `CMD ["catalina.sh", "run"]`. After publishing port 8080 as above, visit `http://localhost:8888` (or `http://host-ip:8888`).

The configuration files are available in `/usr/local/tomee/conf/`. By default, no user is included in the `manager-gui` role required to operate the `/manager/html` web application. To use it, define an appropriate user in `tomcat-users.xml`.

You can also use a published image as a base image and add your application:

```dockerfile
FROM tomee:<published-tag>
COPY <application>.war /usr/local/tomee/webapps/
```

## Issues and contributors

Report issues to the [Tomitribe team](https://github.com/tomitribe/docker-tomee/issues). Contributions are welcome through a fork of [tomitribe/docker-tomee](https://github.com/tomitribe/docker-tomee) and a pull request.

## License

Apache TomEE and the files used to produce these Docker images are licensed under the [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0).

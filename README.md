[![Open Issues](https://img.shields.io/github/issues/VantStark/docker-atlassian-confluence.svg)](https://github.com/VantStark/docker-atlassian-confluence/issues) [![Stars on GitHub](https://img.shields.io/github/stars/VantStark/docker-atlassian-confluence.svg)](https://github.com/VantStark/docker-atlassian-confluence/stargazers) [![Forks on GitHub](https://img.shields.io/github/forks/VantStark/docker-atlassian-confluence.svg)](https://github.com/VantStark/docker-atlassian-confluence/network) [![Stars on Docker Hub](https://img.shields.io/docker/stars/techzero/atlassian-confluence.svg)](https://hub.docker.com/r/techzero/atlassian-confluence/) [![Pulls on Docker Hub](https://img.shields.io/docker/pulls/techzero/atlassian-confluence.svg)](https://hub.docker.com/r/techzero/atlassian-confluence/)

# Supported tags and respective `Dockerfile` links

- [`7.8.1`, `7.8`, `7`, `latest`](https://github.com/VantStark/docker-atlassian-confluence/blob/main/7.8.1/Dockerfile)

# Atlassian Confluence in a Docker container

This is a containerized installation of Atlassian Confluence with Docker, and it's a match made in heaven for us all to enjoy. The aim of this image is to keep the installation as straight forward as possible, but with a few Docker related twists.

## Get started

To quickly get started running a Confluence instance, use the following command:

```bash
docker run --name confluence \
    -d \
    -v /path/to/confluence:/var/atlassian/confluence \
    -e TZ=<timezone> \
    -e X_PROXY_NAME="example.com" \
    -e X_PROXY_PORT="8090" \
    -e X_PROXY_SCHEME="https" \
    -p 8090:8090 \
    techzero/atlassian-confluence:latest
```

Then simply navigate your preferred browser to `http://[dockerhost]:8090` and finish the configuration.

## Configuration

You can configure a small set of things by supplying the following environment variables

| Environment Variable | Description                                                                                      |
| -------------------- | ------------------------------------------------------------------------------------------------ |
| X_PROXY_NAME         | Sets the Tomcat Connectors `ProxyName` attribute                                                 |
| X_PROXY_PORT         | Sets the Tomcat Connectors `ProxyPort` attribute                                                 |
| X_PROXY_SCHEME       | If set to `https` the Tomcat Connectors `secure=true` and `redirectPort` equal to `X_PROXY_PORT` |
| X_PATH               | Sets the Tomcat connectors `path` attribute                                                      |

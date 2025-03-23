# Portfolio Website

Build with [alshedivat/al-folio](https://github.com/alshedivat/al-folio).

## Quick Start - Run Locally

Follow [Local setup using Docker (Recommended)](https://github.com/alshedivat/al-folio/blob/main/INSTALL.md#local-setup-using-docker-recommended).

For MacOS, recommend installing [Docker Desktop](https://www.docker.com/products/docker-desktop/) through [brew](https://formulae.brew.sh/cask/docker):
```
brew install --cask docker
```

Pull latest images for all services defined in [docker-compose.yml](./docker-compose.yml)
```
docker compose pull
```

Now to run the website:
```
docker compose up
```
and if error happens due to cached container, try:
```
docker compose up --build
```
If all runs successfully, the website should be running at http://localhost:8080

## Issues

See [ISSUES](./ISSUES.md)

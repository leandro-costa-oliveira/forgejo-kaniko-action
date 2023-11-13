# Kaniko Action

Build OCI images using Kaniko, with the Dockerfile contents provided directly as an action input.

## Usage

Example:

```yaml
jobs:
  cowsay:
    runs-on: docker
    steps:
      - uses: https://git.kabelsalat.ch/s3lph/forgejo-kaniko-action@v1
        with:
          dockerfile: |
            FROM debian:latest
            RUN apt update && apt install --yes cowsay
          image: docker.example.org/example/cowsay:latest
          registry: docker.example.org
          username: ${{ secrets.REGISTRY_USERNAME }}
          password: ${{ secrets.REGISTRY_PASSWORD }}
```

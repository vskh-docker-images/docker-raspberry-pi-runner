# docker-raspberry-pi-runner

Raspberry Pi runner image based on official Debian with Raspberry Pi tooling (`raspi-utils`) preinstalled and refreshed at build time.

Can be used as the last source image of a multistage docker build.

The Dockerfile intentionally runs `apt-get upgrade` during image build so published images include the latest available security and package updates.

## Published image

- Registry: `ghcr.io`
- Image: `ghcr.io/<owner>/docker-raspberry-pi-runner`
- Target architectures: `linux/arm/v7`, `linux/arm64`

## Build locally

```bash
docker buildx build \
	--platform linux/arm/v7,linux/arm64 \
	-t ghcr.io/<owner>/docker-raspberry-pi-runner:dev \
	.
```

## Publish manually

```bash
docker buildx build \
	--platform linux/arm/v7,linux/arm64 \
	-t ghcr.io/<owner>/docker-raspberry-pi-runner:latest \
	--push \
	.
```

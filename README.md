# Teledock
<img src="https://github.com/MrMarble/teledock/raw/master/assets/teledcock.png" width="180">

![Lint](https://github.com/MrMarble/teledock/workflows/Lint/badge.svg?branch=master&event=push)
![GitHub go.mod Go version](https://img.shields.io/github/go-mod/go-version/mrmarble/teledock)
![Docker Image Version (latest semver)](https://img.shields.io/docker/v/mrmarble/teledock?sort=semver)

**Teledock**: A simple telegram bot that allows a telegram's user to control a docker service.

## Features

- [x] List containers
- [x] Start / Stop containers
- [x] Inspect containers
- [ ] See logs
- [ ] Create container
- [ ] List images
- [ ] Run command inside container

## Build

```bash
go build
```

## Running it

### Requirements

- [Docker](https://docker.com) (Obiously)

### Configuration environmet variables

- `TELEDOCK_TOKEN`: Telegram token. See https://core.telegram.org/bots
- `TELEDOCK_SUPERADMINS`: Comma separated list of Telegram user ids, only users listed here will have access to the bot.

## Docker

To simplify the management of the bot there is a [Docker image](https://hub.docker.com/r/mrmarble/teledock) ready to use. You'll only need to mount the docker socket as a volume and set the environment variables ([see how](https://docs.docker.com/engine/reference/commandline/run/#set-environment-variables--e---env---env-file)). Example:
```bash
docker pull mrmarble/teledock # Only needed the first time or to update
docker run -v /var/run/docker.sock:/var/run/docker.sock --name teledock --env-file=config.env mrmarble/teledock
```

## Suggestions / Contribution

I made teledock because I need it but if you want to use it and there's something missing or not quite right, feel free to create a issue or a pull request if you know how to fix it yourself


## License

This project is licensed under the GPL 3.0 License. See the [LICENSE](LICENSE)
file for details.
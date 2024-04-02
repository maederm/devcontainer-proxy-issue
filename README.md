# vscode devcontainer issue behind proxy when using compose

Minimal repo to reproduce vscode devcontainer issue.

Press F1 and run "Dev Containers: Rebuild Without Cache and Reopen in Container" on "Python 3 docker-compose" -> doesn't work and shows `ERROR: Feature "Poetry (via pipx)" (ghcr.io/devcontainers-contrib/features/poetry) failed to install`

<details>
<summary>Show more logs</summary>

```log
[2024-04-02T17:00:08.968Z] Dev Containers 0.348.0 in VS Code 1.87.2 (863d2581ecda6849923a2118d93a088b0745d9d6).
[2024-04-02T17:00:08.968Z] Start: Resolving Remote
[2024-04-02T17:00:08.970Z] Setting up container for folder or workspace: /Volumes/development/github/devcontainer-proxy-issue
[2024-04-02T17:00:08.970Z] Host: unix:///Users/username/.lima/docker/sock/docker.sock
[2024-04-02T17:00:08.974Z] Start: Check Docker is running
[2024-04-02T17:00:08.974Z] Start: Run: docker version
[2024-04-02T17:00:08.992Z] Client: Docker Engine - Community
[2024-04-02T17:00:08.992Z]  Version:           26.0.0
 API version:       1.45
 Go version:        go1.22.1
 Git commit:        2ae903e86c
 Built:             Wed Mar 20 15:10:03 2024
 OS/Arch:           darwin/arm64
 Context:           default

Server: Docker Engine - Community
 Engine:
  Version:          26.0.0
  API version:      1.45 (minimum version 1.24)
  Go version:       go1.21.8
  Git commit:       8b79278
  Built:            Wed Mar 20 15:18:14 2024
  OS/Arch:          linux/arm64
  Experimental:     false
 containerd:
  Version:          1.6.28
  GitCommit:        ae07eda36dd25f8a1b98dfbf587313b99c0190bb
 runc:
  Version:          1.1.12
  GitCommit:        v1.1.12-0-g51d5e94
 docker-init:
  Version:          0.19.0
  GitCommit:        de40ad0
 rootlesskit:
  Version:          2.0.2
  ApiVersion:       1.1.1
  NetworkDriver:    slirp4netns
  PortDriver:       builtin
  StateDir:         /run/user/501/dockerd-rootless
 slirp4netns:
  Version:          1.0.1
  GitCommit:        6a7b16babc95b6a3056b33fb45b74a6f62262dd4
[2024-04-02T17:00:08.992Z] Stop (18 ms): Run: docker version
[2024-04-02T17:00:08.992Z] Stop (18 ms): Check Docker is running
[2024-04-02T17:00:08.993Z] Start: Run: docker volume ls -q
[2024-04-02T17:00:09.004Z] Stop (11 ms): Run: docker volume ls -q
[2024-04-02T17:00:09.004Z] Start: Run: docker inspect --type container 24c21eaebbebece2795a0598028853482a267cddb6241c5b451c0e3b2c53e508
[2024-04-02T17:00:09.014Z] Stop (10 ms): Run: docker inspect --type container 24c21eaebbebece2795a0598028853482a267cddb6241c5b451c0e3b2c53e508
[2024-04-02T17:00:09.014Z] Start: Run: docker ps -q -a --filter label=vsch.local.folder=/Volumes/development/github/devcontainer-proxy-issue --filter label=vsch.quality=stable
[2024-04-02T17:00:09.024Z] Stop (10 ms): Run: docker ps -q -a --filter label=vsch.local.folder=/Volumes/development/github/devcontainer-proxy-issue --filter label=vsch.quality=stable
[2024-04-02T17:00:09.024Z] Start: Run: docker ps -q -a --filter label=devcontainer.local_folder=/Volumes/development/github/devcontainer-proxy-issue --filter label=devcontainer.config_file=/Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json
[2024-04-02T17:00:09.034Z] Stop (10 ms): Run: docker ps -q -a --filter label=devcontainer.local_folder=/Volumes/development/github/devcontainer-proxy-issue --filter label=devcontainer.config_file=/Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json
[2024-04-02T17:00:09.034Z] Start: Run: docker ps -q -a --filter label=devcontainer.local_folder=/Volumes/development/github/devcontainer-proxy-issue
[2024-04-02T17:00:09.044Z] Stop (10 ms): Run: docker ps -q -a --filter label=devcontainer.local_folder=/Volumes/development/github/devcontainer-proxy-issue
[2024-04-02T17:00:09.044Z] Start: Run: docker ps -q -a --filter label=devcontainer.local_folder=/Volumes/development/github/devcontainer-proxy-issue
[2024-04-02T17:00:09.053Z] Stop (9 ms): Run: docker ps -q -a --filter label=devcontainer.local_folder=/Volumes/development/github/devcontainer-proxy-issue
[2024-04-02T17:00:09.067Z] ProxyResolver#loadSystemCertificates count
[2024-04-02T17:00:09.068Z] ProxyResolver#loadSystemCertificates count filtered
[2024-04-02T17:00:09.069Z] Start: Run: /Applications/Visual Studio Code.app/Contents/Frameworks/Code Helper (Plugin).app/Contents/MacOS/Code Helper (Plugin) /Users/username/.vscode/extensions/ms-vscode-remote.remote-containers-0.348.0/dist/spec-node/devContainersSpecCLI.js read-configuration --workspace-folder /Volumes/development/github/devcontainer-proxy-issue --id-label devcontainer.local_folder=/Volumes/development/github/devcontainer-proxy-issue --id-label devcontainer.config_file=/Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json --log-level trace --log-format json --config /Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json --mount-workspace-git-root
[2024-04-02T17:00:09.223Z] @devcontainers/cli 0.56.2. Node.js v18.17.1. darwin 23.4.0 arm64.
[2024-04-02T17:00:09.223Z] Start: Run: docker ps -q -a --filter label=devcontainer.local_folder=/Volumes/development/github/devcontainer-proxy-issue --filter label=devcontainer.config_file=/Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json
[2024-04-02T17:00:09.235Z] Stop (12 ms): Run: docker ps -q -a --filter label=devcontainer.local_folder=/Volumes/development/github/devcontainer-proxy-issue --filter label=devcontainer.config_file=/Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json
[2024-04-02T17:00:09.238Z] Stop (169 ms): Run: /Applications/Visual Studio Code.app/Contents/Frameworks/Code Helper (Plugin).app/Contents/MacOS/Code Helper (Plugin) /Users/username/.vscode/extensions/ms-vscode-remote.remote-containers-0.348.0/dist/spec-node/devContainersSpecCLI.js read-configuration --workspace-folder /Volumes/development/github/devcontainer-proxy-issue --id-label devcontainer.local_folder=/Volumes/development/github/devcontainer-proxy-issue --id-label devcontainer.config_file=/Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json --log-level trace --log-format json --config /Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json --mount-workspace-git-root
[2024-04-02T17:00:09.238Z] Start: Run: /Applications/Visual Studio Code.app/Contents/Frameworks/Code Helper (Plugin).app/Contents/MacOS/Code Helper (Plugin) /Users/username/.vscode/extensions/ms-vscode-remote.remote-containers-0.348.0/dist/spec-node/devContainersSpecCLI.js up --user-data-folder /Users/username/Library/Application Support/Code/User/globalStorage/ms-vscode-remote.remote-containers/data --container-session-data-folder /tmp/devcontainers-600bd9d6-0db0-457a-b63f-6bc40ef223f91712077208642 --workspace-folder /Volumes/development/github/devcontainer-proxy-issue --workspace-mount-consistency cached --id-label devcontainer.local_folder=/Volumes/development/github/devcontainer-proxy-issue --id-label devcontainer.config_file=/Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json --log-level trace --log-format json --config /Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json --default-user-env-probe loginInteractiveShell --build-no-cache --mount type=volume,source=vscode,target=/vscode,external=true --skip-post-create --update-remote-user-uid-default on --mount-workspace-git-root
[2024-04-02T17:00:09.390Z] @devcontainers/cli 0.56.2. Node.js v18.17.1. darwin 23.4.0 arm64.
[2024-04-02T17:00:09.390Z] Start: Run: docker buildx version
[2024-04-02T17:00:09.430Z] Stop (40 ms): Run: docker buildx version
[2024-04-02T17:00:09.430Z] github.com/docker/buildx v0.13.1 Homebrew
[2024-04-02T17:00:09.430Z] 
[2024-04-02T17:00:09.430Z] Start: Resolving Remote
[2024-04-02T17:00:09.432Z] Start: Run: docker-compose version --short
[2024-04-02T17:00:09.447Z] Stop (15 ms): Run: docker-compose version --short
[2024-04-02T17:00:09.447Z] Docker Compose version: 2.21.0
[2024-04-02T17:00:09.447Z] Start: Run: docker ps -q -a --filter label=com.docker.compose.project=compose --filter label=com.docker.compose.service=devcontainer
[2024-04-02T17:00:09.458Z] Stop (11 ms): Run: docker ps -q -a --filter label=com.docker.compose.project=compose --filter label=com.docker.compose.service=devcontainer
[2024-04-02T17:00:09.458Z] Start: Run: docker-compose -f /Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/docker-compose.yml --profile * config
[2024-04-02T17:00:09.475Z] Stop (17 ms): Run: docker-compose -f /Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/docker-compose.yml --profile * config
[2024-04-02T17:00:09.475Z] name: compose
services:
  devcontainer:
    command:
    - sleep
    - infinity
    image: mcr.microsoft.com/devcontainers/python:1-3.12-bullseye
    networks:
      default: null
    volumes:
    - type: bind
      source: /Volumes/development/github/devcontainer-proxy-issue/.devcontainer
      target: /workspace
      bind:
        create_host_path: true
networks:
  default:
    name: compose_default
[2024-04-02T17:00:09.476Z] Start: Run: docker events --format {{json .}} --filter event=start
[2024-04-02T17:00:09.477Z] PersistedPath=/Users/username/Library/Application Support/Code/User/globalStorage/ms-vscode-remote.remote-containers/data, ContainerHasLabels=false
[2024-04-02T17:00:09.478Z] Start: Run: docker-compose -f /Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/docker-compose.yml --profile * config
[2024-04-02T17:00:09.494Z] Stop (16 ms): Run: docker-compose -f /Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/docker-compose.yml --profile * config
[2024-04-02T17:00:09.494Z] name: compose
services:
  devcontainer:
    command:
    - sleep
    - infinity
    image: mcr.microsoft.com/devcontainers/python:1-3.12-bullseye
    networks:
      default: null
    volumes:
    - type: bind
      source: /Volumes/development/github/devcontainer-proxy-issue/.devcontainer
      target: /workspace
      bind:
        create_host_path: true
networks:
  default:
    name: compose_default
[2024-04-02T17:00:09.495Z] Start: Run: docker inspect --type image mcr.microsoft.com/devcontainers/python:1-3.12-bullseye
[2024-04-02T17:00:09.507Z] Stop (12 ms): Run: docker inspect --type image mcr.microsoft.com/devcontainers/python:1-3.12-bullseye
[2024-04-02T17:00:09.507Z] workspace root: /Volumes/development/github/devcontainer-proxy-issue
[2024-04-02T17:00:09.507Z] configPath: /Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json
[2024-04-02T17:00:09.508Z] --- Processing User Features ----
[2024-04-02T17:00:09.508Z] [* user-provided] ghcr.io/devcontainers-contrib/features/poetry:2
[2024-04-02T17:00:09.508Z] Resolving Feature dependencies for 'ghcr.io/devcontainers-contrib/features/poetry:2'...
[2024-04-02T17:00:09.508Z] * Processing feature: ghcr.io/devcontainers-contrib/features/poetry:2
[2024-04-02T17:00:09.508Z] > input: ghcr.io/devcontainers-contrib/features/poetry:2
[2024-04-02T17:00:09.508Z] >
[2024-04-02T17:00:09.508Z] > resource: ghcr.io/devcontainers-contrib/features/poetry
[2024-04-02T17:00:09.508Z] > id: poetry
[2024-04-02T17:00:09.508Z] > owner: devcontainers-contrib
[2024-04-02T17:00:09.508Z] > namespace: devcontainers-contrib/features
[2024-04-02T17:00:09.508Z] > registry: ghcr.io
[2024-04-02T17:00:09.508Z] > path: devcontainers-contrib/features/poetry
[2024-04-02T17:00:09.508Z] >
[2024-04-02T17:00:09.508Z] > version: 2
[2024-04-02T17:00:09.508Z] > tag?: 2
[2024-04-02T17:00:09.508Z] > digest?: undefined
[2024-04-02T17:00:09.508Z] manifest url: https://ghcr.io/v2/devcontainers-contrib/features/poetry/manifests/2
[2024-04-02T17:00:09.509Z] Loading 13 extra certificates from /var/folders/ls/147svv294kg08fjk2czrl5wc0000gn/T/vsch/certificates-eca1697b584a430608034f30b5e5f8a622250144ea3a78ada212f7feb74d698b.pem.
[2024-04-02T17:00:09.771Z] [httpOci] Attempting to authenticate via 'Bearer' auth.
[2024-04-02T17:00:09.772Z] [httpOci] Invoking credsStore credential helper 'osxkeychain'
[2024-04-02T17:00:09.772Z] Start: Run: docker-credential-osxkeychain get
[2024-04-02T17:00:09.794Z] Stop (22 ms): Run: docker-credential-osxkeychain get
[2024-04-02T17:00:09.794Z] [httpOci] Failed to query for 'ghcr.io' credential from 'docker-credential-osxkeychain': [object Object]
[2024-04-02T17:00:09.794Z] [httpOci] No authentication credentials found for registry 'ghcr.io' via docker config or credential helper.
[2024-04-02T17:00:09.794Z] [httpOci] No authentication credentials found for registry 'ghcr.io'. Accessing anonymously.
[2024-04-02T17:00:09.794Z] [httpOci] Attempting to fetch bearer token from:  https://ghcr.io/token?service=ghcr.io&scope=repository:devcontainers-contrib/features/poetry:pull
[2024-04-02T17:00:10.351Z] [httpOci] 200 on reattempt after auth: https://ghcr.io/v2/devcontainers-contrib/features/poetry/manifests/2
[2024-04-02T17:00:10.351Z] > input: ghcr.io/devcontainers-contrib/features/poetry:2
[2024-04-02T17:00:10.351Z] >
[2024-04-02T17:00:10.351Z] > resource: ghcr.io/devcontainers-contrib/features/poetry
[2024-04-02T17:00:10.351Z] > id: poetry
[2024-04-02T17:00:10.351Z] > owner: devcontainers-contrib
[2024-04-02T17:00:10.351Z] > namespace: devcontainers-contrib/features
[2024-04-02T17:00:10.351Z] > registry: ghcr.io
[2024-04-02T17:00:10.351Z] > path: devcontainers-contrib/features/poetry
[2024-04-02T17:00:10.351Z] >
[2024-04-02T17:00:10.351Z] > version: 2
[2024-04-02T17:00:10.351Z] > tag?: 2
[2024-04-02T17:00:10.351Z] > digest?: undefined
[2024-04-02T17:00:10.353Z] * Processing feature: ghcr.io/devcontainers-contrib/features/pipx-package
[2024-04-02T17:00:10.353Z] > input: ghcr.io/devcontainers-contrib/features/pipx-package
[2024-04-02T17:00:10.353Z] >
[2024-04-02T17:00:10.353Z] > resource: ghcr.io/devcontainers-contrib/features/pipx-package
[2024-04-02T17:00:10.353Z] > id: pipx-package
[2024-04-02T17:00:10.353Z] > owner: devcontainers-contrib
[2024-04-02T17:00:10.353Z] > namespace: devcontainers-contrib/features
[2024-04-02T17:00:10.353Z] > registry: ghcr.io
[2024-04-02T17:00:10.353Z] > path: devcontainers-contrib/features/pipx-package
[2024-04-02T17:00:10.353Z] >
[2024-04-02T17:00:10.353Z] > version: latest
[2024-04-02T17:00:10.353Z] > tag?: latest
[2024-04-02T17:00:10.353Z] > digest?: undefined
[2024-04-02T17:00:10.353Z] manifest url: https://ghcr.io/v2/devcontainers-contrib/features/pipx-package/manifests/latest
[2024-04-02T17:00:10.353Z] [httpOci] Applying cachedAuthHeader for registry ghcr.io...
[2024-04-02T17:00:10.540Z] [httpOci] 200 (Cached): https://ghcr.io/v2/devcontainers-contrib/features/pipx-package/manifests/latest
[2024-04-02T17:00:10.540Z] > input: ghcr.io/devcontainers-contrib/features/pipx-package
[2024-04-02T17:00:10.540Z] >
[2024-04-02T17:00:10.540Z] > resource: ghcr.io/devcontainers-contrib/features/pipx-package
[2024-04-02T17:00:10.540Z] > id: pipx-package
[2024-04-02T17:00:10.540Z] > owner: devcontainers-contrib
[2024-04-02T17:00:10.540Z] > namespace: devcontainers-contrib/features
[2024-04-02T17:00:10.540Z] > registry: ghcr.io
[2024-04-02T17:00:10.540Z] > path: devcontainers-contrib/features/pipx-package
[2024-04-02T17:00:10.540Z] >
[2024-04-02T17:00:10.540Z] > version: latest
[2024-04-02T17:00:10.540Z] > tag?: latest
[2024-04-02T17:00:10.540Z] > digest?: undefined
[2024-04-02T17:00:10.541Z] * Processing feature: ghcr.io/devcontainers/features/python
[2024-04-02T17:00:10.541Z] > input: ghcr.io/devcontainers/features/python
[2024-04-02T17:00:10.541Z] >
[2024-04-02T17:00:10.541Z] > resource: ghcr.io/devcontainers/features/python
[2024-04-02T17:00:10.541Z] > id: python
[2024-04-02T17:00:10.541Z] > owner: devcontainers
[2024-04-02T17:00:10.541Z] > namespace: devcontainers/features
[2024-04-02T17:00:10.541Z] > registry: ghcr.io
[2024-04-02T17:00:10.541Z] > path: devcontainers/features/python
[2024-04-02T17:00:10.541Z] >
[2024-04-02T17:00:10.541Z] > version: latest
[2024-04-02T17:00:10.541Z] > tag?: latest
[2024-04-02T17:00:10.541Z] > digest?: undefined
[2024-04-02T17:00:10.541Z] manifest url: https://ghcr.io/v2/devcontainers/features/python/manifests/latest
[2024-04-02T17:00:10.541Z] [httpOci] Applying cachedAuthHeader for registry ghcr.io...
[2024-04-02T17:00:10.763Z] [httpOci] 200 (Cached): https://ghcr.io/v2/devcontainers/features/python/manifests/latest
[2024-04-02T17:00:10.763Z] > input: ghcr.io/devcontainers/features/python
[2024-04-02T17:00:10.763Z] >
[2024-04-02T17:00:10.763Z] > resource: ghcr.io/devcontainers/features/python
[2024-04-02T17:00:10.763Z] > id: python
[2024-04-02T17:00:10.763Z] > owner: devcontainers
[2024-04-02T17:00:10.763Z] > namespace: devcontainers/features
[2024-04-02T17:00:10.763Z] > registry: ghcr.io
[2024-04-02T17:00:10.763Z] > path: devcontainers/features/python
[2024-04-02T17:00:10.763Z] >
[2024-04-02T17:00:10.763Z] > version: latest
[2024-04-02T17:00:10.763Z] > tag?: latest
[2024-04-02T17:00:10.763Z] > digest?: undefined
[2024-04-02T17:00:10.764Z] [* resolved worklist] ghcr.io/devcontainers-contrib/features/poetry:2
[2024-04-02T17:00:10.764Z] [
  {
    "type": "user-provided",
    "userFeatureId": "ghcr.io/devcontainers-contrib/features/poetry:2",
    "options": {},
    "dependsOn": [],
    "installsAfter": [
      {
        "type": "resolved",
        "userFeatureId": "ghcr.io/devcontainers-contrib/features/pipx-package",
        "options": {},
        "featureSet": {
          "sourceInformation": {
            "type": "oci",
            "manifest": {
              "schemaVersion": 2,
              "mediaType": "application/vnd.oci.image.manifest.v1+json",
              "config": {
                "mediaType": "application/vnd.devcontainers",
                "digest": "sha256:e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
                "size": 0
              },
              "layers": [
                {
                  "mediaType": "application/vnd.devcontainers.layer.v1+tar",
                  "digest": "sha256:6112eae98139dd734d71f82adbd04126a5d98f54af0b3d1231484756faf905a8",
                  "size": 10752,
                  "annotations": {
                    "org.opencontainers.image.title": "devcontainer-feature-pipx-package.tgz"
                  }
                }
              ],
              "annotations": {
                "dev.containers.metadata": "{\"name\":\"Pipx package\",\"id\":\"pipx-package\",\"version\":\"1.1.7\",\"description\":\"Installs a pipx package.\",\"documentationURL\":\"http://github.com/devcontainers-contrib/features/tree/main/src/pipx-package\",\"installsAfter\":[\"ghcr.io/devcontainers/features/python\"],\"options\":{\"package\":{\"type\":\"string\",\"proposals\":[\"black\"],\"default\":\"\",\"description\":\"Select the pipx package to install.\"},\"version\":{\"type\":\"string\",\"proposals\":[\"latest\"],\"default\":\"latest\",\"description\":\"Select the version of the pipx package to install.\"},\"injections\":{\"type\":\"string\",\"proposals\":[\"pylint pytest\"],\"default\":\"\",\"description\":\"Space delimitered list of python packages to inject into the main package env\"},\"includeDeps\":{\"default\":false,\"description\":\"Include apps of dependent packages\",\"type\":\"boolean\"},\"interpreter\":{\"type\":\"string\",\"proposals\":[\"python3\"],\"default\":\"\",\"description\":\"Force python interpreter to be use (must already exists on the container). If none selected (the default) then python3 will be used (and will be installed in case it does not exists)\"}}}",
                "com.github.package.type": "devcontainer_feature"
              }
            },
            "manifestDigest": "sha256:4d08e51f0594c984c3d930bf8ab4c7d2650b675c429fc259b08cfaf167831642",
            "featureRef": {
              "id": "pipx-package",
              "owner": "devcontainers-contrib",
              "namespace": "devcontainers-contrib/features",
              "registry": "ghcr.io",
              "resource": "ghcr.io/devcontainers-contrib/features/pipx-package",
              "path": "devcontainers-contrib/features/pipx-package",
              "version": "latest",
              "tag": "latest"
            },
            "userFeatureId": "ghcr.io/devcontainers-contrib/features/pipx-package",
            "userFeatureIdWithoutVersion": "ghcr.io/devcontainers-contrib/features/pipx-package"
          },
          "features": [
            {
              "id": "pipx-package",
              "included": true,
              "value": {}
            }
          ]
        },
        "dependsOn": [],
        "installsAfter": [],
        "roundPriority": 0,
        "featureIdAliases": [
          "pipx-package"
        ]
      },
      {
        "type": "resolved",
        "userFeatureId": "ghcr.io/devcontainers/features/python",
        "options": {},
        "featureSet": {
          "sourceInformation": {
            "type": "oci",
            "manifest": {
              "schemaVersion": 2,
              "mediaType": "application/vnd.oci.image.manifest.v1+json",
              "config": {
                "mediaType": "application/vnd.devcontainers",
                "digest": "sha256:e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
                "size": 0
              },
              "layers": [
                {
                  "mediaType": "application/vnd.devcontainers.layer.v1+tar",
                  "digest": "sha256:4fc585a6d2d12dbc85da1b8466cd76ef12c2ef4c2d952bf466edc369b8daaf6c",
                  "size": 44032,
                  "annotations": {
                    "org.opencontainers.image.title": "devcontainer-feature-python.tgz"
                  }
                }
              ],
              "annotations": {
                "dev.containers.metadata": "{\"id\":\"python\",\"version\":\"1.4.2\",\"name\":\"Python\",\"documentationURL\":\"https://github.com/devcontainers/features/tree/main/src/python\",\"description\":\"Installs the provided version of Python, as well as PIPX, and other common Python utilities.  JupyterLab is conditionally installed with the python feature. Note: May require source code compilation.\",\"options\":{\"version\":{\"type\":\"string\",\"proposals\":[\"latest\",\"os-provided\",\"none\",\"3.12\",\"3.11\",\"3.10\",\"3.9\",\"3.8\",\"3.7\",\"3.6\"],\"default\":\"os-provided\",\"description\":\"Select a Python version to install.\"},\"installTools\":{\"type\":\"boolean\",\"default\":true,\"description\":\"Flag indicating whether or not to install the tools specified via the 'toolsToInstall' option. Default is 'true'.\"},\"toolsToInstall\":{\"type\":\"string\",\"default\":\"flake8,autopep8,black,yapf,mypy,pydocstyle,pycodestyle,bandit,pipenv,virtualenv,pytest,pylint\",\"description\":\"Comma-separated list of tools to install when 'installTools' is true. Defaults to a set of common Python tools like pylint.\"},\"optimize\":{\"type\":\"boolean\",\"default\":false,\"description\":\"Optimize Python for performance when compiled (slow)\"},\"enableShared\":{\"type\":\"boolean\",\"default\":false,\"description\":\"Enable building a shared Python library\"},\"installPath\":{\"type\":\"string\",\"default\":\"/usr/local/python\",\"description\":\"The path where python will be installed.\"},\"installJupyterlab\":{\"type\":\"boolean\",\"default\":false,\"description\":\"Install JupyterLab, a web-based interactive development environment for notebooks\"},\"configureJupyterlabAllowOrigin\":{\"type\":\"string\",\"default\":\"\",\"description\":\"Configure JupyterLab to accept HTTP requests from the specified origin\"},\"httpProxy\":{\"type\":\"string\",\"default\":\"\",\"description\":\"Connect to GPG keyservers using a proxy for fetching source code signatures by configuring this option\"}},\"containerEnv\":{\"PYTHON_PATH\":\"/usr/local/python/current\",\"PIPX_HOME\":\"/usr/local/py-utils\",\"PIPX_BIN_DIR\":\"/usr/local/py-utils/bin\",\"PATH\":\"/usr/local/python/current/bin:/usr/local/py-utils/bin:${PATH}\"},\"customizations\":{\"vscode\":{\"extensions\":[\"ms-python.python\",\"ms-python.vscode-pylance\"],\"settings\":{\"python.defaultInterpreterPath\":\"/usr/local/python/current/bin/python\"}}},\"installsAfter\":[\"ghcr.io/devcontainers/features/common-utils\",\"ghcr.io/devcontainers/features/oryx\"]}",
                "com.github.package.type": "devcontainer_feature"
              }
            },
            "manifestDigest": "sha256:bf021f1800543f08bf029c449a3f25341be782b620802befa1f8e6ee51cf6cf6",
            "featureRef": {
              "id": "python",
              "owner": "devcontainers",
              "namespace": "devcontainers/features",
              "registry": "ghcr.io",
              "resource": "ghcr.io/devcontainers/features/python",
              "path": "devcontainers/features/python",
              "version": "latest",
              "tag": "latest"
            },
            "userFeatureId": "ghcr.io/devcontainers/features/python",
            "userFeatureIdWithoutVersion": "ghcr.io/devcontainers/features/python"
          },
          "features": [
            {
              "id": "python",
              "included": true,
              "value": {}
            }
          ]
        },
        "dependsOn": [],
        "installsAfter": [],
        "roundPriority": 0,
        "featureIdAliases": [
          "python"
        ]
      }
    ],
    "roundPriority": 0,
    "featureSet": {
      "sourceInformation": {
        "type": "oci",
        "manifest": {
          "schemaVersion": 2,
          "mediaType": "application/vnd.oci.image.manifest.v1+json",
          "config": {
            "mediaType": "application/vnd.devcontainers",
            "digest": "sha256:e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
            "size": 0
          },
          "layers": [
            {
              "mediaType": "application/vnd.devcontainers.layer.v1+tar",
              "digest": "sha256:45db22cf19ed39eb84a3b22bdbb6119e28e30cd62475fe4de762fcc92a7bd21c",
              "size": 11776,
              "annotations": {
                "org.opencontainers.image.title": "devcontainer-feature-poetry.tgz"
              }
            }
          ],
          "annotations": {
            "dev.containers.metadata": "{\"id\":\"poetry\",\"version\":\"2.0.17\",\"name\":\"Poetry (via pipx)\",\"documentationURL\":\"http://github.com/devcontainers-contrib/features/tree/main/src/poetry\",\"description\":\"Poetry is a tool for dependency management and packaging in Python.\",\"options\":{\"version\":{\"default\":\"latest\",\"description\":\"Select the version to install.\",\"proposals\":[\"latest\"],\"type\":\"string\"}},\"installsAfter\":[\"ghcr.io/devcontainers-contrib/features/pipx-package\",\"ghcr.io/devcontainers/features/python\"]}",
            "com.github.package.type": "devcontainer_feature"
          }
        },
        "manifestDigest": "sha256:85ad0e0190682104214e5ae4faa2bf8c2e181802567c01db0ef2dc9a70790f32",
        "featureRef": {
          "id": "poetry",
          "owner": "devcontainers-contrib",
          "namespace": "devcontainers-contrib/features",
          "registry": "ghcr.io",
          "resource": "ghcr.io/devcontainers-contrib/features/poetry",
          "path": "devcontainers-contrib/features/poetry",
          "version": "2",
          "tag": "2"
        },
        "userFeatureId": "ghcr.io/devcontainers-contrib/features/poetry:2",
        "userFeatureIdWithoutVersion": "ghcr.io/devcontainers-contrib/features/poetry"
      },
      "features": [
        {
          "id": "poetry",
          "included": true,
          "value": {},
          "version": "2.0.17",
          "name": "Poetry (via pipx)",
          "documentationURL": "http://github.com/devcontainers-contrib/features/tree/main/src/poetry",
          "description": "Poetry is a tool for dependency management and packaging in Python.",
          "options": {
            "version": {
              "default": "latest",
              "description": "Select the version to install.",
              "proposals": [
                "latest"
              ],
              "type": "string"
            }
          },
          "installsAfter": [
            "ghcr.io/devcontainers-contrib/features/pipx-package",
            "ghcr.io/devcontainers/features/python"
          ]
        }
      ]
    },
    "featureIdAliases": [
      "poetry"
    ]
  }
]
[2024-04-02T17:00:10.764Z] [raw worklist]: ghcr.io/devcontainers-contrib/features/poetry:2
[2024-04-02T17:00:10.764Z] Soft-dependency 'ghcr.io/devcontainers/features/python' is not required.  Removing from installation order...
[2024-04-02T17:00:10.764Z] Soft-dependency 'ghcr.io/devcontainers-contrib/features/pipx-package' is not required.  Removing from installation order...
[2024-04-02T17:00:10.764Z] [worklist-without-dangling-soft-deps]: ghcr.io/devcontainers-contrib/features/poetry:2
[2024-04-02T17:00:10.764Z] Starting round-based Feature install order calculation from worklist...
[2024-04-02T17:00:10.764Z] 
[round] ghcr.io/devcontainers-contrib/features/poetry:2
[2024-04-02T17:00:10.764Z] [round-candidates] ghcr.io/devcontainers-contrib/features/poetry:2 (0)
[2024-04-02T17:00:10.764Z] [round-after-filter-priority] (maxPriority=0) ghcr.io/devcontainers-contrib/features/poetry:2 (0)
[2024-04-02T17:00:10.764Z] [round-after-comparesTo] ghcr.io/devcontainers-contrib/features/poetry:2
[2024-04-02T17:00:10.764Z] --- Fetching User Features ----
[2024-04-02T17:00:10.764Z] * Fetching feature: poetry_0_oci
[2024-04-02T17:00:10.764Z] Fetching from OCI
[2024-04-02T17:00:10.765Z] blob url: https://ghcr.io/v2/devcontainers-contrib/features/poetry/blobs/sha256:45db22cf19ed39eb84a3b22bdbb6119e28e30cd62475fe4de762fcc92a7bd21c
[2024-04-02T17:00:10.766Z] [httpOci] Applying cachedAuthHeader for registry ghcr.io...
[2024-04-02T17:00:11.187Z] [httpOci] 200 (Cached): https://ghcr.io/v2/devcontainers-contrib/features/poetry/blobs/sha256:45db22cf19ed39eb84a3b22bdbb6119e28e30cd62475fe4de762fcc92a7bd21c
[2024-04-02T17:00:11.192Z] ./ : Directory
[2024-04-02T17:00:11.193Z] ./README.md : File
[2024-04-02T17:00:11.193Z] ./devcontainer-feature.json : File
[2024-04-02T17:00:11.193Z] ./install.sh : File
[2024-04-02T17:00:11.193Z] ./library_scripts.sh : File
[2024-04-02T17:00:11.195Z] Files extracted from blob: ./README.md, ./devcontainer-feature.json, ./install.sh, ./library_scripts.sh
[2024-04-02T17:00:11.196Z] * Fetched feature: poetry_0_oci version 2.0.17
[2024-04-02T17:00:11.199Z] Docker Compose override file for building image:
version: '3.7'

services:
  devcontainer:
    image: vsc-devcontainer-proxy-issue-466f7ef84248efa8e47f2390676738f526c9ec87b58fb3460e9db6a6b2d64bf4
    build:
      dockerfile: /var/folders/ls/147svv294kg08fjk2czrl5wc0000gn/T/devcontainercli/container-features/0.56.2-1712077209507/Dockerfile-with-features
      context: /Users/username/Library/Application Support/Code/User/globalStorage/ms-vscode-remote.remote-containers/data/empty-folder
      args:
        - BUILDKIT_INLINE_CACHE=1
        - _DEV_CONTAINERS_BASE_IMAGE=dev_container_auto_added_stage_label
        - _DEV_CONTAINERS_IMAGE_USER=root
        - _DEV_CONTAINERS_FEATURE_CONTENT_SOURCE=dev_container_feature_content_temp
      additional_contexts:
        - dev_containers_feature_content_source=/var/folders/ls/147svv294kg08fjk2czrl5wc0000gn/T/devcontainercli/container-features/0.56.2-1712077209507

[2024-04-02T17:00:11.200Z] Start: Run: docker-compose --project-name compose -f /Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/docker-compose.yml -f /Users/username/Library/Application Support/Code/User/globalStorage/ms-vscode-remote.remote-containers/data/docker-compose/docker-compose.devcontainer.build-1712077211199.yml build --no-cache
[2024-04-02T17:00:11.410Z] [+] Building 0.0s (0/1)                                          docker:default
[2024-04-02T17:00:11.561Z] [+] Building 0.2s (1/2)                                          docker:default
 => [devcontainer internal] load build definition from Dockerfile-with-fe  0.0s
 => => transferring dockerfile: 2.41kB                                     0.0s
[2024-04-02T17:00:11.561Z]  => [devcontainer] resolve image config for docker-image://docker.io/dock  0.1s
[2024-04-02T17:00:11.713Z] [+] Building 0.3s (1/2)                                          docker:default
 => [devcontainer internal] load build definition from Dockerfile-with-fe  0.0s
 => => transferring dockerfile: 2.41kB                                     0.0s
 => [devcontainer] resolve image config for docker-image://docker.io/dock  0.3s
[2024-04-02T17:00:11.864Z] [+] Building 0.5s (1/2)                                          docker:default
 => [devcontainer internal] load build definition from Dockerfile-with-fe  0.0s
 => => transferring dockerfile: 2.41kB                                     0.0s
 => [devcontainer] resolve image config for docker-image://docker.io/dock  0.4s
[2024-04-02T17:00:11.864Z] 
[2024-04-02T17:00:11.988Z] [+] Building 0.6s (6/14)                                         docker:default
 => [devcontainer internal] load build definition from Dockerfile-with-fe  0.0s
 => => transferring dockerfile: 2.41kB                                     0.0s
 => [devcontainer] resolve image config for docker-image://docker.io/dock  0.5s
 => CACHED [devcontainer] docker-image://docker.io/docker/dockerfile:1.4@  0.0s
 => [devcontainer internal] load .dockerignore                             0.0s
[2024-04-02T17:00:11.988Z]  => => transferring context: 2B                                            0.0s
 => [devcontainer internal] load metadata for mcr.microsoft.com/devcontai  0.0s
 => [devcontainer context dev_containers_feature_content_source] load .do  0.0s
 => => transferring dev_containers_feature_content_source: 2B              0.0s
[2024-04-02T17:00:12.122Z] [+] Building 0.7s (10/14)                                        docker:default
 => [devcontainer internal] load build definition from Dockerfile-with-fe  0.0s
 => => transferring dockerfile: 2.41kB                                     0.0s
 => [devcontainer] resolve image config for docker-image://docker.io/dock  0.5s
[2024-04-02T17:00:12.122Z]  => CACHED [devcontainer] docker-image://docker.io/docker/dockerfile:1.4@  0.0s
 => [devcontainer internal] load .dockerignore                             0.0s
 => => transferring context: 2B                                            0.0s
 => [devcontainer internal] load metadata for mcr.microsoft.com/devcontai  0.0s
 => [devcontainer context dev_containers_feature_content_source] load .do  0.0s
 => => transferring dev_containers_feature_content_source: 2B              0.0s
 => CACHED [devcontainer dev_container_auto_added_stage_label 1/1] FROM m  0.0s
 => [devcontainer context dev_containers_feature_content_source] load fro  0.0s
 => => transferring dev_containers_feature_content_source: 15.70kB         0.0s
 => [devcontainer dev_containers_target_stage 1/4] RUN mkdir -p /tmp/dev-  0.1s
 => [devcontainer dev_containers_feature_content_normalize 1/2] COPY --fr  0.0s
 => [devcontainer dev_containers_f
[2024-04-02T17:00:12.122Z] eature_content_normalize 2/2] RUN chmod  0.1s
[2024-04-02T17:00:12.233Z] [+] Building 0.8s (11/14)                                        docker:default
 => [devcontainer internal] load build definition from Dockerfile-with-fe  0.0s
 => => transferring dockerfile: 2.41kB                                     0.0s
[2024-04-02T17:00:12.233Z]  => [devcontainer] resolve image config for docker-image://docker.io/dock  0.5s
 => CACHED [devcontainer] docker-image://docker.io/docker/dockerfile:1.4@  0.0s
 => [devcontainer internal] load .dockerignore                             0.0s
 => => transferring context: 2B                                            0.0s
 => [devcontainer internal] load metadata for mcr.microsoft.com/devcontai  0.0s
 => [devcontainer context dev_containers_feature_content_source] load .do  0.0s
 => => transferring dev_containers_feature_content_source: 2B              0.0s
 => CACHED [devcontainer dev_container_auto_added_stage_label 1/1] FROM m  0.0s
 => [devcontainer context dev_containers_feature_content_source] load fro  0.0s
 => => transferring dev_containers_feature_content_source: 15.70kB         0.0s
 => [devcontainer dev_containers_target_stage 1/4] RUN mkdir -p /tmp/dev-  0.1s
 => [devcontainer dev_contain
[2024-04-02T17:00:12.233Z] ers_feature_content_normalize 1/2] COPY --fr  0.0s
 => [devcontainer dev_containers_feature_content_normalize 2/2] RUN chmod  0.2s
[2024-04-02T17:00:12.384Z] [+] Building 1.0s (12/14)                                        docker:default
 => [devcontainer internal] load build definition from Dockerfile-with-fe  0.0s
 => => transferring dockerfile: 2.41kB                                     0.0s
[2024-04-02T17:00:12.384Z]  => [devcontainer] resolve image config for docker-image://docker.io/dock  0.5s
 => CACHED [devcontainer] docker-image://docker.io/docker/dockerfile:1.4@  0.0s
 => [devcontainer internal] load .dockerignore                             0.0s
 => => transferring context: 2B                                            0.0s
 => [devcontainer internal] load metadata for mcr.microsoft.com/devcontai  0.0s
 => [devcontainer context dev_containers_feature_content_source] load .do  0.0s
 => => transferring dev_containers_feature_content_source: 2B              0.0s
 => CACHED [devcontainer dev_container_auto_added_stage_label 1/1] FROM m  0.0s
 => [devcontainer context dev_containers_feature_content_source] load fro  0.0s
 => => transferring dev_containers_feature_content_source: 15.70kB         0.0s
 => [devcontainer dev_containers_target_stage 1/4] RUN mkdir -p /tmp/dev-  0.1s
 => [devcontainer dev_contain
[2024-04-02T17:00:12.384Z] ers_feature_content_normalize 1/2] COPY --fr  0.0s
 => [devcontainer dev_containers_feature_content_normalize 2/2] RUN chmod  0.2s
 => [devcontainer dev_containers_target_stage 2/4] COPY --from=dev_contai  0.0s
 => [devcontainer dev_containers_target_stage 3/4] RUN echo "_CONTAINER_U  0.1s
[2024-04-02T17:00:12.534Z] [+] Building 1.1s (13/14)                                        docker:default
[2024-04-02T17:00:12.534Z]  => [devcontainer internal] load build definition from Dockerfile-with-fe  0.0s
 => => transferring dockerfile: 2.41kB                                     0.0s
 => [devcontainer] resolve image config for docker-image://docker.io/dock  0.5s
 => CACHED [devcontainer] docker-image://docker.io/docker/dockerfile:1.4@  0.0s
 => [devcontainer internal] load .dockerignore                             0.0s
 => => transferring context: 2B                                            0.0s
 => [devcontainer internal] load metadata for mcr.microsoft.com/devcontai  0.0s
 => [devcontainer context dev_containers_feature_content_source] load .do  0.0s
 => => transferring dev_containers_feature_content_source: 2B              0.0s
 => CACHED [devcontainer dev_container_auto_added_stage_label 1/1] FROM m  0.0s
 => [devcontainer context dev_containers_feature_content_source] load fro  0.0s
 => => transferring dev_conta
[2024-04-02T17:00:12.534Z] iners_feature_content_source: 15.70kB         0.0s
 => [devcontainer dev_containers_target_stage 1/4] RUN mkdir -p /tmp/dev-  0.1s
 => [devcontainer dev_containers_feature_content_normalize 1/2] COPY --fr  0.0s
 => [devcontainer dev_containers_feature_content_normalize 2/2] RUN chmod  0.2s
 => [devcontainer dev_containers_target_stage 2/4] COPY --from=dev_contai  0.0s
 => [devcontainer dev_containers_target_stage 3/4] RUN echo "_CONTAINER_U  0.2s
 => [devcontainer dev_containers_target_stage 4/4] RUN --mount=type=bind,  0.1s
[2024-04-02T17:00:12.641Z] [+] Building 1.2s (14/14)                                        docker:default
 => [devcontainer internal] load build definition from Dockerfile-with-fe  0.0s
 => => transferring dockerfile: 2.41kB                                     0.0s
 => [devcontainer] resolve image config for docker-image://docker.io/dock  0.5s
 => CACHED [devcontainer] docker-image://docker.io/docker/dockerfile:1.4@  0.0s
 => [devcontainer internal] load .dockerignore                             0.0s
 => => transferring context: 2B                                            0.0s
 => [devcontainer internal] load metadata for mcr.microsoft.com/devcontai  0.0s
 => [devcontainer context dev_containers_feature_content_source] load .do  0.0s
 => => transferring dev_containers_feature_content_source: 2B              0.0s
 => CACHED [devcontainer dev_container_aut
[2024-04-02T17:00:12.641Z] o_added_stage_label 1/1] FROM m  0.0s
 => [devcontainer context dev_containers_feature_content_source] load fro  0.0s
 => => transferring dev_containers_feature_content_source: 15.70kB         0.0s
 => [devcontainer dev_containers_target_stage 1/4] RUN mkdir -p /tmp/dev-  0.1s
 => [devcontainer dev_containers_feature_content_normalize 1/2] COPY --fr  0.0s
 => [devcontainer dev_containers_feature_content_normalize 2/2] RUN chmod  0.2s
 => [devcontainer dev_containers_target_stage 2/4] COPY --from=dev_contai  0.0s
 => [devcontainer dev_containers_target_stage 3/4] RUN echo "_CONTAINER_U  0.2s
 => ERROR [devcontainer dev_containers_target_stage 4/4] RUN --mount=type  0.2s
[2024-04-02T17:00:12.653Z] [+] Building 1.2s (14/14) FINISHED                               docker:default
 => [devcontainer internal] load build definition from Dockerfile-with-fe  0.0s
 => => transferring dockerfile: 2.41kB                                     0.0s
 => [devcontainer] resolve image config for docker-image://docker.io/dock  0.5s
 => CACHED [devcontainer] docker-image://docker.io/docker/dockerfile:1.4@  0.0s
 => [devcontainer internal] load .dockerignore                             0.0s
 => => transferring context: 2B                                            0.0s
 => [devcontainer internal] load metadata for mcr.microsoft.com/devcontai  0.0s
 => [devcontainer context dev_containers_feature_content_source] load .do  0.0s
[2024-04-02T17:00:12.653Z]  => => transferring dev_containers_feature_content_source: 2B              0.0s
 => CACHED [devcontainer dev_container_auto_added_stage_label 1/1] FROM m  0.0s
 => [devcontainer context dev_containers_feature_content_source] load fro  0.0s
 => => transferring dev_containers_feature_content_source: 15.70kB         0.0s
 => [devcontainer dev_containers_target_stage 1/4] RUN mkdir -p /tmp/dev-  0.1s
 => [devcontainer dev_containers_feature_content_normalize 1/2] COPY --fr  0.0s
 => [devcontainer dev_containers_feature_content_normalize 2/2] RUN chmod  0.2s
 => [devcontainer dev_containers_target_stage 2/4] COPY --from=dev_contai  0.0s
 => [devcontainer dev_containers_target_stage 3/4] RUN echo "_CONTAINER_U  0.2s
 => ERROR [devcontainer dev_containers_target_stage 4/4] RUN --mount=type  0.2s
------
 > [devcontainer dev_containers_target_stage 4/4] RUN --mount=type=bind,from=dev_containers_feature_content_so
[2024-04-02T17:00:12.653Z] urce,source=poetry_0,target=/tmp/build-features-src/poetry_0     cp -ar /tmp/build-features-src/poetry_0 /tmp/dev-container-features  && chmod -R 0755 /tmp/dev-container-features/poetry_0  && cd /tmp/dev-container-features/poetry_0  && chmod +x ./devcontainer-features-install.sh  && ./devcontainer-features-install.sh  && rm -rf /tmp/dev-container-features/poetry_0:
0.142 ===========================================================================
0.142 Feature       : Poetry (via pipx)
0.142 Description   : Poetry is a tool for dependency management and packaging in Python.
0.142 Id            : ghcr.io/devcontainers-contrib/features/poetry
0.142 Version       : 2.0.17
0.142 Documentation : http://github.com/devcontainers-contrib/features/tree/main/src/poetry
0.142 Options       :
0.142     VERSION="latest"
0.142 ===========================================================================
0.176 ERROR: Feature "Poetry (via pipx)" (ghcr.io/devcontainers-contrib/features/poetry) failed to install! Look a
[2024-04-02T17:00:12.653Z] t the documentation at http://github.com/devcontainers-contrib/features/tree/main/src/poetry for help troubleshooting this error.
------
[2024-04-02T17:00:12.654Z] failed to solve: process "/bin/sh -c cp -ar /tmp/build-features-src/poetry_0 /tmp/dev-container-features  && chmod -R 0755 /tmp/dev-container-features/poetry_0  && cd /tmp/dev-container-features/poetry_0  && chmod +x ./devcontainer-features-install.sh  && ./devcontainer-features-install.sh  && rm -rf /tmp/dev-container-features/poetry_0" did not complete successfully: exit code: 7
[2024-04-02T17:00:12.655Z] Stop (1455 ms): Run: docker-compose --project-name compose -f /Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/docker-compose.yml -f /Users/username/Library/Application Support/Code/User/globalStorage/ms-vscode-remote.remote-containers/data/docker-compose/docker-compose.devcontainer.build-1712077211199.yml build --no-cache
[2024-04-02T17:00:12.655Z] Error: Command failed: docker-compose --project-name compose -f /Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/docker-compose.yml -f /Users/username/Library/Application Support/Code/User/globalStorage/ms-vscode-remote.remote-containers/data/docker-compose/docker-compose.devcontainer.build-1712077211199.yml build --no-cache
[2024-04-02T17:00:12.655Z]     at G0 (/Users/username/.vscode/extensions/ms-vscode-remote.remote-containers-0.348.0/dist/spec-node/devContainersSpecCLI.js:429:525)
[2024-04-02T17:00:12.655Z]     at process.processTicksAndRejections (node:internal/process/task_queues:95:5)
[2024-04-02T17:00:12.655Z]     at async itA (/Users/username/.vscode/extensions/ms-vscode-remote.remote-containers-0.348.0/dist/spec-node/devContainersSpecCLI.js:429:2497)
[2024-04-02T17:00:12.655Z]     at async ttA (/Users/username/.vscode/extensions/ms-vscode-remote.remote-containers-0.348.0/dist/spec-node/devContainersSpecCLI.js:409:3170)
[2024-04-02T17:00:12.655Z]     at async StA (/Users/username/.vscode/extensions/ms-vscode-remote.remote-containers-0.348.0/dist/spec-node/devContainersSpecCLI.js:481:3833)
[2024-04-02T17:00:12.655Z]     at async ZC (/Users/username/.vscode/extensions/ms-vscode-remote.remote-containers-0.348.0/dist/spec-node/devContainersSpecCLI.js:481:4775)
[2024-04-02T17:00:12.656Z]     at async trA (/Users/username/.vscode/extensions/ms-vscode-remote.remote-containers-0.348.0/dist/spec-node/devContainersSpecCLI.js:614:11269)
[2024-04-02T17:00:12.656Z]     at async erA (/Users/username/.vscode/extensions/ms-vscode-remote.remote-containers-0.348.0/dist/spec-node/devContainersSpecCLI.js:614:11010)
[2024-04-02T17:00:12.658Z] Stop (3420 ms): Run: /Applications/Visual Studio Code.app/Contents/Frameworks/Code Helper (Plugin).app/Contents/MacOS/Code Helper (Plugin) /Users/username/.vscode/extensions/ms-vscode-remote.remote-containers-0.348.0/dist/spec-node/devContainersSpecCLI.js up --user-data-folder /Users/username/Library/Application Support/Code/User/globalStorage/ms-vscode-remote.remote-containers/data --container-session-data-folder /tmp/devcontainers-600bd9d6-0db0-457a-b63f-6bc40ef223f91712077208642 --workspace-folder /Volumes/development/github/devcontainer-proxy-issue --workspace-mount-consistency cached --id-label devcontainer.local_folder=/Volumes/development/github/devcontainer-proxy-issue --id-label devcontainer.config_file=/Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json --log-level trace --log-format json --config /Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json --default-user-env-probe loginInteractiveShell --build-no-cache --mount type=volume,source=vscode,target=/vscode,external=true --skip-post-create --update-remote-user-uid-default on --mount-workspace-git-root
[2024-04-02T17:00:12.658Z] Exit code 1
[2024-04-02T17:00:12.659Z] Command failed: /Applications/Visual Studio Code.app/Contents/Frameworks/Code Helper (Plugin).app/Contents/MacOS/Code Helper (Plugin) /Users/username/.vscode/extensions/ms-vscode-remote.remote-containers-0.348.0/dist/spec-node/devContainersSpecCLI.js up --user-data-folder /Users/username/Library/Application Support/Code/User/globalStorage/ms-vscode-remote.remote-containers/data --container-session-data-folder /tmp/devcontainers-600bd9d6-0db0-457a-b63f-6bc40ef223f91712077208642 --workspace-folder /Volumes/development/github/devcontainer-proxy-issue --workspace-mount-consistency cached --id-label devcontainer.local_folder=/Volumes/development/github/devcontainer-proxy-issue --id-label devcontainer.config_file=/Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json --log-level trace --log-format json --config /Volumes/development/github/devcontainer-proxy-issue/.devcontainer/compose/devcontainer.json --default-user-env-probe loginInteractiveShell --build-no-cache --mount type=volume,source=vscode,target=/vscode,external=true --skip-post-create --update-remote-user-uid-default on --mount-workspace-git-root
[2024-04-02T17:00:12.659Z] Exit code 1
```
</details>

Press F1 and run "Dev Containers: Rebuild Without Cache and Reopen in Container" on "Python 3 direct" and the container gets installed successfully.

When being connected directly to the internet without proxy both methods work.

## Environment

- MacOS Sonoma 14.4.1 on a MacBook Pro M2
- vscode 1.87.2
- Dev Containers v0.348.0
- Running docker 26.0.0 using lima 0.21.0
    - [Lima Template](https://github.com/lima-vm/lima/blob/master/examples/docker.yaml)
    - Root certificates including proxy are set using caCerts.files

### Networking

- Running behind an enterprise proxy using ssl interception
- Env http_proxy, https_proxy, HTTPS_PROXY, HTTP_PROXY and NO_PROXY are set in .zshrc
- Env no_proxy, NO_PROXY, https_proxy and http_proxy are set in lima docker vm.


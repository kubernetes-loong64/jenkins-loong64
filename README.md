# Jenkins for LoongArch64

<p align="center"><a href="README.md">English</a> | <a href="README-zh.md">中文</a></p>

<p align="center"><img src="https://img.shields.io/badge/Jenkins%20LoongArch64%20%E9%BE%99%E8%8A%AF%E6%9E%B6%E6%9E%84%E5%8F%91%E8%A1%8C%E7%89%88-blue?logo=jenkins&logoColor=white" alt="Jenkins LoongArch64 龙芯架构发行版"></p>

Prebuilt [Jenkins](https://www.jenkins.io/) Docker images for the **LoongArch64 (loong64)** architecture.

## Docker Images

Images are published to Docker Hub under [`kubernetesloong64/jenkins-loong64`](https://hub.docker.com/r/kubernetesloong64/jenkins-loong64).

- [![kubernetesloong64/jenkins-loong64:2.569-jdk21](https://img.shields.io/docker/v/kubernetesloong64/jenkins-loong64/2.569-jdk21?arch=loong64&logo=docker&label=kubernetesloong64%2Fjenkins-loong64)](https://hub.docker.com/r/kubernetesloong64/jenkins-loong64/tags)
- [![kubernetesloong64/jenkins-loong64:2.569-jdk25](https://img.shields.io/docker/v/kubernetesloong64/jenkins-loong64/2.569-jdk25?arch=loong64&logo=docker&label=kubernetesloong64%2Fjenkins-loong64)](https://hub.docker.com/r/kubernetesloong64/jenkins-loong64/tags)
- [![kubernetesloong64/jenkins-loong64:2.555.3-jdk21](https://img.shields.io/docker/v/kubernetesloong64/jenkins-loong64/2.555.3-jdk21?arch=loong64&logo=docker&label=kubernetesloong64%2Fjenkins-loong64)](https://hub.docker.com/r/kubernetesloong64/jenkins-loong64/tags)
- [![kubernetesloong64/jenkins-loong64:2.555.3-jdk25](https://img.shields.io/docker/v/kubernetesloong64/jenkins-loong64/2.555.3-jdk25?arch=loong64&logo=docker&label=kubernetesloong64%2Fjenkins-loong64)](https://hub.docker.com/r/kubernetesloong64/jenkins-loong64/tags)

### Pull Images

```shell
# Jenkins (debian 14)
docker pull kubernetesloong64/jenkins-loong64:2.569-jdk21
docker pull kubernetesloong64/jenkins-loong64:2.569-jdk25

# Jenkins LTS (debian 14)
docker pull kubernetesloong64/jenkins-loong64:2.555.3-jdk21
docker pull kubernetesloong64/jenkins-loong64:2.555.3-jdk25
```

### Usage

```shell
# Run Jenkins
docker run -d --name jenkins \
  -p 8080:8080 -p 50000:50000 \
  -v jenkins_home:/var/jenkins_home \
  kubernetesloong64/jenkins-loong64:2.569-jdk21

# Run Jenkins LTS
docker run -d --name jenkins \
  -p 8080:8080 -p 50000:50000 \
  -v jenkins_home:/var/jenkins_home \
  kubernetesloong64/jenkins-loong64:2.555.3-jdk21
```

After starting, get the initial admin password:

```shell
docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```

## Branch Naming

Push a branch named `loong64-<jenkins-version>` (e.g. `loong64-2.569`) to trigger a build.

## License

[Apache License 2.0](LICENSE)

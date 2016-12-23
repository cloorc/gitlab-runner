# GitLab runner

> See [https://github.com/soiff/gitlab-ci-multi-runner.git](https://github.com/soiff/gitlab-ci-multi-runner.git)

---

# Building

1. Clone project [https://github.com/soiff/gitlab-ci-multi-runner.git](https://github.com/soiff/gitlab-ci-multi-runner.git);
1. Building binaries: `make build-and-deploy-binary`;
1. Create working directory: `mkdir docker`;
1. Copy necessary scripts into working directory: `cp packaging/* docker/`;
1. Copy necessary binaries into working directory: `cp out/binaries/gitlab-ci-multi-runner docker/`;
1. Create soft link of `Dockerfile.amd64` to working directory: `ln -s Dockerfile.amd64 docker/`;
1. Change directory to working directory: `cd docker`;
1. Building docker image: `docker build soiff/gitlab-runner:latest -f Dockerfile.amd64 .`;
1. Pushing image to `https://docker.io`;

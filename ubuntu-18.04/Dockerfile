FROM pizzafactory0contorno/piatto:18.04-ubunutu@sha256:c8c3e15c0d98952f90ce02df17820a4453653a3c3763402d48dfb78ca682fd25

USER root
RUN apt-get update \
 && DEBIAN_FRONTEND=noninteractive apt-get install -y \
      apt-transport-https curl gnupg zip unzip git \
      openjdk-11-jdk-headless python3 python3-pip python3-distutils \
 && curl https://storage.googleapis.com/git-repo-downloads/repo | sed -e 's|env python|env python3|' > /usr/bin/repo \
 && chmod a+x /usr/bin/repo \
 && curl https://github.com/bazelbuild/bazelisk/releases/download/v${BAZELISK_VERSION}/bazelisk-linux-${TARGETARCH} > /usr/bin/bazel \
 && chmod a+x /usr/bin/bazel \
 && DEBIAN_FRONTEND=noninteractive apt-get full-upgrade -y \
 && apt-get clean && rm -rf /var/lib/apt/lists/*
USER user
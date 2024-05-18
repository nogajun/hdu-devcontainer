FROM debian:bookworm-slim

LABEL version="1.5"
LABEL maintainer="nogata@gm.himeji-du.ac.jp"
LABEL description="For web app development class. used from dev container on Visual studio code."

# 必要なパッケージをインストール
RUN apt-get -y update && apt-get -y full-upgrade && \
    apt-get -y install apt-utils locales sudo python3-all python3-pip python3-venv python-is-python3 python3-yaml flake8 python3-flake8 python3-flake8-builtins black python3-flake8-black python3-ipykernel bash-completion wget curl jq git task-japanese && \
    apt-get -y autoremove && apt-get -y clean && rm -rf /var/lib/apt/lists/*

# 日本語ロケール(ja_JP.UTF-8)を追加
ARG UID=1000
ARG GID=1000
ARG USER_NAME=docker
ARG USER_LOCALE=ja_JP.UTF-8
RUN sed -i -e "s/^# \(${USER_LOCALE}\)/\1/g" /etc/locale.gen && \
    echo "LANG=${USER_LOCALE}" > /etc/default/locale && \
    dpkg-reconfigure --frontend=noninteractive locales && \
    update-locale LANG=${USER_LOCALE} && \
    groupadd -g ${GID} ${USER_NAME} && \
    useradd -u ${UID} -g ${GID} -s /bin/bash -m ${USER_NAME} && \
    gpasswd -a ${USER_NAME} docker && \
    echo "${USER_NAME}  ALL=(ALL:ALL) NOPASSWD:ALL" > /etc/sudoers.d/${USER_NAME} && \
    chmod 440 /etc/sudoers.d/${USER_NAME} && \
    mkdir -p /etc/bash_completion.d/

# bash_completionにpipのオプション補完を追加 https://github.com/ekalinin/pip-bash-completion
COPY ./.devcontainer/pip /etc/bash_completion.d/

ENV LANG ${USER_LOCALE}
ENV LANGUAGE ja
ENV TZ Asia/Tokyo

USER ${UID}

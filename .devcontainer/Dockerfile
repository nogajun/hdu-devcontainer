FROM debian:bookworm

LABEL version="1.3"
LABEL maintainer="nogata@gm.himeji-du.ac.jp"
LABEL description="For web app creation class. used from dev container on Visual studio code."

# 必要なパッケージをインストール
RUN apt-get -y update && \
    apt-get -y full-upgrade && \
    apt-get -y install apt-utils locales sudo python3-all python3-pip python3-venv python-is-python3 python3-yaml python3-autopep8 bash-completion wget curl jq git task-japanese

# 日本語ロケール(ja_JP.UTF-8)を追加
ARG USER_LOCALE=ja_JP.UTF-8
RUN sed -i -e "s/^# \(${USER_LOCALE}\)/\1/g" /etc/locale.gen && \
    echo "LANG=${USER_LOCALE}" > /etc/default/locale && \
    dpkg-reconfigure --frontend=noninteractive locales && \
    update-locale LANG=${USER_LOCALE}
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja

# bash_completionにpipのオプション補完を追加 https://github.com/ekalinin/pip-bash-completion
RUN mkdir -p /etc/bash_completion.d/
COPY pip /etc/bash_completion.d/

# dockerユーザーとグループを追加
ARG UID=1000
ARG GID=1000
RUN groupadd -g ${GID} docker && \
    useradd -u ${UID} -g ${GID} -s /bin/bash -m docker && \
    gpasswd -a docker docker

# dockerユーザーがsudoを使えるように設定
RUN echo "docker  ALL=(ALL:ALL) NOPASSWD:ALL" > /etc/sudoers.d/docker && \
    chmod 440 /etc/sudoers.d/docker

USER ${UID}

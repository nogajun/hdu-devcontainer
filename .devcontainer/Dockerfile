FROM debian:bookworm-slim

LABEL version="1.7"
LABEL maintainer="nogata@gm.himeji-du.ac.jp"
LABEL description="For web app development class. used from dev container on Visual studio code."

# 1. Python関連パッケージ追加
# 2. 日本語ロケール(ja_JP.UTF-8)を追加
# 3. ユーザー追加
# 4. sudoが利用できるように/etc/sudoers.d/以下にユーザーを追加
# 5. aptのキャッシュ削除
ARG UID=1000
ARG USERNAME=vscode
ARG LOCALE=ja_JP.UTF-8

RUN apt-get -y update && apt-get -y dist-upgrade && \
  apt-get -y --no-install-recommends install apt-utils locales sudo python3-all python3-pip python3-venv python-is-python3 python3-yaml flake8 python3-flake8 python3-flake8-builtins black python3-flake8-black python3-ipykernel bash-completion wget curl jq git task-japanese && \
  sed -i -e "s/^# \(${LOCALE}\)/\1/g" /etc/locale.gen && \
  echo "LANG=${LOCALE}" > /etc/default/locale && \
  dpkg-reconfigure --frontend=noninteractive locales && \
  update-locale LANG=${LOCALE} && \
  useradd --uid ${UID} -s /bin/bash -m -U ${USERNAME} && \
  echo "${USERNAME}  ALL=(ALL:ALL) NOPASSWD:ALL" > /etc/sudoers.d/${USERNAME} && \
  chmod 440 /etc/sudoers.d/${USERNAME} && \
  apt-get -y autoremove && apt-get -y clean && rm -rf /var/lib/apt/lists/*

# bash_completionにpipのオプション補完を追加 https://github.com/ekalinin/pip-bash-completion
COPY pip /etc/bash_completion.d/

# 環境変数
ENV LANG=${LOCALE}
ENV LANGUAGE=ja
ENV TZ=Asia/Tokyo

USER ${UID}

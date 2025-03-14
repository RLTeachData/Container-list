FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

# 更新系統並安裝 Python 3.9、pip 和必要的工具
RUN apt update && apt install sudo curl wget\
    && sudo apt install -y software-properties-common \
    && sudo add-apt-repository -y ppa:deadsnakes/ppa \
    && sudo apt update \
    && apt install -y python3.9 \
    python3-pip \
    git \
    curl \
    && rm -rf /var/lib/apt/lists/*

RUN ln -sf /usr/bin/python3.9 /usr/bin/python \
    && ln -sf /usr/bin/pip3 /usr/bin/pip

RUN pip install --no-cache-dir jupyter

WORKDIR /workspace

CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]

EXPOSE 8888
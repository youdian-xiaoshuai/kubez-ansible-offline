FROM ubuntu:18.04

WORKDIR /kubez-ansible
COPY . .

RUN apt-get update
RUN apt install -y git python-pip ansible sshpass && \
    pip install /kubez-ansible && \
    apt remove -y git python-pip && \
    apt autoremove -y && \
    apt-get clean

COPY docker/start.sh /usr/local/bin/pixiu_start

CMD ["pixiu_start"]

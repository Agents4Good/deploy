FROM python:3.11-slim

ARG BRANCH
ARG GITUSER
ARG GITPASSWORD
ARG REPO_NAME=EurecaAI

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y --no-install-recommends \
        build-essential \
        git \
        curl \
        htop \
        vim \
        wget \
        net-tools \
        iputils-ping \
        ffmpeg \
        ca-certificates && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /root

RUN git config --global credential.helper 'store --file=/root/.git-credentials'

RUN echo "https://$GITUSER:$GITPASSWORD@dev.sti.ufcg.edu.br" > /root/.git-credentials && \
    git clone https://github.com/Agents4Good/${REPO_NAME}.git

WORKDIR /root/${REPO_NAME}

RUN git checkout ${BRANCH} && \
    python -m venv venv && \
    . venv/bin/activate && \
    pip install --upgrade pip && \
    pip install -r requirements.txt

RUN touch .env

COPY .env .env

CMD ["./venv/bin/python", "-m", "flask_app.app"]
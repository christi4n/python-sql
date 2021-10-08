FROM python:3.9.7

WORKDIR /usr/src/app

RUN  apt-get update && apt-get install -y \ 
    libsasl2-dev \
    python-dev \
    libldap2-dev \
    libssl-dev

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY . .
COPY scripts/ /scripts/

RUN groupadd -r python && useradd -r -g python python

RUN pwd \
    ls /usr/src/app/scripts/hello.py -la

USER python

RUN cd scripts

ENTRYPOINT ["tail", "-f", "/dev/null"]
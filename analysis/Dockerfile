FROM python:2.7.12
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update \
  && apt-get install -y mysql-server --no-install-recommends \
  && apt-get clean \
  && pip install PyMySQL \
  && pip install MySQL-python \
  && pip install twarc \
  && pip install sqlalchemy \
  && pip install textblob \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN mkdir /trump && pip install -U flask-cors

WORKDIR /trump

ADD . /trump

ENV FLASK_APP server.pyyy

#ENTRYPOINT ["flask"]
#CMD ["run"]

# This Dockerfile doesn't need to have an entrypoint and a command
# as Bitbucket Pipelines will overwrite it with a bash script.

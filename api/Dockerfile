FROM  pantsbuild/centos7:latest

USER root

WORKDIR /usr/src/app

COPY bin .

RUN chmod -R +x *

RUN yum install epel-release -y \
  && yum update -y \
  && yum install jq -y

RUN ./build-support/generate_constraints.sh

# RUN ./pants fmt lint check ::

RUN ./pants run cli/:pex_binary

CMD []

FROM ubuntu:latest

RUN rm -rf /etc/apt/sources.list
ADD sources.list /etc/apt/
RUN apt-get update ; apt-get -y install fortune
ADD fortuneloop.sh /bin/fortuneloop.sh
RUN chmod +x /bin/fortuneloop.sh


ENTRYPOINT /bin/fortuneloop.sh


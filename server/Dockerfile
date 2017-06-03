FROM phusion/baseimage:0.9.22

ENV TERM xterm

RUN apt-get update -qq && apt-get install -y build-essential

RUN echo "deb https://download.gocd.io /" > /etc/apt/sources.list.d/gocd.list
RUN curl https://download.gocd.io/GOCD-GPG-KEY.asc | apt-key add -
RUN apt-get update
RUN apt-get install -y openjdk-8-jre-headless
RUN apt-get install -y go-server

ADD files/etc/my_init.d/01_gocd_server.sh /etc/my_init.d/01_gocd_server.sh
RUN chmod 0755 /etc/my_init.d/01_gocd_server.sh

CMD ["/sbin/my_init"]
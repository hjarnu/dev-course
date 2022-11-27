FROM ubuntu:20.04

ENV TZ="Asia/Almaty"
RUN \
  apt-get update && \
  apt-get -y upgrade && \
  apt install -y tzdata && \
  apt-get install -y build-essential openssl libssl-dev zlib1g-dev && \
  apt-get install -y software-properties-common && \
  apt-get install -y byobu curl git htop man vim wget openssl libffi-dev &&\
  rm -rf /var/lib/apt/lists/*
RUN \
  wget https://cache.ruby-lang.org/pub/ruby/2.7/ruby-2.7.2.tar.bz2 &&\
  tar -xf ruby-2.7.2.tar.bz2

RUN cd ruby-2.7.2 && ./configure --prefix=/my/ruby/dir && \
 make && make install


ENV HOME /root
ENV PATH="${PATH}:/my/ruby/dir/bin/"

CMD ["bash"]
FROM alibaba-cloud-linux-3-registry.cn-hangzhou.cr.aliyuncs.com/alinux3/alinux3:latest

RUN yum update -y 
RUN yum install -y gcc gcc-c++ make cmake curl rpm-build
RUN yum install -y automake gcc-c++ git libcurl-devel libxml2-devel fuse-devel openssl-devel \
  && curl -SL "https://cache.ruby-china.com/pub/ruby/ruby-2.6.5.tar.gz" -o /opt/ruby-2.6.5.tar.gz\
  && cd /opt/ && tar zxvf ruby-2.6.5.tar.gz && cd ruby-2.6.5 \
  && ./configure && make -j10 && make install \
  && gem sources -a http://mirrors.aliyun.com/rubygems/ -r https://rubygems.org/ \
  && gem install dotenv -v 2.8.1 \
  && gem install fpm

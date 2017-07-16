FROM centos

RUN rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
RUN echo $'[kibana-5.x]\n\
name=Kibana repository for 5.x packages\n\
baseurl=https://artifacts.elastic.co/packages/5.x/yum\n\
gpgcheck=1\n\
gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch\n\
enabled=1\n\
autorefresh=1\n\
type=rpm-md' > /etc/yum.repos.d/elastic.repo

RUN yum install -y kibana-5.3.0-1

WORKDIR /usr/share/kibana
RUN curl -OL https://github.com/fbaligand/kibana/releases/download/v5.3.0-csv-export/csv-export-patch.tar.gz
RUN tar -xzvf ./csv-export-patch.tar.gz
RUN chown kibana:kibana -R ./src
RUN rm -rf ./optimize/*

#RUN echo 'nameserver 192.168.1.77' >> /etc/resolv.conf

#USER kibana
#WORKDIR /usr/share/kibana

CMD /usr/share/kibana/bin/kibana
#CMD /usr/local/bin/kibana

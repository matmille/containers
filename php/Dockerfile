FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install php git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/php
RUN mv /build/languages/php/hello.php /app/hello.php
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove git 
CMD ["php","/app/hello.php"]

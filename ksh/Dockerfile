FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install ksh git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/ksh
RUN mv /build/languages/ksh/hello.sh /app/hello.sh
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove git 
CMD ["ksh","/app/hello.sh"]

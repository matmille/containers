FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
RUN yum -y install gnucobol git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/cobol
RUN cobc -o hello -x hello.cob
RUN mv /build/languages/cobol/hello /app/hello
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove gnucobol git
CMD ["/app/hello"]

FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install gcc git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/assembly
RUN gcc -o hello hello.s
RUN mv /build/languages/assembly/hello /app/hello
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove gcc git
CMD ["/app/hello"]

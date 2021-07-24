FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install gcc-gnat git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/ada
RUN gnatmake hello.adb
RUN gnatclean -c hello.adb
RUN mv /build/languages/ada/hello /app/hello
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove gcc-gnat git
CMD ["/app/hello"]

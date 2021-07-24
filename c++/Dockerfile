FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install gcc-c++ git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/c++
RUN g++ -o hello -Bstatic hello.cpp
RUN mv /build/languages/c++/hello /app/hello
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove gcc-c++ git
CMD ["/app/hello"]

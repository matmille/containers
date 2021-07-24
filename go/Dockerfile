FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
RUN yum -y install golang git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/go
RUN go build -ldflags="-extldflags=-static" -o hello hello.go
RUN mv /build/languages/go/hello /app/hello
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove golang git
CMD ["/app/hello"]

FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/awk
RUN mv /build/languages/awk/hello.awk /app/hello.awk
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove git 
CMD ["awk","-f","/app/hello.awk"]

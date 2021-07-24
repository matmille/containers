FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install tcsh git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/csh
RUN mv /build/languages/csh/hello.csh /app/hello.csh
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove git 
CMD ["csh","/app/hello.csh"]

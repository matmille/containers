FROM registry.access.redhat.com/ubi7/ubi
RUN yum-config-manager --enable rhel-server-rhscl-7-rpms
RUN yum -y install rh-scala210 rh-scala210-runtime git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/scala
RUN scl enable rh-scala210 "scalac hello.scala"
RUN mv /build/languages/scala/hello* /app
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove git 
CMD ["scl","enable","rh-scala210","scala hello"]

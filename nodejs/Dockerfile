FROM registry.access.redhat.com/ubi7/ubi
RUN yum-config-manager --enable rhel-server-rhscl-7-rpms
RUN yum -y install rh-nodejs14 rh-nodejs14-runtime git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/nodejs
RUN mv /build/languages/nodejs/hello.js /app/hello.js
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove git 
CMD ["scl","enable","rh-nodejs14","node /app/hello.js"]

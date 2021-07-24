FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install lua git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/lua
RUN mv /build/languages/lua/hello.lua /app/hello.lua
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove git 
CMD ["lua","/app/hello.lua"]

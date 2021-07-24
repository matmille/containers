FROM registry.access.redhat.com/ubi7/ubi
RUN yum-config-manager --enable rhel-7-server-dotnet-rpms
RUN yum -y install rh-dotnet50 git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/dotnet
RUN scl enable rh-dotnet50 "dotnet build -o bin hello" \
    && mv /build/languages/dotnet/bin/* /app/ \
    && rm -rf /build
WORKDIR /app
RUN yum -y remove rh-dotnet git 
CMD ["/app/hello"]

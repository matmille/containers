FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install tcl git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/tcl
RUN mv /build/languages/tcl/hello.tcl /app/hello.tcl
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove git 
CMD ["tclsh","/app/hello.tcl"]

FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install gcc gcc-gfortran git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/fortran
RUN gfortran hello.f90 -o hello
RUN mv /build/languages/fortran/hello /app/hello
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove gcc gcc-gfortran git
CMD ["/app/hello"]

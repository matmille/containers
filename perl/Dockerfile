FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install perl git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/perl
RUN mv /build/languages/perl/hello.pl /app/hello.pl
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove git 
CMD ["perl","/app/hello.pl"]

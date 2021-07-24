FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install python git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/python
RUN mv /build/languages/python/hello.py /app/hello.py
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove git 
CMD ["python","/app/hello.py"]

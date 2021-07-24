FROM registry.access.redhat.com/ubi7/ubi
RUN yum -y install java-11-openjdk java-11-openjdk-devel git && yum clean all
RUN mkdir -p /app /build
WORKDIR /build
RUN git clone https://github.com/demoinghelloworld/languages.git
WORKDIR /build/languages/java
RUN javac hello.java
RUN mv /build/languages/java/hello.class /app/hello.class
WORKDIR /app
RUN rm -rf /build
RUN yum -y remove java-11-openjdk-devel git
CMD ["java","hello"]

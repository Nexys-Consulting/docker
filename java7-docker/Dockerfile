#
# Ubuntu + Java
#

# Pull base image
FROM snouhaud/baseimage:v1

# Install java-7
RUN add-apt-repository -y ppa:webupd8team/java
RUN apt-get update
RUN echo debconf shared/accepted-oracle-license-v1-1 select true | debconf-set-selections
RUN echo debconf shared/accepted-oracle-license-v1-1 seen true | debconf-set-selections
# Install it and after that remove no longer needed files to save 150mb
RUN apt-get install -y oracle-java7-installer && rm /var/cache/oracle-jdk7-installer/*.tar.gz /usr/lib/jvm/java-7-oracle/src.zip

# Fix java-7-oracle cacerts
RUN apt-get install -y ca-certificates-java
RUN rm /usr/lib/jvm/java-7-oracle/jre/lib/security/cacerts; ln -s /etc/ssl/certs/java/cacerts /usr/lib/jvm/java-7-oracle/jre/lib/security/cacerts
#
# Ubuntu Dockerfile
#

# Pull base image
FROM phusion/baseimage:0.9.10

MAINTAINER Stéphane NOUHAUD "https://github.com/snouhaud"

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install htop -y
# Remove it
RUN rm -f /etc/ssh/ssh_host_*

# Add support for add-apt-repository command, commonly used certificates and wget
RUN apt-get install -y software-properties-common ca-certificates wget

# Add ca-certifcates
#RUN mkdir -p /usr/local/share/ca-certificates
#ADD cacert.org /usr/local/share/ca-certificates/cacert.org
#RUN update-ca-certificates

# Enable installation of authorized keys through github
ADD add_github_keys.sh /etc/my_init.d/add_github_keys.sh

# Expose /var/log as volume
VOLUME /var/log
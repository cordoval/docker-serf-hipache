# Pull base image.
FROM dockerfile/ubuntu

# Install Nginx.
RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:nginx/stable
RUN apt-get update
RUN apt-get install -y nginx
RUN echo "\ndaemon off;" >> /etc/nginx/nginx.conf

# Attach volumes.
VOLUME /etc/nginx/sites-enabled
VOLUME /var/log/nginx
VOLUME /usr/share/nginx/html

# Set working directory.
WORKDIR /etc/nginx

# Expose ports.
EXPOSE 80

# add the startup script
ADD ./startup.sh /opt/startup.sh

# Define default command.
CMD ["/bin/bash", "/opt/startup.sh"]

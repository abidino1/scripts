FROM alpine:latest

# Install apache2 without saving a copy of the package list locally
RUN apk add --no-cache apache2

# Configure Apache to run in the foreground using 'sed' the stream editor to set 'ServerName' to 'Localhost' in Apache2 configuration
# file /etc/apache2/httpd.conf
RUN sed -i 's/#ServerName www.example.com:80/ServerName localhost/' /etc/apache2/httpd.conf

# This appends the printed string to the end of the apache2 configuration file
RUN echo "PidFile /run/apache2/httpd.pid" >> /etc/apache2/httpd.conf

# Expose port 80
EXPOSE 80

# Start Apache
CMD ["httpd", "-D", "FOREGROUND"]

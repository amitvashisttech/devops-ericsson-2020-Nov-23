# Base Image 
FROM ubuntu:16.04

# Initalize the Apt Repo. 
RUN apt-get update 

# Install Apache2 Packages 
RUN apt-get install apache2 -y

# Expose the service
EXPOSE 80
EXPOSE 3306

# Create a Custome Web Page
COPY info.html /var/www/html/info.html

# Bring up the Service
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"] 
 

FROM httpd:latest
RUN apt update -y
RUN apt install  -y unzip zip
# Just my name who wrote this file
MAINTAINER SaravAK (aksarav@middlewareinventory.com)

# to Copy a file named httpd.conf from present working directory to the /usr/local/apache2/conf inside the container
# I have taken the Standard httpd.conf file and enabled the necassary modules and adding Support for an additional Directory
COPY httpd.conf /usr/local/apache2/conf/httpd.conf

# This is the Additional Directory where we are going to keep our Virtualhost configuraiton files
# You can use the image to create N number of different virtual hosts
RUN mkdir -p /usr/local/apache2/conf/sites/

#ADD http://fr2.rpmfind.net/linux/opensuse/tumbleweed/repo/oss/x86_64/ftp-0.17-694.31.x86_64.rpm /var/
#COPY html.zip /var/www/
#RUN unzip   /var/www/html.zip

# To tell docker to expose this port
EXPOSE 80

# The Base command, This command should be used to start the container
# Remember, A Container is a Process.As long as the base process (started by base cmd) is live the Container will be ALIVE.
CMD ["httpd", "-D", "FOREGROUND"]

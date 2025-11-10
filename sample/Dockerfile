FROM ubuntu:latest 
#base image used as ubuntu 

LABEL dev="shra"  
#keyvalue tags and labels 

#executed commands in the dockerfile
RUN apt-get update && \
    apt-get install apache2 unzip -y  && \
    rm /var/www/html/index.html 

#downloaded and add the zip file to the specified location
ADD https://www.creative-tim.com/product/soft-ui-dashboard  /var/www/html/soft-ui-dashboard.zip

#switched working directory to the specified location
WORKDIR /var/www/html  

#unzip the file and move the contents to the specified location
RUN unzip soft-ui-dashboard.zip && \
    mv soft-ui-dashboard/* /var/www/html/


#exposed port for the container
EXPOSE 80 

#command to run the apache server in foreground mode
#CMD ["httpd-foreground"]
CMD ["apache2ctl", "-D", "FOREGROUND"]









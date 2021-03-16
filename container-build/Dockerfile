# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

# Port
LABEL io.openshift.expose-services="8080:http"
RUN sed -i "s/Listen 80/Listen 8080/g" /etc/conf/httpd/httpd.conf
EXPOSE 8080

# Permissions
ENV MYDIRS="/var/log/www /var/run/httpd /var/logs/httpd"
RUN chown -R 1001:0 ${MYDIRS} &&\
	chmod -R g=u  ${MYDIRS} &&\
	chgrp -R 0  ${MYDIRS} 
USER 1001

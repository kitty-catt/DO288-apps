# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

LABEL io.openshift.expose-services="8080:http"

ENV DIRS="/var/log/httpd /var/run/httpd"

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf
RUN chown -R 1001:0 $DIRS &&\
    chgrp -R 0 $DIRS &&\
    chmod -R g=u $DIRS 

USER 1001
EXPOSE 8080

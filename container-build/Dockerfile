# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

LABEL io.openshift.expose-services="8080:http"

ENV MYDIRS="/var/log/httpd /var/run/httpd"

RUN chown -R 1001:0 $MYDIRS && \
    chgrp -R 0 $MYDIRS && \
    chmod -R g=u $MYDIRS

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf

USER 1001


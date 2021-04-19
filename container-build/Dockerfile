# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

# ports
LABEL io.openshift.expose-services="8080:http"
RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf
EXPOSE 8080

# permissions
ENV MYDIRS="/var/run/httpd /var/log/httpd"
RUN chown -R 1001:0 ${MYDIRS} && \
    chmod -R g=u ${MYDIRS} && \
    chgrp -R 0 ${MYDIRS}
USER 1001


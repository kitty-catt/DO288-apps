# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

# PORT
LABEL io.openshift.expose-services="8080/http"
RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf
EXPOSE 8080

# PRIVILEDGES
ENV MYDIR="/var/logs/httpd"
RUN chown -R 1001:0 ${MYDIR} &&\
    chmod -R g=u ${MYDIR} &&\
    chgrp -R 0 ${MYDIR}
USER 1001

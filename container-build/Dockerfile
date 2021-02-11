 FROM quay.io/redhattraining/httpd-parent

# 3 port jobs
LABEL io.openshift.expose-services="8080:http"
RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf
EXPOSE 8080

# 3 user jobs
ENV DIRS="/var/log/httpd /var/run/httpd"
RUN chown -R 1001:0 $DIRS &&\
    chgrp -R 0 $DIRS &&\
    chmod -R g=u $DIRS 
USER 1001

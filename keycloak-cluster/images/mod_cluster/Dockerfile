FROM karm/mod_cluster-master-dockerhub:latest
MAINTAINER Rafael T. C. Soares <rafaelcba@gmail.com>

# update packages and install the iproute utilities
RUN dnf -y update && dnf -y install iproute && dnf clean all

#coment the ServerName diretive to avoid issues with Docker environment
RUN sed -i 's/^ServerName/#ServerName/g' ${HTTPD_MC_BUILD_DIR}/conf/httpd.conf

COPY mod_cluster.conf ${HTTPD_MC_BUILD_DIR}/conf/extra/mod_cluster.conf
COPY docker-entrypoint.sh /
RUN chmod +x /docker-entrypoint.sh

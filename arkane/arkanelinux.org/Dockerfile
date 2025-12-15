FROM docker.io/debian:13 AS build
WORKDIR /build
RUN apt-get update && \
    apt-get install git -y && \
    git clone https://github.com/arkanelinux/arkanelinux.org.git

FROM docker.io/httpd:latest
COPY --from=build /build/arkanelinux.org/src/ /usr/local/apache2/htdocs/

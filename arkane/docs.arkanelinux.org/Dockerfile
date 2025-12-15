FROM docker.io/debian:13 AS build
WORKDIR /build
RUN apt-get update && \
    apt-get install git npm -y && \
		git clone https://github.com/arkanelinux/docs.arkanelinux.org.git && \
		cd docs.arkanelinux.org/docs && \
    npm install vitepress && \
    npm run docs:build

FROM docker.io/httpd:latest
COPY --from=build /build/docs.arkanelinux.org/docs/.vitepress/dist /usr/local/apache2/htdocs


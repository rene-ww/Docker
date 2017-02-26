FROM maxexcloo/nginx-php:latest
MAINTAINER Max Schaefer <max@excloo.com>
RUN apt-get update && apt-get install -y -o Dpkg::Options::="--force-confdef" -o Dpkg::Options::="--force-confold" php7.0-xml && apt-get clean all

WORKDIR /app
RUN git clone https://tt-rss.org/gitlab/fox/tt-rss.git && \
	cd tt-rss && rm -rf .git *.md *.pot */*/.empty */.empty .gitignore utils
WORKDIR /
ADD config /config
ADD supervisord.conf /etc/supervisor/conf.d/tiny-tiny-rss.conf

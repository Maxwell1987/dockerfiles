#
# Base on https://github.com/dockerfile/java
#

FROM ubuntu:16.04

ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64

RUN set -xe \
	&& apt-get update \
	&& apt-get install -y --no-install-recommends \
		bzip2 \
		openjdk-8-jdk-headless \
		unzip \
		xz-utils \
	&& rm -rf /var/lib/apt/lists/*

# If you're reading this and have any feedback on how this image could be
#   improved, please open an issue or a pull request so we can discuss it!

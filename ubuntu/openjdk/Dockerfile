#
# Base on https://github.com/dockerfile/java
#

FROM ubuntu:16.04

RUN apt update && apt install -y --no-install-recommends \
		bzip2 \
		unzip \
		xz-utils

# Default to UTF-8 file.encoding
ENV LANG C.UTF-8

# add a simple script that can auto-detect the appropriate JAVA_HOME value
# based on whether the JDK or only the JRE is installed
RUN { \
		echo '#!/bin/sh'; \
		echo 'set -e'; \
		echo; \
		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; \
	} > /usr/local/bin/docker-java-home \
	&& chmod +x /usr/local/bin/docker-java-home

ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64

ENV JAVA_VERSION 8u91
ENV JAVA_UBUNTU_VERSION 8u91-b14-3ubuntu1~16.04.1

RUN set -x \
	&& apt update \
	&& apt install -y \
		openjdk-8-jdk-headless="$JAVA_UBUNTU_VERSION" \
	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]

# If you're reading this and have any feedback on how this image could be
#   improved, please open an issue or a pull request so we can discuss it!

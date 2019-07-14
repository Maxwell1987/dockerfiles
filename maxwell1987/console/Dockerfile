FROM buildpack-deps:bionic

RUN apt-get update && apt-get install -y --no-install-recommends \
		dnsutils \
		iproute2 \
		iputils-ping \
		nano \
		python3 \
		telnet \
		traceroute \
&& rm -rf /var/lib/apt/lists/*

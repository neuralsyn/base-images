# AUTOGENERATED FILE
FROM balenalib/jetson-nano-fedora:28-build

RUN dnf -y update \
	&& dnf clean all \
	&& dnf -y install \
		gzip \
		java-1.8.0-openjdk \
		java-1.8.0-openjdk-devel \
		tar \
	&& dnf clean all

# set JAVA_HOME
ENV JAVA_HOME /usr/lib/jvm/java-openjdk

CMD ["echo","'No CMD command was set in Dockerfile! Details about CMD command could be found in Dockerfile Guide section in our Docs. Here's the link: https://balena.io/docs"]
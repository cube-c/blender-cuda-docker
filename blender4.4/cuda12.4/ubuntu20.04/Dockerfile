FROM nvidia/cuda:12.4.1-devel-ubuntu20.04

ENV BLENDER_MAJOR=4.4
ENV BLENDER_VERSION=4.4.0
ENV BLENDER_TAR_URL=https://download.blender.org/release/Blender${BLENDER_MAJOR}/blender-${BLENDER_VERSION}-linux-x64.tar.xz

RUN apt-get update && \
	apt-get install -y \
		curl wget nano \
		bzip2 libfreetype6 libgl1-mesa-dev \
		libglu1-mesa \
		libxi6 libxrender1 \
        libxkbcommon-dev libsm6 && \
	apt-get -y autoremove

# Install blender

RUN mkdir /usr/local/blender && \
	wget --quiet ${BLENDER_TAR_URL} -O blender.tar.xz && \
	tar -xvf blender.tar.xz -C /usr/local/blender --strip-components=1 && \
	rm blender.tar.xz


VOLUME /media


ENTRYPOINT ["/usr/local/blender/blender", "-b"]

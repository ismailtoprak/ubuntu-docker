# Get docker image
FROM ubuntu:22.04

# install neccessary packages for build
RUN DEBIAN_FRONTEND=noninteractive \
   apt-get update \
   && apt-get install -yq apt-utils \
   git \
   locales \ 
   curl \
   wget \
   sudo \ 
   gcc \
   vim

# cleanup apt caches
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# define locales for build configurations
RUN localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
ENV LANG en_US.utf8

# add user
RUN useradd -ms /bin/bash alonsy && echo "alonsy:ismo34" | chpasswd && adduser alonsy sudo && echo "ubuntu" > /etc/hostname

# switch to alonsy account
USER alonsy

# set default docker path
WORKDIR /home/alonsy

CMD ["sleep", "infinity"]

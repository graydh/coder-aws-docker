FROM ubuntu:noble

RUN apt-get update
RUN apt-get install vim sudo curl -y

RUN useradd -m -s /bin/bash -G sudo coder
RUN echo "coder ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/coder

# auto inject seems to not work with docker-in-docker, install coder cli manually
RUN curl -fsSL https://coder.com/install.sh | sh -s --version 2.12.0

USER coder

# add a fancy prompt to show we're in the correct devContainer
RUN echo "PS1='🐳 \[\033[1;36m\]\h \[\033[1;34m\]\W\[\033[0;35m\] \[\033[1;36m\]# \[\033[0m\]'" > ~/.bashrc

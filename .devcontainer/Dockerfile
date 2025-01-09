FROM ubuntu:noble

RUN apt-get update
RUN apt-get install vim sudo curl -y

RUN useradd -m -s /bin/bash -G sudo coder
RUN echo "coder ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/coder

# auto inject seems to not work with docker-in-docker, install coder cli manually
# TODO version incompatable with host, doesn't show cpu/mem capacity of workspace
RUN curl -fsSL https://coder.com/install.sh | sh

USER coder

# add a fancy prompt to show we're in the correct devContainer
RUN echo "PS1='🐳 \[\033[1;36m\]\h \[\033[1;34m\]\W\[\033[0;35m\] \[\033[1;36m\]# \[\033[0m\]'" > ~/.bashrc

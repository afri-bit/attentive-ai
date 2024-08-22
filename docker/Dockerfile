FROM ubuntu:22.04 as base

ENV DEBIAN_FRONTEND noninteractive

ENV USER_NAME=alpaca
ENV USER_PASSWORD=${USER_NAME}

# ========== Basic installation for ubuntu

RUN apt update \
    && apt install -y \
    locales \
    gcc \
    g++ \
    build-essential \
    python3 \
    python3-pip \
    vim \
    nano \
    net-tools \
    tmux \
    inetutils-ping \
    software-properties-common \
    curl \
    htop \
    git \
    libclang-dev 

RUN locale-gen en_US en_US.UTF-8 \
    && update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8

RUN add-apt-repository universe \
    && curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

RUN echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | tee /etc/apt/sources.list.d/ros2.list > /dev/null 

RUN apt update \
    && apt install -y \
       ros-dev-tools \
       ros-iron-desktop \
       python3-rosdep

# ========== User level

# Create a non-root user with sudo privileges
RUN useradd -m -s /bin/bash "${USER_NAME}" && \
    echo "${USER_NAME}:${USER_PASSWORD}" | chpasswd && \
    usermod -aG sudo "${USER_NAME}"

USER ${USER_NAME}

# Set the working directory
WORKDIR /home/${USER_NAME}

# Update the pip version
RUN pip install --upgrade pip

# Setup ROS environment
RUN echo 'source /opt/ros/iron/setup.sh' >> $HOME/.bashrc

FROM base as convagent

USER root

# ========== Convagent Setup
RUN apt update \
    && apt install -y espeak ffmpeg libespeak1

USER ${USER_NAME}

RUN pip install ollama

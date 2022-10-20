#
# Copyright 2018-2022 Micro Focus or one of its affiliates.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

# Docker registry
ARG DOCKER_HUB_PUBLIC=docker.io

FROM ${DOCKER_HUB_PUBLIC}/cafapi/prereleases:opensuse-jdk11-3.7.0-477072-SNAPSHOT

# Pinning version of scikit-learn to 1.0.1 to avoid this error: "Trying to unpickle estimator LinearSVC from version 1.0.1 when using version 1.1.2."
RUN zypper -n refresh && \
    zypper -n update && \
    zypper -n install python38 && \
    zypper -n install python38-devel && \
    zypper -n install python38-pip && \
    zypper -n install python38-matplotlib && \
    zypper -n install zlib-devel && \
    zypper -n install python38-numpy-devel && \
    zypper -n install python38-lxml && \
    zypper -n install python38-scipy && \
    zypper -n install gcc-c++ && \
    pip install scikit-learn==1.0.1 && \
    pip install regex==2022.6.2 && \
    pip install -U https://github.com/rorytorneymf/talon/archive/refs/tags/1.6.0-with-8138ea9a604f037f47f544dfb805f13d26696275-reverted.zip  && \
    pip install jep==4.0.3 && \
    zypper -n clean --all

ENV LD_PRELOAD=/usr/lib64/python3.8/config-3.8-x86_64-linux-gnu/libpython3.8.so
ENV LD_LIBRARY_PATH=/usr/lib/python3.8/site-packages/talon:/usr/lib64/python3.8/site-packages/jep
ENV PYTHONPATH=/maven

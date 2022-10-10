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

FROM ${DOCKER_HUB_PUBLIC}/cafapi/opensuse-jdk11:3
FROM ${DOCKER_HUB_PUBLIC}/cafapi/prereleases:opensuse-jdk11:3.7.0-rory-tumbleweed-SNAPSHOT

RUN zypper -n refresh && \
    zypper -n update && \
    zypper -n install python3-devel && \
    zypper -n install python3-pip && \
    zypper -n install python3-matplotlib && \
    zypper -n install zlib-devel && \
    zypper -n install python3-numpy-devel && \
    zypper -n install python3-lxml && \
    zypper -n install python3-scipy && \
    zypper -n install gcc-c++ && \
    pip install regex==2022.6.2 && \
    pip install talon==1.3.4 && \
    pip install jep==3.8.2 && \
    zypper -n clean --all

ENV LD_PRELOAD=//usr/lib64/python3.10/config-3.10-x86_64-linux-gnu/libpython3.10.so
ENV LD_LIBRARY_PATH=/usr/lib/python3.10/site-packages/talon:/usr/lib64/python3.10/site-packages/jep
ENV PYTHONPATH=/maven

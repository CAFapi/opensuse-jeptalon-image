#
# Copyright 2018-2020 Micro Focus or one of its affiliates.
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

FROM ${DOCKER_HUB_PUBLIC}/cafinternal/prereleases:opensuse-jdk11-3.3.0-SNAPSHOT

RUN zypper -n refresh && \
    zypper -n update && \
    zypper -n install python-devel && \
    zypper -n install python-pip && \
    zypper -n install python-matplotlib && \
    zypper -n install zlib-devel && \
    zypper -n install python-numpy-devel && \
    zypper -n install python-lxml && \
    zypper -n install python-scipy && \
    zypper -n install gcc-c++ && \
    pip install regex==2014.12.24 && \
    pip install talon==1.3.4 && \
    pip install jep==3.8.2 && \
    zypper -n clean --all

ENV LD_PRELOAD=/usr/lib64/python2.7/config/libpython2.7.so
ENV LD_LIBRARY_PATH=/usr/local/lib/python2.7/site-packages/talon:/usr/local/lib64/python2.7/site-packages/jep
ENV PYTHONPATH=/maven

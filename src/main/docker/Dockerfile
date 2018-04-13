#
# Copyright 2015-2017 EntIT Software LLC, a Micro Focus company.
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

FROM cafinternal/prereleases:opensuse-jdk8-1.0.0-SNAPSHOT

RUN zypper -n install python-devel && \
    zypper -n install python-pip && \
    zypper -n install python-matplotlib && \
    zypper -n install zlib-devel && \
    zypper -n install python-numpy && \
    zypper -n install python-lxml && \
    zypper -n install python-scipy && \
    zypper -n install gcc-c++ && \
    pip install regex==2014.12.24 && \
    pip install numpy==1.8.2 && \
    pip install talon==1.3.4 && \
    pip install jep==3.5.2

ENV PD_PRELOAD=/usr/lib64/libpython2.7.so.1.0
ENV LD_LIBRARY_PATH=/usr/lib/python2.7/site-packages/talon:/usr/lib64/python2.7/site-packages/jep
ENV PYTHONPATH=/maven

# Tag the image
ARG BUILD_NUMBER
ARG BUILD_DATE
ARG GIT_REPO
ARG GIT_BRANCH
ARG GIT_COMMIT

LABEL Build.Number="$BUILD_NUMBER" \
      Build.Date="$BUILD_DATE" \
      Git.Repo="$GIT_REPO" \
      Git.Branch="$GIT_BRANCH" \
      Git.Commit="$GIT_COMMIT"

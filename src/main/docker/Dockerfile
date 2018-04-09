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

FROM cafapi/opensuse-python2:1

ENV JAVA_HOME=/usr/lib64/jvm/java-1.8.0-openjdk-1.8.0

RUN zypper -n in java-1_8_0-openjdk-devel && \
zypper -n install gcc && \
pip install pip --upgrade && \
pip install lxml==3.6.0 --upgrade && \
pip install regex==2014.12.24 talon==1.4.4 && \
pip install statsmodels==0.8.0 && \
pip install jep==3.5.2    

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

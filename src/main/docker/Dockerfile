#
# Copyright 2019-2020 Micro Focus or one of its affiliates.
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

FROM cafapi/opensuse-jdk8:1

RUN zypper -n install python3-devel && \
    zypper -n install python3-pip && \
    zypper -n install gcc-c++ && \
    pip install numpy==1.17.0 && \
    pip install scipy==1.3.1 && \
    pip install pybind11==2.3.0 && \
    pip install jep==3.8.2 && \
    pip install fasttext==0.9.1

ENV LD_PRELOAD=/usr/lib64/python3.6/config-3.6m-x86_64-linux-gnu/libpython3.6m.so
ENV LD_LIBRARY_PATH=/usr/lib64/python3.6/site-packages/jep:/usr/lib64/python3.6/site-packages/fasttext
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

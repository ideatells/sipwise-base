# DOCKER_NAME=sipwise-base-buster
FROM docker.mgm.sipwise.com/sipwise-buster:latest

# Important! Update this no-op ENV variable when this Dockerfile
# is updated with the current date. It will force refresh of all
# of the base images and things like `apt-get update` won't be using
# old cached versions when the Dockerfile is built.
ENV REFRESHED_AT 2019-06-27

RUN apt-get update && apt-get install --assume-yes libmodule-build-perl libtrycatch-perl libstrictures-perl

RUN echo "cd /code && ./t/testrunner" >/root/.bash_history

WORKDIR /code/

################################################################################
# Instructions for usage
# ----------------------
# When you want to build the base image from scratch
# (jump to the next section if you don't want to build yourself!):
#
# NOTE: run the following command from root folder of git repository:
# % docker build --tag="sipwise-base-buster" -f ./t/Dockerfile .
# % docker run --rm -i -t -v $(pwd):/code:rw sipwise-base-buster:latest bash
#
# Use the existing docker image:
# % docker pull docker.mgm.sipwise.com/sipwise-base-buster
# NOTE: run the following command from root folder of git repository:
# % docker run --rm -i -t -v $(pwd):/code:rw docker.mgm.sipwise.com/sipwise-base-buster:latest bash
#
# Inside docker:
#   cd /code && ./t/testrunner
################################################################################

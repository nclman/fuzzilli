FROM swift:latest

ENV DEBIAN_FRONTEND=noninteractive
ENV SHELL=bash

RUN apt-get -y update
RUN apt-get -y upgrade

# Required for jsc
RUN apt-get install -y libicu-dev

RUN mkdir /home/fuzzer
WORKDIR /home/fuzzer

# Add fuzzer binary
ADD FuzzilliBuilder/out/Fuzzilli Fuzzilli

# Add JavaScriptCore binary
ADD JSCBuilder/out jsc
# Add Spidermonkey binary
ADD SpidermonkeyBuilder/out spidermonkey
# Add v8 binary
ADD V8Builder/out v8

RUN mkdir fuzz

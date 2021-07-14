#-------------------------------------------------------------------------------------------------------------
# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License. See https://go.microsoft.com/fwlink/?linkid=2090316 for license information.
#--------------------------------------------------:-----------------------------------------------------------

ARG DOTNETCORE_VERSION=3.1
FROM mcr.microsoft.com/dotnet/core/sdk:${DOTNETCORE_VERSION}
#FROM debian:stretch

# # # put the dotnet tools into the path
ENV PATH="${PATH}:/root/.dotnet/tools" 

RUN apt-get -y update \
&& apt-get -y upgrade 

RUN apt-get -y install curl

# install Azure CLI
RUN curl -sL https://aka.ms/InstallAzureCLIDeb | bash 

# install PowerShell
RUN echo INSTALL POWERSHELL \
&& dotnet tool install --global PowerShell --version 7.0.6

# install NODE LTS
RUN echo INSTALL NODE \
&& curl -sL https://deb.nodesource.com/setup_14.x | bash - \
&& apt-get install -y nodejs

RUN echo INSTALL LUISGEN \
&& dotnet tool install -g LUISGen

# install dotnet runtime 2.1
RUN echo INSTALL DOTNET RUNTIME 2.1 \
&& wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg \
&& mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/ \
&& wget -q https://packages.microsoft.com/config/debian/10/prod.list \
&& mv prod.list /etc/apt/sources.list.d/microsoft-prod.list \
&& chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg \
&& chown root:root /etc/apt/sources.list.d/microsoft-prod.list \
&& apt-get update \
&& apt-get install -y dotnet-runtime-2.1

# # install bot tools
RUN npm i -g --unsafe-perm @microsoft/botframework-cli
RUN npm i -g luis-apis

# install dispatch locally because of issue installing dotnet globally
RUN cd / \
&& npm install botdispatch

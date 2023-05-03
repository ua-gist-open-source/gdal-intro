FROM mcr.microsoft.com/vscode/devcontainers/base:buster

RUN sudo apt update \
  && sudo apt install -y software-properties-common \
  && sudo add-apt-repository ppa:ubuntugis/ppa \
  && sudo apt-get update \
  && sudo apt-get install -y gdal-bin

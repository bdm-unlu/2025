#imagen base
FROM jupyter/scipy-notebook

#copio el requirements
COPY ./requirements.txt /tmp/requirements.txt

USER root

RUN apt-get update && apt-get --yes install apt-utils

RUN apt-get --yes install libproj-dev \
    proj-data \
    proj-bin \
    libgeos-dev \
    graphviz

USER $NB_UID

#instalo los paquetes
RUN pip3 install -r /tmp/requirements.txt

#volumenes para guardar los notebooks
WORKDIR /notebooks
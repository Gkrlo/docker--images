FROM tiangolo/uvicorn-gunicorn-fastapi:python3.7

RUN apt-get update && apt-get install -y libaio1

COPY resources/instantclient_12_2.zip ./

RUN unzip instantclient_12_2.zip -d /usr/lib/ && \ 
    rm instantclient_12_2.zip && \
    ln /usr/lib/instantclient_12_2/libclntsh.so.12.1 /usr/lib/instantclient_12_2/libclntsh.so && \
    ln /usr/lib/instantclient_12_2/libocci.so.12.1 /usr/lib/instantclient_12_2/libocci.so

ENV ORACLE_BASE /usr/lib/instantclient_12_2
ENV LD_LIBRARY_PATH /usr/lib/instantclient_12_2
ENV TNS_ADMIN /usr/lib/instantclient_12_2
ENV ORACLE_HOME /usr/lib/instantclient_12_2

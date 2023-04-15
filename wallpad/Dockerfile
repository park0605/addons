ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8
# Copy data for add-on
COPY run.sh /
COPY js /js

#RUN python3 -m pip install pyserial
apk add py3-pyserial
RUN python3 -m pip install paho-mqtt

WORKDIR /share

# Install requirements for add-on
RUN apk add --no-cache jq npm make gcc g++ python3 linux-headers udev \
&& npm init -f


#RUN python3 -m pip install mqtt
#RUN python3 -m pip install serialport --build-from-source=serialport



RUN chmod a+x /run.sh

# CMD [ "/run.sh" ]
ENTRYPOINT [ "/run.sh" ]

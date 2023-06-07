ARG FROM_IMAGE=vnv_base
FROM ${FROM_IMAGE}

#Install the simple application example. 
COPY . ${SOURCE_DIR}/psip  
RUN  cd ${SOURCE_DIR}/psip \
     && mkdir build \
     && cd build \
     && cmake -DInjection_DIR=${VNV_DIR}/lib/cmake -DCMAKE_INSTALL_PREFIX=${SOFTWARE_DIR}/plugins/psip .. \
     && make \
     && make install  \
     && cp -r ../vnv/config ${SOFTWARE_DIR}/plugins/psip/gui \
     && rm -r ${SOURCE_DIR}/psip

RUN ${VNV_REGISTER} gui psip ${SOFTWARE_DIR}/plugins/psip/gui/vnv.__registration__
RUN ${VNV_REGISTER} plugin PSIP ${SOFTWARE_DIR}/plugins/psip/lib/libpsip.so

FROM  debian:testing-slim

RUN apt update -y && apt install -y qt5-default iputils-ping g++ make \
    libpoco-dev libqt5sql5-psql git && apt -y clean && \
    mkdir -p /usr/lib64/ && \
    ln -s /usr/lib/x86_64-linux-gnu/libPocoNet.so.70 /usr/lib64/libPocoNet.so && \
    ln -s /usr/lib/x86_64-linux-gnu/libPocoFoundation.so.70 /usr/lib64/libPocoFoundation.so && \
    git clone https://github.com/EvgenyKorolev/BackFOP.git && \
    cd BackFOP && qmake && make && cp /BackFOP/out/post /bin

CMD ["/BackFOP/out/post"]
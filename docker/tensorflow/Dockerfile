FROM eismcc/pushpy-tensorflow-gpu:latest

COPY requirements.txt /tmp/requirements.txt
RUN pip install -r /tmp/requirements.txt

COPY entrypoint.sh /tmp/entrypoint.sh

ADD boot /opt/pushpy/boot
ADD conf /opt/pushpy/conf
COPY conf/single.yml /opt/pushpy/push.conf

ADD monitor.py /opt/pushpy

WORKDIR /tmp

EXPOSE 10000 11000 50000

ENTRYPOINT ["/tmp/entrypoint.sh"]

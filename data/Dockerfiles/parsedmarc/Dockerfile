FROM pypy:3-slim

ADD start.sh /start.sh
RUN apt-get update \
    && apt-get install -y libxslt-dev libz-dev libxml2-dev libssl-dev gcc rustc libemail-outlook-message-perl \
    && pip install -U --no-cache-dir parsedmarc \
    && apt-get purge --yes gcc rustc && apt autoremove --yes && apt-get clean \
    && rm -Rf /var/lib/{apt,dpkg}/ && rm -Rf /root/.cache/ && rm -Rf /root/.cargo/ \
    && chmod +x /start.sh

ENTRYPOINT [ "/start.sh" ]

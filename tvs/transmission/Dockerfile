FROM fedora:23

MAINTAINER Eduardo Minguez <edu@linux.com>

RUN dnf clean all && \
    dnf update -y && \
    dnf install -y transmission-daemon-2.84-8.fc23 transmission-2.84-8.fc23 transmission-cli-2.84-8.fc23 transmission-common-2.84-8.fc23 transmission-gtk-2.84-8.fc23 && \
    dnf clean all

ADD files/run_transmission.sh /run_transmission.sh

RUN mkdir -p /var/lib/transmission/{incomplete,downloads,watch} && \
    groupadd -g 8378 tvs && \
    useradd -u 911 -g tvs tvs -s /bin/bash && \
    chown -R tvs:tvs /var/lib/transmission && \
    ln -sf /var/lib/transmission/downloads /downloads
    

ADD files/transmission-daemon/settings.json /etc/transmission-daemon/settings.json
RUN chown -R tvs:tvs /etc/transmission-daemon    

VOLUME ["/var/lib/transmission/downloads", "/var/lib/transmission/incomplete", "/var/lib/transmission/watch", "/etc/transmission-daemon"]

EXPOSE 9091 12345

USER tvs

CMD ["/run_transmission.sh"]

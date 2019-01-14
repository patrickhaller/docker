FROM ubuntu:xenial

RUN apt-get update && apt-get install -y \
	eclipse \
	tightvncserver \
	twm \
	xterm \
	&& apt-get clean && rm -rf /var/lib/apt/lists/*

RUN mkdir /root/.vnc
RUN bash -c "echo foobar | vncpasswd -f > /root/.vnc/passwd"
RUN chmod 600 /root/.vnc/passwd
COPY xstartup /root/.vnc/xstartup
RUN chmod +x /root/.vnc/xstartup

COPY twmrc /root/.twmrc

ENV USER=root
ENV RESOLUTION=1280x800
USER root

ENTRYPOINT vncserver :1 -geometry $RESOLUTION -depth 24 && tail -F /root/vnc/*.log
EXPOSE 5901

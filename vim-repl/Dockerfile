FROM ubuntu:cosmic

RUN apt-get update &&  apt-get install -y \
	autocutsel \
	curl \
	git \
	netcat \
	socat \
	tightvncserver \
	twm \
	wget \
	xterm

RUN apt-get update &&  apt-get install -y \
	tmux \
	vim \
	python \
	python3

RUN apt-get clean && rm -rf /var/lib/apt/lists/*

RUN mkdir /root/.vnc
RUN bash -c "echo foobar | vncpasswd -f > /root/.vnc/passwd"
RUN chmod 600 /root/.vnc/passwd
COPY xstartup /root/.vnc/xstartup
RUN chmod +x /root/.vnc/xstartup

COPY twmrc /root/.twmrc
COPY vimrc /root/.vimrc

ENV USER=root
ENV RESOLUTION=1280x1024
USER root

ENTRYPOINT vncserver :1 -geometry $RESOLUTION -depth 24 && tail -F /root/vnc/*.log
EXPOSE 5901

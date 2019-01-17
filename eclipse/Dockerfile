FROM ubuntu:cosmic

RUN apt-get update && apt-get install --no-install-recommends -y \
	default-jre \
	tightvncserver \
	twm \
	wget \
	xterm \
	&& apt-get clean && rm -rf /var/lib/apt/lists/*

#RUN wget -O /root/eclipse.tar.gz http://ftp.yz.yamagata-u.ac.jp/pub/eclipse/technology/epp/downloads/release/2018-12/R/eclipse-jee-2018-12-R-linux-gtk-x86_64.tar.gz
RUN wget -O /root/eclipse.tar.gz http://www.ofs.edu.sg/user/patrick_haller/eclipse.tar.gz
RUN tar zxf /root/eclipse.tar.gz -C /opt


RUN mkdir /root/.vnc
RUN bash -c "echo foobar | vncpasswd -f > /root/.vnc/passwd"
RUN chmod 600 /root/.vnc/passwd
COPY xstartup /root/.vnc/xstartup
RUN chmod +x /root/.vnc/xstartup

COPY twmrc /root/.twmrc

ENV USER=root
ENV RESOLUTION=1280x1024
USER root

ENTRYPOINT vncserver :1 -geometry $RESOLUTION -depth 24 && tail -F /root/vnc/*.log
EXPOSE 5901

from ubuntu:18.04

run apt-get -qq update && apt-get install -qq --no-install-recommends xinetd rsyslog python3 python3-pip socat qemu-system-x86
run pip3 install click
# only for testing
run apt-get install -qq --no-install-recommends vim net-tools netcat.openbsd

copy biooosless.conf /etc/xinetd.d/biooosless.conf
run chmod 440 /etc/xinetd.d/biooosless.conf
copy banner_fail /banner_fail

copy wrapper /opt/wrapper
run chmod 555 /opt/wrapper
run chmod 551 /opt

run mkdir -p /biooosless && chmod 755 /biooosless
copy src/x.py /biooosless/
copy src/bios-template.bin /biooosless/
copy src/floppy-flag.img /biooosless/flag.img
run chmod 755 /biooosless/x.py
run chmod 644 /biooosless/bios-template.bin /biooosless/flag.img
run chown -R root:root /biooosless

run chmod 773 /tmp/

expose 6543
cmd chmod go-rwx /proc && /usr/sbin/xinetd -syslog local0 -dontfork -f /etc/xinetd.d/biooosless.conf

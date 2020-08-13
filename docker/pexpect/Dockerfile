FROM moku828/gdb-sh-elf:8.1
RUN apt-get update && apt-get install -y --no-install-recommends python3-pip && rm -rf /var/lib/apt/lists/*
RUN pip3 install -q python-gdb-mi pexpect==4.8.0

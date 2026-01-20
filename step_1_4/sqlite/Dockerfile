FROM debian:bookworm-slim

RUN apt-get update && \
	apt-get install -y --no-install-recommends \
		build-essential \
		ca-certificates \
		wget \
		&& rm -rf /var/lib/apt/lists/*

WORKDIR /sqlite_build

COPY sqlite3.c sqlite3.h ./

RUN gcc -fPIC -shared sqlite3.c -o libsqlite3.so

CMD ["/bin/bash"]

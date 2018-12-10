FROM debian
RUN echo "deb http://deb.debian.org/debian/ unstable main" > /etc/apt/sources.list.d/unstable.list
RUN printf 'Package: *\nPin: release a=unstable\nPin-Priority: 90\n' > /etc/apt/preferences.d/limit-unstable
RUN apt-get update
RUN apt-get install -y wireguard iproute openssl ebtables ipset
COPY babeld_rita.conf /etc/config/babeld.conf
COPY babeld /bin/babeld
COPY rita.toml /etc/config/rita.toml
COPY rita /bin/rita
ENTRYPOINT babeld -D -c /etc/config/babeld.conf lo && RUST_LOG=trace rita --platform=linux --config=/etc/config/rita.toml 

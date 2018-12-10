# althea-docker
Dockerfiles for Althea

## Usage

build [rita](https://github.com/althea-mesh/althea_rs) and [althea-babeld](https://github.com/althea-mesh/babeld) for your platform, then copy the binaries into
the docker file folder and run docker build.

You can use [rust-cross](https://github.com/japaric/rust-cross) to easily build binaries for
any arch including go style staticlly linked run anywhere Rust programs using x86_64 musl, as 
for babeld, look in the build scripts directory in althea_rs they can easily be modified to 
build babel instead using openwrt toolchains.

TODO: figure out how to apply [mcvlan](https://docs.docker.com/network/macvlan/#create-a-macvlan-network) effectively to pass through both peer interfaces and to setup the docker
host to send traffic over Althea

TODO: figure out how to handle config files, editing them by hand sucks and some
things (eth private key) we probably want to persist. 

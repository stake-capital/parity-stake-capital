# Parity
Everything Parity

# Ethereum Parity Client on Linux
## Update the system
```
sudo apt update
sudo apt upgrade -y
sudo apt install gcc git make libudev-dev cmake -y
```

if you get errors: 
`sudo apt install build-essential`

## Install rust 
`curl https://sh.rustup.rs -sSf | sh`

## Install Parity
```
# download Parity Ethereum code
$ git clone https://github.com/paritytech/parity-ethereum
$ cd parity-ethereum

# build in release mode or just cargo build if build from specific tag
$ cargo build --release --features final
```

## Start Parity Ethereum

### Manually

To start Parity Ethereum manually, just run

```bash
$ ./target/release/parity
```

so Parity Ethereum begins syncing the Ethereum blockchain.

### Using `systemd` service file

To start Parity Ethereum as a regular user using `systemd` init:

1. Copy `./scripts/parity.service` to your
`systemd` user directory (usually `~/.config/systemd/user`).
2. Copy Parity to bin: `sudo cp -R ./target/release/parity /usr/bin/`
2. To configure Parity Ethereum, write a `/etc/parity/config.toml` config file, see [Configuring Parity Ethereum](https://paritytech.github.io/wiki/Configuring-Parity) for details.



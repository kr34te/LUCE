# ~~1864ish~~IGWT -  Such ! Many currency! HolyCow! 🐕

Copyright (c) 2014-2019 The Monero Project.
Portions Copyright (c) 2012-2013 The Cryptonote developers.

# CyberDollHair
An Android pruned full node for IGWT

[<img src="https://f-droid.org/badge/get-it-on.png"
      alt="Get it on F-Droid"
      height="80">](https://f-droid.org/en/packages/org.igwt.cyberwow/)
<a href='https://play.google.com/store/apps/details?id=org.igwt.cyberwow'><img alt='Get it on Google Play' src='https://play.google.com/intl/en_us/badges/images/generic/en_badge_web_generic.png' height='80'/></a>

# IDroidWT
An Android Wallet for IGWT

[<img src="https://f-droid.org/badge/get-it-on.png"
      alt="Get it on F-Droid"
      height="80">](https://f-droid.org/packages/com.igwt-todo.--/)
<a href='https://play.google.com/store/apps/details?id=com.igwt-todo.--'><img alt='Get it on Google Play' src='https://play.google.com/intl/en_us/badges/images/generic/en_badge_web_generic.png' height='80'/></a>

## Resources

- Web: [igwt-todo.org](http://igwt-todo.org)
- Twitter: [@w0wn3r0](https://twitter.com/w0wn3r0)
- Reddit: [/r/igwt-todo](https://www.reddit.com/r/igwt-todo)
- Mail: [igwt-todo@protonmail.com](mailto:igwt-todo@protonmail.com)
- GitHub: [https://github.com/igwt-todo/igwt-todo](https://github.com/igwt-todo/igwt-todo)
- IRC: [#igwt-todo on Freenode](https://kiwiirc.com/client/irc.freenode.net/?nick=suchchatter|?#igwt-todo)
- Bitmessage Chan: igwt-todo (`BM-2cSzWtrj2pzLva9GF1Jp2TYsnLjrnJpvba`)
- IGWT Funding System: [https://funding.igwt-todo.com](https://funding.igwt-todo.com)
- Keybase Chat Group: [https://keybase.io/team/igwt-todo](https://keybase.io/team/igwt-todo)

Blockchain Explorers
- https://
- https://
- http://.onion

Free Public Nodes
- .onion:34568
- ...:34568 (US)
- ...:34568 (CAN)
- ...:34568 (IN)
- ...:34568 (UK)

Tor Peers
- .onion
- .onion

## Introduction

IGWT is a privacy-centric coin that was fairly launched on April 1, 2018 with no pre-mine, stealth-mine or ICO. IGWT has a maximum supply of around 184 million IGWT with a slow and steady emission over 50 years. It is a fork of Monero, but with its own genesis block, so there is no degradation of privacy due to ring signatures using different participants for the same tx outputs on opposing forks.

## Scheduled software upgrades

IGWT uses a fixed-schedule software upgrade (hard fork) mechanism to implement new features. This means that users of IGWT (end users and service providers) should run current versions and upgrade their software on a regular schedule. The required software for these upgrades will be available prior to the scheduled date. Please check the repository prior to this date for the proper IGWT software version. Below is the historical schedule and the projected schedule for the next upgrade.
Dates are provided in the format YYYY-MM-DD.

| Software upgrade block height | Date       | Release Name | Minimum IGWT version | Recommended IGWT version | Details                                                                            |
| ------------------------------ | -----------| ----------------- | ---------------------- | -------------------------- | ---------------------------------------------------------------------------------- |
| 1                              | 2018-04-01 | Awesome Akita                | v0.1.0.0               | v0.1.0.0                  | Cryptonight variant 1, ringsize >= 8, sorted inputs
| 288,888                          | 2021-02-08 | Hallucinogenic Hypnotoad  | v0.8.0.0               | v0.8.0.0                  | SHA3-256 PoW, Dandelion++ support

X's indicate that these details have not been determined as of commit date.

\* indicates estimate as of commit date

## Release staging and Contributing

**Anyone is welcome to contribute to IGWT's codebase!**

If you have a fix or code change, feel free to submit it as a pull request. Ahead of a scheduled software upgrade, a development branch will be created with the new release version tag. Pull requests that address bugs should be made to Master. Pull requests that require review and testing (generally, optimizations and new features) should be made to the development branch. All pull requests will be considered safe until the US dollar valuation of 1 IGWT equals $1000. After this valuation has been reached, more research will be needed to introduce experimental cryptography and/or code into the codebase.

## Installing from a package

Packages are available for

* Arch Linux/Manjaro

        yay -S igwt-git

* NixOS

        nix-shell -p igwt

* Ubuntu 18.04/Ubuntu 16.04/Debian 9/Debian 8 (amd64)

        sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys B09DF0E4B0C56A94
        sudo add-apt-repository "deb http://ppa.igwt.com/ bionic main"
        sudo apt-get update
        sudo apt-get install igwt

Packaging for your favorite distribution would be a welcome contribution!

**DISCLAIMER: These packages are not part of this repository, and as such, do not go through the same review process to ensure their trustworthiness and security.**


## Building from Source

* Arch Linux/Manjaro

        sudo pacman -Syu && sudo pacman -S base-devel cmake boost openssl zeromq libpgm unbound libsodium git
        git clone https://github.com/igwt/igwt
        cd igwt
        make


* Debian/Ubuntu

        sudo apt update && sudo apt install build-essential cmake pkg-config libboost-all-dev libssl-dev libzmq3-dev libunbound-dev libsodium-dev libpgm-dev git
        git clone https://github.com/igwt/igwt
        cd igwt
        make


## Running Binaries

The build places the binary in `bin/` sub-directory within the build directory
from which cmake was invoked (repository root by default). To run in
foreground:

    ./bin/igwtd

To list all available options, run `./bin/igwtd --help`.  Options can be
specified either on the command line or in a configuration file passed by the
`--config-file` argument.  To specify an option in the configuration file, add
a line with the syntax `argumentname=value`, where `argumentname` is the name
of the argument without the leading dashes, for example `log-level=1`.

To run in background:

    ./bin/igwtd --log-file igwtd.log --detach

To run as a systemd service, copy
[igwtd.service](utils/systemd/igwtd.service) to `/etc/systemd/system/` and
[igwtd.conf](utils/conf/igwtd.conf) to `/etc/`. The [example
service](utils/systemd/igwtd.service) assumes that the user `igwt` exists
and its home is the data directory specified in the [example
config](utils/conf/igwtd.conf).

Once node is synced to network, run the CLI wallet by entering:

    ./bin/igwt-wallet-cli

Type `help` in CLI wallet to see standard commands (for advanced options, type `help_advanced`).

## Tor Anonymity Network

* Install [Tor Browser](https://www.torproject.org/download/)
* Open `torrc` file in a text editor ([installation directory]/Browser/TorBrowser/Data/Tor/torrc) and add hidden service information as follows:

```
HiddenServiceDir [installation directory]/Browser/TorBrowser/Data/Tor/igwt_node
HiddenServiceVersion 3
HiddenServicePort 44568 127.0.0.1:44568
```
* Save `torrc` file and restart Tor Browser (keep open)
* Change directory to the `igwt_node` folder, open `hostname` file, and copy your node's ".onion" address
* Start igwtd with the following parameters:

```
./igwtd --tx-proxy tor,127.0.0.1:9150,10 --add-peer hdps3qwnusz64r7odvynmae6myc2uyvrsc2emap6636qeuzll72eouid.onion:44568 --anonymous-inbound YOUR_NODE_ADDRESS.onion:44568,127.0.0.1:44568,25
```

### Access remote Tor node from CLI wallet

```
./igwt-wallet-cli --proxy 127.0.0.1:9150 --daemon-address todo.onion:34568
```

Use port `9050` instead of `9150` if you installed Tor as a standalone daemon. For more information, check out [ANONYMITY_NETWORKS](https://github.com/igwt/igwt/blob/master/ANONYMITY_NETWORKS.md).

## Donating to IGWT Project

Developers are volunteers doing this mostly for shits and giggles. If you would like to support our shenanigans and stimulant addictions, please consider donating:

XMR: `todo`

BTC: `todo`

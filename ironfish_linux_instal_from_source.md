# Install

Tested on: ubuntu 20.04
reference: https://github.com/iron-fish/ironfish#initial-setup

### Node.js

Install node, ref: https://github.com/nodejs/help/wiki/Installation
```
# download bianryes
wget https://nodejs.org/dist/v16.13.0/node-v16.13.0-linux-x64.tar.xz

# unzip
VERSION=v16.13.0
DISTRO=linux-x64
sudo mkdir -p /usr/local/lib/nodejs
sudo tar -xJvf node-$VERSION-$DISTRO.tar.xz -C /usr/local/lib/nodejs 

# set env
echo 'VERSION=v16.13.0' >> ~/.profile
echo 'DISTRO=linux-x64' >> ~/.profile
echo 'export PATH=/usr/local/lib/nodejs/node-$VERSION-$DISTRO/bin:$PATH' >> ~/.profile

. ~/.profile

# test
node -v
```

install pm npm
```
sudo apt install npm -y
```

### Install Rush

ref: https://www.rust-lang.org/learn/get-started
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```

### Install yarn

ref: https://classic.yarnpkg.com/en/docs/install#mac-stable

```
npm install --global yarn && yarn --version

```

# Iron fish

```
git clone https://github.com/iron-fish/ironfish.git
```

Run `yarn install` from the root directory to install packages.

change dir to `/ironfish-cli`

Build, run, when code change
```
yarn start

# with no code change
yarn start:once
```

### Mine
change your own `graffiti`, run in two seperate terminals:
```
# one terminal
yarn start start -d default -p 9033
# the other
yarn start config:set blockGraffiti "graffiti"
yarn start miners:start -t 8
```

check status
```
yarn start status -f
```

### Update source code

code change, build, run
```
yarn start
```
back to mine

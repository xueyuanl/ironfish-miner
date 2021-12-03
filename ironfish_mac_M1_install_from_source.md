# Install

Tested on M1, macOS 11.4

### Install brew

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Node.js

Use the macOS installer from UI, https://nodejs.org/en/download/, `v16.13.1`

### Rust
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```

### yarn

```
sudo npm install --global yarn && yarn --version
```

### install denpendencies

```
# install cmake
brew install cmake

# install openssl
brew install openssl
echo 'export PATH="/opt/homebrew/opt/openssl@3/bin:$PATH"' >> ~/.zshrc
. ~/.zshrc

export LDFLAGS=“-L/opt/homebrew/opt/openssl@3/lib"
export CPPFLAGS="-I/opt/homebrew/opt/openssl@3/include"
export OPENSSL_ROOT_DIR=/opt/homebrew/opt/openssl@3/

# export PKG_CONFIG_PATH="/opt/homebrew/opt/openssl@3/lib/pkgconfig" # if not ok, try it
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
run in two seperate terminals:
```
# first
yarn start start -d default -p 9033
# second
yarn start config:set blockGraffiti "<your-graffiti>"
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

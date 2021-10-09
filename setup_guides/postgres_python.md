# How to Install `psycopg2/ psycopg2-binary` on M1 Mac

M1 mac with big sur or monterey bricks existing configuration of `psycopg2` required for python/postgres development
pipeline. 
Follow the guide below to install it successfully. 

1. Make sure you have `xcode-select` installed on your mac. If not install with following.

```bash
sudo rm -rf /Library/Developer/CommandLineTools
sudo xcode-select --install
```

2. Install postgresql and openssl, and link openssl. Export openssl to your path, and link it to pkgconfig as well.

```bash

brew install postgresql
brew install openssl

# linking
brew link openssl

# this is what you'll see
Warning: Refusing to link macOS provided/shadowed software: openssl@1.1
If you need to have openssl@1.1 first in your PATH, run:
  echo 'export PATH="/opt/homebrew/opt/openssl@1.1/bin:$PATH"' >> ~/.zshrc

For compilers to find openssl@1.1 you may need to set:
  export LDFLAGS="-L/opt/homebrew/opt/openssl@1.1/lib"
  export CPPFLAGS="-I/opt/homebrew/opt/openssl@1.1/include"

For pkg-config to find openssl@1.1 you may need to set:
  export PKG_CONFIG_PATH="/opt/homebrew/opt/openssl@1.1/lib/pkgconfig"

```

3. Install `psycopg2` or `psycopg2-binary` based on what you need.

```
pip install psycopg2
```
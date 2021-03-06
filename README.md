## st - simple terminal

st is a simple terminal emulator for X which sucks less.

## Requirements

In order to build st you need the Xlib header files.

## Installation

Edit `config.mk` to match your local setup (st is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install st (if
necessary as root):

    make clean install

## Running st

If you did not install st with make clean install, you must compile
the st terminfo entry with the following command:

    tic -sx st.info

See the man page for additional details.

## Credits

Based on Aurélien APTEL \<aurelien dot aptel at gmail dot com\> bt source code.

## My changes

This was created based on [st
0.8.2](https://dl.suckless.org/st/st-0.8.2.tar.gz) , the patch added on
[st-sane-defaults](https://aur.archlinux.org/packages/st-sane-defaults/)

```bash
wget https://dl.suckless.org/st/st-0.8.2.tar.gz
wget https://st.suckless.org/patches/nordtheme/st-nordtheme-0.8.2.diff
git clone https://aur.archlinux.org/st-sane-defaults.git
cp st-sane-defaults/sane-defaults-patch.diff ./
tar -zxvf st-0.8.2.tar.gz
patch -d st-0.8.2 < st-sane-defaults/sane-defaults-patch.diff
patch -d st-0.8.2 < st-nordtheme-0.8.2.diff
```

Then proceeded to fix the rejects manually

I ran into problems trying to run `nvim` so I copied the `st.info` file from
the official [st repo](https://git.suckless.org/st) and did

```bash
tic -sx st.info
```

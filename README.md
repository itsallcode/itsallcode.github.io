# itsallcode.github.io

Content of https://blog.itsallcode.org/

## Publishing Guide

### Checkout

```sh
git clone https://github.com/itsallcode/itsallcode.github.io.git
cd itsallcode.github.io/
git submodule init
git submodule update
```

### Initial Setup

Install [Hugo](https://gohugo.io/):

```sh
sudo apt install hugo
```

### Start Live Preview

Start Hugo server:

```sh
cd itsallcode.github.io
hugo server
```

Open http://localhost:1313 in your browser. The blog will be updated automatically when you save files.

### Build Website

Run the following command:

```sh
hugo
```

This will generate the website in directory `public/`.

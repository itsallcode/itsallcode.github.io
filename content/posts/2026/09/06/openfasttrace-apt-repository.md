---
title: "Install OpenFastTrace from the itsallcode.org APT Repository"
date: 2026-09-06
draft: false
author: "sebastian"
---

OpenFastTrace is now available from the new [Itsallcode APT repository](https://apt.itsallcode.org). Debian, Ubuntu, and users of other Debian-based distributions can install it through their normal package-management workflow.

[OpenFastTrace 4.9.0](https://github.com/itsallcode/openfasttrace/releases/tag/4.9.0) is the first version published there. From now on, we will publish new OFT releases as `.deb` packages in the repository shortly after their GitHub release.

## Configure the repository

First, install the itsallcode.org signing key and add the APT source:

```sh
sudo install --directory --mode=0755 /etc/apt/keyrings
curl --fail --silent --show-error --location \
  https://apt.itsallcode.org/itsallcode-archive-keyring.asc \
  | sudo gpg --dearmor --yes --output /etc/apt/keyrings/itsallcode-archive-keyring.gpg
echo 'deb [signed-by=/etc/apt/keyrings/itsallcode-archive-keyring.gpg] https://apt.itsallcode.org stable main' \
  | sudo tee /etc/apt/sources.list.d/itsallcode.list > /dev/null
sudo apt update
```

Before trusting a newly downloaded signing key, compare its fingerprint with the [published fingerprint](https://apt.itsallcode.org/itsallcode-archive-keyring.fingerprint).

## Install OpenFastTrace

Once the repository is configured, install OpenFastTrace with:

```sh
sudo apt install openfasttrace
```

After installation, `oft --help` shows the available command-line options. For usage and requirement notation, see the [OpenFastTrace user guide](https://github.com/itsallcode/openfasttrace/blob/main/doc/user_guide/user_guide.md).

The [APT repository project](https://github.com/itsallcode/itsallcode-apt-repository) contains the repository documentation and packaging sources.

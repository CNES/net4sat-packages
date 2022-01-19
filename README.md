Net4Sat Packages
================

Welcome on the PPA repository for the packages managed by the Net4Sat project.

Usage
-----

This PPA is signed using a GPG key, so you'll first want to include
[the signing key](gpg/net4sat.gpg.key) into your APT keyring. To do so, run the
next command on your machine:

```
curl -sS https://raw.githubusercontent.com/CNES/net4sat-packages/master/gpg/net4sat.gpg.key | sudo apt-key add -
```

Next, you'll want to instruct APT that you want to fetch packages from this PPA:

```
echo "deb https://raw.githubusercontent.com/CNES/net4sat-packages/master/ focal stable" | sudo tee /etc/apt/sources.list.d/github.net4sat.list
```

You can use the `dev` or `testing` component instead of `stable` depending on
your needs.

Lastly, you want to populate APT's cache so it knows which packets are available from here:

```
sudo apt-get update
```

You're all set-up now, you can install any packet you want from here, e.g.:

```
sudo apt-get install pepsal
```

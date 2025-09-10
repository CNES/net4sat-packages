Net4Sat Packages
================

Welcome on the PPA repository for the packages managed by the Net4Sat project.

Usage
-----

This PPA is signed using a GPG key, so you'll first want to include
[the signing key](gpg/net4sat.gpg.key) into your filesystem and instruct
APT to use it to check packages from this repository. To do so, start by
downloading the key to a path of your liking, for instance:

```
sudo mkdir /etc/apt/keyrings
curl -sS https://raw.githubusercontent.com/CNES/net4sat-packages/master/gpg/net4sat.gpg.key | gpg --dearmor | sudo dd of=/etc/apt/keyrings/net4sat.gpg
```

Depending on your system, you may need to also change the reading rights
of the file, so APT can read it:

```
sudo chmod a+r /etc/apt/keyrings/net4sat.gpg
```

Next, you'll want to instruct APT that you want to fetch packages from
this PPA. Run the following command to create the appropriate file in
the `/etc/apt/sources.list.d/` folder:

```
cat << EOF | sudo tee /etc/apt/sources.list.d/github.net4sat.sources
Types: deb
URIs: https://raw.githubusercontent.com/CNES/net4sat-packages/master/focal/
Suites: focal
Components: stable
Signed-By: /etc/apt/keyrings/net4sat.gpg
EOF
```

Change `focal` by `jammy`, `noble`, `bookworm` or `trixie` if appropriate.

You can also use the `dev` or `testing` components instead of or alongside `stable` depending on your needs.

Lastly, you want to populate APT's cache so it knows which packets are available from here:

```
sudo apt-get update
```

You're all set-up now, you can install any packet you want from here, e.g.:

```
sudo apt-get install pepsal
```

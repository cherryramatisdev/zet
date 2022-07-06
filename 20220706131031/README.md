# install docker on ubuntu server

The documentation on docker is so bad omg, this is just simpler:

1. Clone the repo

```
gh repo clone docker/docker-install
```

2. Run the install script

```
./install.sh
```

3. Setup as rootless

```
dockerd-rootless-setuptool.sh install
```


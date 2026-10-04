# SmolVM machines

This repository contains Smolfiles for creating persistent [SmolVM](https://github.com/smol-machines/smolvm) machines.

## Machines

| Smolfile | Description |
| --- | --- |
| [`arch-docker.smolfile`](arch-docker.smolfile) | Arch Linux ARM machine for Docker Engine. Installs Docker, stores its data on the VM's storage disk, and selects `virtio-net` in the Smolfile. |
| [`atelier.smolfile`](atelier.smolfile) | Systemd-enabled Ubuntu 26.04 machine for Atelier. Exposes the guest Docker socket to the host and forwards host port `8095` to guest port `80`. |

## Create and start a machine

Install the `smolvm` CLI first. Then create and start the machine you want:

```sh
smolvm machine create --name docker-arch --smolfile arch-docker.smolfile
smolvm machine start --name docker-arch
```

```sh
smolvm machine create --name atelier --smolfile atelier.smolfile
smolvm machine start --name atelier
```

List machines with `smolvm machine ls`. Stop one with `smolvm machine stop --name NAME`.

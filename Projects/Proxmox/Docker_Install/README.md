# Install Docker

> The purpose of this playbook is to install and verify docker on the remote host(s).

## Pre-Setup

1. Test Reacheability.
2. Update Cache `apt update`.
3. Upgrade packages to the latest `apt upgrade`.
4. Remove conflicting packages(if exist).
5. Install packages to allow apt to use a repository over HTTPS.

## Adding Docker GPG key and setting up Docker APT Repo

- Major credit goes to this repo. Was struggling a lot adding the keys correctly before referring to this.
<br>`https://github.com/modem7/Ansible/blob/master/tasks/docker_install.yaml`

6. Remove old gpg keys if they exist.
7. Download Docker GPG key.
8. De-Armor Docker GPG key.
9. Add Docker's repository to APT sources list.

## Install Docker Engine and Verify

10. Install Docker Engine and other required packages.
11. Verify Installation using `community.docker.docker_container` module.
baseimage-docker
================

This is a simple base image starting from the phusion/baseimage with extra installed packages:
* `software-properties-common` adding the `add-apt-repository` command
* `ca-certificates` containing updated SSL certificated for various services
* `wget` for downloading files easily

Public keys
----------------
As an extra to facilitate login through ssh you can specify the `GITHUB_USERS` environment variable that can contain a comma-separated list of github user names of which public keys will be added to this docker container on startup. for example `-e GITHUB_USERS=sjoerdmulder` will add my public keys (https://github.com/sjoerdmulder.keys) to the docker container.
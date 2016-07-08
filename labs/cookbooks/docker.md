# Docker Cookbook

* Git repository: https://github.com/chef-cookbooks/docker
* Supermarket: https://supermarket.chef.io/cookbooks/docker

## Background

The Docker Cookbook is a library cookbook concerned specifically with management of the Docker Container Engine as developed by Docker, Inc.. It provides custom resources for use in recipes but does not address the Docker ecosystem, tooling, or prerequisite technology such as cgroups or aufs.

## About Docker
Docker is an open source project for packing, shipping and running application in lightweight containers. (Imagine LXC or Solaris Zones).
Docker containers are both hardware-agnostic and platform-agnostic which means they can run anywhere and they don't require you to use a particular language, framework or packaging system. 
While docker is not lightweight virtual machines if your application a Unix process that uses files, tcp connections, environment variables, standard Unix streams and command-line arguments as inputs and outputs, then Docker can run it.

## Further Reading
* https://docs.docker.com
* https://github.com/docker/docker
* https://docs.docker.com/engine/examples/

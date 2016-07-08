# Etcd Cookbook

* Git repository: https://github.com/chef-cookbooks/etcd
* Supermarket: https://supermarket.chef.io/cookbooks/etcd

## Background

The Etcd Cookbook is a library cookbook that provides means to install and configure the etcd distributed key/value store.

## About Etcd 
Etcd is a distributed key value store that provides a reliable way to store data across a cluster of machines, generally referred to as a “service discovery” system. Etcd gracefully handles leader elections during network partitions and will tolerate machine failure, including the leader.

There are several other open source service discovery projects in the wild including consul and zookeeper. While these implementations are drastically different, they seek to achieve the same purpose. If you are unfamiliar with Etcd but familiar with the former or latter then you (should) have a common vocabulary for the technology.

## Further Reading
More information on etcd can be found here:

* https://github.com/coreos/etcd
* https://coreos.com/etcd/
* https://coreos.com/etcd/docs/latest/
* https://coreos.com/etcd/docs/latest/getting-started-with-etcd.html
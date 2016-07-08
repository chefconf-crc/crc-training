## Lab 2
## Create Chef Cookbook using chef generate
Allotted Time: 20 minutes

In this activity, you will generate a sample cookbook using the chef generate command. This will be a quick review for many, the essentials to generate the cookbook, create a kitchen.docker.yml file and converge the node. This will verify that you know the essentials for creating and converging on your system and that everything is working correctly. 

Create cookbook and an install_apache recipe.

```
 cd ~/wd
 chef generate cookbook apache
 git add apache
 git commit -m "creation of apache cookbook"
 cd apache
 chef generate recipe . install_apache
 vi recipes/install_apache.rb

```

Add the follow `resources` to the `install_apache` recipe.

```
package 'httpd'

service 'httpd' do
  action [ :enable, :start ]
end

```


Edit the default recipe:

```
   vi recipes/default.rb
```

Update the contents of the `default.rb` recipe with the following contents:


```
include_recipe 'apache::install_apache'

```

Create a `.kitchen.docker.yml` to match the following configuration. 


```

 $ vi .kitchen.docker.yml


driver:
  name: dokken
  chef_version: latest
  privileged: true # because Docker and SystemD/Upstart

network:
    - ["forwarded_port", {guest: 80, host: 80}]

transport:
  name: dokken

provisioner:
  name: dokken

verifier:
  name: inspec
  format: doc

platforms:

- name: centos-6
  driver:
    image: centos:6
    platform: rhel
    pid_one_command: /sbin/init
    intermediate_instructions:
      - RUN yum -y install which initscripts


```


Update which configuration kitchen uses by setting the *KITCHEN_LOCAL_YAML* file and then converge your node.

```
$ export KITCHEN_LOCAL_YAML=.kitchen.docker.yml
$ kitchen converge 
$ kitchen login
```

How do you know if your recipe worked? Kitchen converge finishes without errors, and you have a port up and running. You can check by browsing directly to the node because you have set up port forwarding!

Validate your node has apache up and running:

```
curl localhost

```

## Outcomes

* Use chef generate command to create a cookbook.
* Understand basic kitchen configuration.
* Successfully running Apache on your node.

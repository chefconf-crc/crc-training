# Translate a runbook for installing MongoDB into chef
Allotted Time: 20 minutes

In this activity your team will be creating a community cookbook from scratch.

1. Read the following instructions.
2. Identify who will do what on the team and pair as needed.
3. Create a teamname-mongodb cookbook
4. Upload teamname-mongodb cookbook to the class supermarket https://supermarket.reusablechef.com/dashboard.

MongoDB is an open-source, document-oriented database designed for ease of development and scaling.  The MongoDB documentation site includes a [installation guide on how to install MongoDB on Red Hat Enterprise Linux, CentOS Linux, Fedora Linux, or a related system](http://docs.mongodb.org/manual/tutorial/install-mongodb-on-red-hat-centos-or-fedora-linux/). 

* [Chef Resource Documentation](https://docs.chef.io/resources.html)

Read the [installation guide](http://docs.mongodb.org/manual/tutorial/install-mongodb-on-red-hat-centos-or-fedora-linux/), identify the resources you need, and create a mongodb cookbook populated with an appropriate recipe. 

As a team identify 

* What users do you need? What groups?
* What packages do you need?
* What configurations do you need?
* Where is data stored?
* What directories do you need to create?
* What services do you need?

Hint:

## Use the yum community cookbook

The yum community cookbook provides resource *yum_repository* that allows us to make individual yum repositories available for use. 

In the [installation guide](http://docs.mongodb.org/manual/tutorial/install-mongodb-on-red-hat-centos-or-fedora-linux/), we see that we need to configure a yum repo in order to install mongodb packages using yum. 


```
[mongodb-org-3.2]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/3.2/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-3.2.asc
```

translates to chef dsl as: 

```
    yum_repository 'mongodb-org-3.2' do
      description 'MongoDB Repository'
      baseurl 'https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/3.2/x86_64/'
      gpgcheck true
      gpgkey 'https://www.mongodb.org/static/pgp/server-3.2.asc'
      enabled true
      action :create
```


## Make sure your hosted chef account has connected to the supermarket.

Browse to the class supermarket website at https://supermarket.reusablechef.com.

Create (or login to your existing) hosted chef account. 

## Creating a hosted chef account

If you have not created a hosted chef account, fill in the form with a real email address, as you will need to verify your account.

Check your email for the verification link.

Click on the verification link. This will generate your pemfile. Copy and save this pemfile to your node (and you may want to save this locally as well). The node will go away, this hosted chef account is yours free to do with as you wish.

## Login to your existing hosted chef account.

Copy your user pemfile to your node. If you don't have this currently, you will need to regenerate (which will invalidate your old pemfile, and any use of the old pemfile will fail).

## Private versus Public Supermarket

Note. When you use the Public Supermarket you should link your Github account to your Chef account so that your contributions on GitHub are signed with your Contributors License Agreement.

If you haven't signed the Contributors License Agreement, and your company doesn't have a company license agreement make sure that you [Sign the individual contributor license agreement.](https://supermarket.chef.io/icla-signatures/new). This will ensure that any contributions you make in this class and in the future can get included in community cookbooks.

## Configure stove on your node (Everyone)

[Stove](https://github.com/sethvargo/stove) 

You want to set up authentication to supermarket using your pem, and set the endpoint to be the class supermarket. (If you don't set it up as the class supermarket, it will push to the public supermarket instead!) If you forget to configure extended-metadata then your cookbook uploads will not include the metadata information that comes from Chef 12+ (issues_url for example).

```
$ stove login --username YOURUSERNAME --key ~/.chef/HOSTEDCHEF.pem
$ stove --endpoint https://supermarket.reusablechef.com/api/v1
$ stove --extended-metadata
```

## Upload completed cookbook to the supermarket (1 person)

Change to the cookbook directory and then execute stove.

```
$ chef exec stove
```

Login to the class supermarket and add the rest of your team as moderators to the cookbook.

https://supermarket.reusablechef.com


## Outcome 

* mongodb running on the node within a docker container
* code checked into repository on github
* A successful push to teamname-mongodb to the class supermarket https://supermarket.reusablechef.com/dashboard.


## Hint

* If you need further hints, you can check out this [working example](https://github.com/nathenharvey/install_mongo)  https://github.com/nathenharvey/install_mongo of minimal requirements to install mongodb.

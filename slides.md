slidenumbers: true
footer: __**:sparkles: @sigje :sparkles:**__
<!-- theme: "Letters from Sweden" white -->

=======

# [fit] Crafting Reusable Cookbooks
#### Jennifer Davis 

Network Name: 
Access Code:  

---

# Ian Henry

---

# TA's

---

# Communication 

* Jennifer Davis Twitter: @sigje 
* Ian Henry Twitter: @Eeyun___

---

# Feedback

* Constructive feedback
  * What did you find helpful?
  * What would you like to see more/less of?
  * Was there anything you found unclear?

---

Network Name: 
Access Code:  

---

# Why are we here?

---

# Expectations

* Safe space to share experiences, learn from each other
* [Code of Conduct]
* Learn effective workflows for using and testing source control and configuration management

---

# Collaboration

> Individuals working together with shared interactions and input building towards a common goal.

---

# Collaboration

* Multiple types of collaboration
* Monitoring for single points of failure
* Monitoring burnout


![](/Users/jenniferdavis/images/14283534363_a2db2d3345_k.jpg)

[^3]: CC Image courtesy of Spoons by Jacqui Brown on Flickr

---

# Smarter Teams
## build better value


![](/Users/jenniferdavis/images/25392512853_3462461c21_k.jpg)

[^2]: CC Image courtesy of WOCinTech Chat by wocintech on Flickr

^ * Lots of Communication
* Contribute equally to team's discussions
* Theory of Mind
* Increased diversity
Why Some Teams are Smarter than Others
Anita Woolley and Thomas Malone

---

# Tools

> Accelerators of culture that if used effectively can enhance and support a culture of collaboration and affinity.

---

# Team

* Common purpose
* Defined beliefs
* Empowered

---

# Diversity in Teams

* Professional
* Personal
* Goals
* Cognitive Styles

---

# Critical Habits for Teams

* Code Review
* Pairing

---

# Code Review

* Max 90 minutes in one setting

---

# Pairing

* Agile software development
* 2 people work together on 1 workstation
* Driver - writes code
* Observer - reviews each line
* Roles switch frequently

---

# Types of Pairing

* Expert-expert
* Expert-novice
* Novice-novice



^ When experts pair, work gets done quickly, new innovation not always obtained, depending on skill overlap because not questioning accepted standards of doing things.

^ When expert and novice pair, can be very good or very bad. if expert isn't patient and does all the typing, novice learns helplessness and slow to get anything done. if expert is patient can involve growth for both as novice helps expert to question standards.

^ When novices pair, can work together to learn and achieve more than a novice working on their own. If no understanding in pair, and fire-fighting schedules can lead to poor practices implemented into production higher technical debt.

---

# Team Activity 1

* Meet your team!
 * What are motivations? 
 * What are objectives?
 * Skills? Gaps in skills?
  * git, chef, docker, continuous integration, continuous delivery

http://goo.gl/forms/Pem3KqRvGbSF3Ovv2

Time: 20 minutes

![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/timer.png)

---

# Devops Tools

* Establish local development environment
* Version control
* Manual -> Automation -> Continuous
 * Artifacts
 * Infrastructure
 * Sandbox
 * Test and Build
 * Monitoring

---

# Local Development Environment (LDE)

* Consistent set of tools across the team
* Ability to quickly onboard new engineers

---

# Team Activity 2

* Share with your team:
 * Do you have a team common local development environment?
 * What current tools are you using in chef development?

Time: 10 minutes

![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/timer.png)

---

# Provisioned Node - LDE

* AWS instance node
* Chef DK
 * Test Kitchen
 * Ruby
 * ChefSpec, ServerSpec
* Git

---

# [fit] Introduction to Lab 1

* Log into node
* Set up git 
* Create GitHub identity
* Set up GitHub keys.
* Share team tools from Activity 2.

[Lab 1](https://github.com/iennae/crc-training/blob/master/labs/lab_1.md)

![fit](images/standing_cat.png)

---

# Lab 1

Time: 20 minutes

![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/timer.png)

---

# Quick Chef Review

---

# Resources

* Ingredients of infrastructure
* Basic building blocks

![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/slides_splash_resources.png)

----

# Resource Review


```ruby
RESOURCETYPE "RESOURCE_NAME" do
  PARAMETER PARAMETER_VALUE
end
```

---

# Resources

A resource is a statement of policy that:

* Describes the desired state for an element
* Specifies a resource type---such as ``package``, ``template``, or ``service``
* Lists additional details (also known as parameters), as necessary
* Are grouped into recipes

---

# Recipes

* Collection of ordered resources
* Combination of ruby and Chef DSL

---

# Cookbooks

* Thematic
* Collection of recipes and other supporting files

---

# Run List

* Ordered list of recipes and roles
* Specific to a node

---

# Nodes

* Machine (virtual, physical, cloud server, or other device) that is managed by Chef

---

# Environments

* Abstraction models workflow
* Name
* Description
* Cookbook version pinning

---

# Supermarket

* Community site with a number of cookbooks
* Read before using in your environment

---

# Chef DK

* Chef development kit
* Includes a number of utilities and software to facilitate cookbook creation
* Free download off of the website

---

# Berkshelf

* Dependency management
* Included with Chef DK

---

# Test Kitchen

* Included with Chef DK
* Sandbox automation
* Test harness

---

# Test Kitchen

* Execute code on one or more platforms
* Driver plugins supporting various cloud and virtualization providers

---

# .kitchen.yml

* driver
* provisioner
* platforms
* suites

---

# .kitchen.yml driver

* virtualization or cloud provider

Example: vagrant, docker

---

# .kitchen.yml provisioner

* application to configure the node

Example: chef_zero

---

# .kitchen.yml platforms

* target operating systems

Example: centos-6.5

---

# .kitchen.yml suites

* target configurations

Example:
```
 name:default
   run_list:
   - recipe[apache::default]
   attributes:
```

---

# Kitchen commands (1/2)

* kitchen init
* kitchen list
* kitchen create
* kitchen converge

---

# Kitchen commands (2/2)

* kitchen verify
* kitchen destroy
* kitchen test

---

# [fit] Introduction to Lab 2

* Create cookbook

[Lab 2](https://github.com/iennae/crc-training/blob/master/labs/lab_2.md)

![fit](images/standing_cat.png)

---

# Lab 2

Time: 20 minutes

![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/timer.png)

---

# Runbook to Recipes

---

# Introducing MongoDB

---

# MongoDB terminology

* document - basic unit of data for MongoDB, ordered set of keys with associated values
* collection - group of documents. analogous to table.
* instance - MongoDB can host multiple independent databases, each of which can have its own collections.
* _id - special key unique within a collection.

---

# MongoDB Shell

* mongo 

full featured JavaScript interpreter

---

# [fit] Introduction to Lab 3

Translate a runbook for installing MongoDB into chef.

[Lab 3]https://github.com/iennae/crc-training/blob/master/labs/lab_3.md)

![fit](images/rainbow_cat.png)


---

# Lab 3

Time: 20 minutes

![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/timer.png)

---

# History of Customizing Chef

* Attributes
* Definitions
* LWRP and HWRP

---

# Introducing Custom Resources 

---

# [fit] Introduction to Lab 4

Translate our MongoDB cookbook from recipes into resources.

[Lab 4](https://github.com/iennae/crc-training/blob/master/labs/lab_4.md)

![fit](images/standing_cat.png)

---

# Lab 4

Time: 30 minutes

![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/timer.png)

---

# Managing Risk

* Test
* Small frequent releases

---

# Linting

* Ensure code adheres to styles and conventions
* Weave expectations into development
* Encourages collaboration

---

# Testing

* Documenting objectives and intent
* Measuring "done"

---

# Code Correctness

* foodcritic
* rubocop

---

# Integration Tests

* ServerSpec
* InSpec

---

# Rubocop

* Ruby linter
* Analyzes source code to verify the syntax and structure of our cookbooks.
* [Ruby style guide](https://github.com/bbatsov/ruby-style-guide)
* Included with ChefDK

---

# Why

* identify simple errors early
* improve the review process by eliminating stylistic issues

---

# Rubocop Example

```
$ rubocop cookbooks/COOKBOOK1 cookbooks/COOKBOOK2 cookbooks/COOKBOOK4
```

---

# Reading Rubocop Output

```
Inspecting 8 files
CWCWCCCC
```

* `.` means that the file contains no issues
* `C` means a issue with convention
* `W` means a warning
* `E` means an error
* `F` means an fatal error

---

# Rubocop Cops

* Lint
* Rails
* Style

Example: rubocop --lint.

---

# Disabling Rubocop cops

Any configuration in `.rubocop.yml` is disabled.

To disable string literals:
```
StringLiterals:
  Enabled: false
```

---

# Foodcritic

* Chef linter
* [Chef style guide](http://foodcritic.io)
* Included with ChefDK

---

# Foodcritic Example

```
$ foodcritic cookbooks/setup
```

---

# Reading Foodcritic Output

```
FC008: Generated cookbook metadata needs updating: ./metadata.rb:2
```

---

# ServerSpec

* Tests to verify servers functionality
* Resource types
 * Package, service, user, and many others
* Integrates with Test Kitchen
* http://serverspec.org

---

# ServerSpec Generic Form

```
describe "<subject>" do
  it "<description>" do
    expect(thing).to eq result
  end
end
```

---

# ServerSpec Potential Tests

* Is the service running?
* Is the port accessible?
* Is the expected content being served?

---

# ServerSpec Example

```
describe 'apache' do
 it "is installed" do
   expect(package 'httpd').to be_installed
 end
 it "is running" do
   expect(service 'httpd').to be_running
 end
end
```

---

# Reading ServerSpec Output

```
app::default
  httpd service is running

Finished in 0.26429 seconds (files took 0.7166 seconds to load)
1 example, 0 failures
```

---

# InSpec

* infrastructure specification
* open-source testing framework for infrastructure
* human and machine readable 
* compliance, security, and policy requirements
* Based off of ServerSpec

---

# InSpec Example

```
describe service 'ssh-agent' do
  it { should be_running }
end
```

---

# InSpec Example Run

```
$ inspec exec test.rb
.

Finished in 0.00901 seconds (files took 0.98501 seconds to load)
1 example, 0 failures
```

---

# InSpec Remote Run

```
$ inspec exec test.rb -i ~/.aws/YOUR.pem -t ssh://ec2-user@54.152.7.203
```

---

# InSpec Remote Run on Windows

```
$ inspec exec test.rb -t winrm://Admin@192.168.1.2 --password super
```

---

# InSpec Docker Containers

```
$ inspec exec test.rb -t docker://3dda08e75838
```

---

# More info on InSpec

https://github.com/chef/inspec/blob/master/docs/ctl_inspec.rst

---

# InSpec Audit Rules 

* lots of resources to facilitate auditing nodes

---

# InSpec host resource example

```
describe host('example.com', port: 80, proto: 'tcp') do
  it { should be_reachable }
end
```

---

# InSpec login_defs resource example

```
describe login_defs do
  its('PASS_MAX_DAYS') { should eq '180' }
  its('PASS_MIN_DAYS') { should eq '1' }
  its('PASS_MIN_LEN') { should eq '15' }
  its('PASS_WARN_AGE') { should eq '30' }
end

```

---

# [fit] Introduction to Lab 5

Clean any rubocop and foodcritic issues reported. 
Add tests to MongoDB cookbook.

[Lab 5](https://github.com/iennae/crc-training/blob/master/labs/lab_5.md)

![fit](images/standing_cat.png)

---

# Lab 5

Time: 30 minutes

![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/timer.png)

---

# [fit] Introduction to Lab 6

Extending Existing Cookbooks

[Lab 6](https://github.com/iennae/crc-training/blob/master/labs/lab_6.md)

![fit](images/standing_cat.png)

---

# Lab 6

Time: 1 hour

![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/timer.png)



## Lab 4
## Translate our MongoDB cookbook from recipes into resources
Allotted Time: 30 minutes total

[Custom Resource documentation](https://docs.chef.io/custom_resources.html)

In this activity your team will be updating your teamname-mongodb community cookbook to use custom resources.

1. Identify who will do what on the team and pair as needed.
2. Create a custom resource for installing mongodb.
3. Update documentation for teamname-mongodb.
4. Commit teamname-mongodb to github repo.
5. Upload teamname-mongodb cookbook to the class supermarket https://supermarket.reusablechef.com/dashboard.

## Custom Resources 12.5 Style 

* simple extension of Chef
* implemented as part of a cookbook
* follows easy, repeatable syntax patterns
* effectively leverages resources that are built into Chef
* is reusable in the same way as resources that are built into Chef

Defined as ruby file (.rb extension) located in cookbook's resources directory.

```
property :name, RubyType, default: 'value'

load_current_value do
  # some Ruby
end

action :name do
 # a mix of built-in Chef resources and Ruby
end

action :name do
 # a mix of built-in Chef resources and Ruby
end


```

In the following example, this resource would create a 
Example:

```
resource_name :httpd

property :homepage, String, default: '<h1>Hello world!</h1>'

load_current_value do
  if ::File.exist?('/var/www/html/index.html')
    homepage IO.read('/var/www/html/index.html')
  end
end

action :create do
  package 'httpd'

  service 'httpd' do
    action [:enable, :start]
  end

  file '/var/www/html/index.html' do
    content homepage
  end
end
```

Example of using this resource

```
httpd 'build website' do
  homepage '<h1>Welcome to the Example Co. website!</h1>'
  action :create
end

```

[Walk-through of creating custom resources.](https://docs.chef.io/decks/custom_resources.html)

## Outcomes 

* custom resource file in resources directory of cookbook
* simplified recipe in cookbook
* updated cookbook to the class supermarket
* cookbook committed to github

\pagebreak

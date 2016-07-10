# Maintainable Chef
Allotted Time: 30 minutes total

1. Identify who will do what on the team and pair as needed.
2. Add the ubuntu platform to your kitchen configuration, and update your cookbook to handle the new platform.
2. Clean any rubocop and foodcritic issues reported. 
3. Add inspec integration tests to MongoDB cookbook.

## Adding Ubuntu platform

Update the `.kitchen.docker.yml` in your cookbook. 

To platforms section, add 

  - name: ubuntu-16.04

Check the [installation guide](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/) for mongodb to see Ubuntu requirements.


## Linting 

Run _foodcritic_, the chef linting tool from within your team's mongodb cookbook. 

```
foodcritic .
```

Run _rubocop_, the ruby linting tool from within your team's mongodb cookbook.

```
rubocop .
```

Clean up any errors that you discover with your mongodb cookbook.
 
## Integration Tests 

Add inspec tests to your team's mongodb cookbook.

https://github.com/chef/inspec 

## Outcomes

* No foodcritic or rubocop errors.
* Integration test added to cookbook.
* cookbook committed to github
* A successful update to your teams assigned cookbook to the class supermarket https://supermarket.reusablechef.com/dashboard.
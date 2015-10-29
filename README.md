# kheler
khelper, The Kitchen Helper.
Speed up the test-kitchen process by not uploading all the files before running
chef-client. This starts the chef-client run against the chef-zero on the server.

## Usage
After converging in test-kitchen (minimally the converge must upload the cookbooks
and start the recipe runs) use khelper to login,scp or run chef-client

  * khelper --help
  * khelper login --help
  * khelper scp --help
  * khelper chef-client --help

## use case
Converge your cookbook, make any changes to your cookbook or an upstream
cookbook (av-jas, av-java, etc). Use khelper login to verify a setting

  * khelper login -u root

Realize you need to update the av-jas cookbook and your local cookbook.

  * khelper scp -c .
  * khelper scp -c ../aw-jas
  * khelper chef-client

Edit your databag to change the password and upload the data_bags

  * khelper scp -d ../data_bags
  * khelper chef-client

## sample commands

  * khelper login -u root
  * khelper scp -c .
  * khelper scp -d ../data_bags
  * khelper chef-client

### Options

These options are availalbe for all sub commands

# vagrant-rails-on-digitalocean

Create Ruby on Rails droplet on DigitalOcean via vagrant.

# Resources
* https://github.com/mitchellh/vagrant
* https://github.com/smdahlen/vagrant-digitalocean

# DigitalOcean API Reference
* https://developers.digitalocean.com/documentation/v2/

# Run droplet

```
$ vagrant up --provider=digital_ocean
```

# Get latest ruby version via RVM

```
$ rvm get stable && rvm install ruby
$ gem install bundler
$ gem install unicorn
```

Modify Ruby version used by unicorn.

```
vi /etc/default/unicorn
```

```
PATH=/usr/local/rvm/rubies/ruby-x.x.x/bin
export GEM_HOME=/usr/local/rvm/gems/ruby-x.x.x
export GEM_PATH=/usr/local/rvm/gems/ruby-x.x.x
DAEMON=/usr/local/rvm/gems/ruby-x.x.x/bin/unicorn
```

# Value for `provider.image`

```
$ curl -X GET -H 'Content-Type: application/json' -H 'Authorization: Bearer {your_token}' "https://api.digitalocean.com/v2/images?type=application" | jq ".images[].slug"

"ruby-on-rails"
"wordpress"
"magento"
"freebsd-amp"
"drone"
"docker"
"cassandra"
"phpmyadmin"
"ghost"
"mongodb"
"drupal"
"owncloud"
"gitlab"
"django"
"mumble"
"mediawiki"
"node"
"lamp"
"lemp"
"mean"
```

# Value for `provider.region`

```
✗ curl -X GET -H 'Content-Type: application/json' -H 'Authorization: Bearer {your_token}' "https://api.digitalocean.com/v2/regions" | jq ".regions[].slug"

"nyc1"
"ams1"
"sfo1"
"nyc2"
"ams2"
"sgp1"
"lon1"
"nyc3"
"ams3"
```

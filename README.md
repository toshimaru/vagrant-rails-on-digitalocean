# vagrant-rails-on-digitalocean

Create Ruby on Rails droplet on DigitalOcean via vagrant.

# Resources
* https://github.com/mitchellh/vagrant
* https://github.com/smdahlen/vagrant-digitalocean

# DigitalOcean API Reference
* https://developers.digitalocean.com/documentation/v2/

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

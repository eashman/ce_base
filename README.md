This is a Rails root directory for Community Engine 'edge' branch (for Rails 4.2):  
https://github.com/bborn/communityengine/tree/edge

How to use (to run CommunityEngine)
--------------------------------

### 1. Preparation

Here, we assume Debian (Jessie) is running.
Install the following packages:
```
# apt-get install git imagemagick openssl 
```
and one of the JavaScript runtimes on execjs' supported list:  
https://github.com/sstephenson/execjs

We recommend to use `rbenv` as Ruby environment if you can.  
Install the lasest version of `ruby-2.0.0`.  
Then, install `bundler`.

### 2. Install and run CommunityEngine

For a user with rbenv:
```
$ git clone https://github.com/taro-k/ce_base.git ce-edge-test
$ cd ce-edge-test
$ bundle install --path vendor/bundle
$ bundle exec rake community_engine:install:migrations
$ bundle exec rake db:migrate
$ cp config/secrets.yml.sample config/secrets.yml
$ bundle exec rails server
```
For a user without rbenv:
```
$ git clone https://github.com/taro-k/ce_base.git ce-edge-test
$ cd ce-edge-test
$ bundle install --path vendor/bundle
$ bin/rake community_engine:install:migrations
$ bin/rake db:migrate
$ cp config/secrets.yml.sample config/secrets.yml
$ bin/rails server
```

### 3. Increasing security and customization

Update your secret keys in `config/secrets.yml`
with new keys generated by
```
$ bundle exec rake secret
```
or
```
$ bin/rake secret
```
Edit `config/application_config.rb` to customize your site.


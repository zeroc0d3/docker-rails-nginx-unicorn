# docker-rails-nginx-unicorn
[![](https://images.microbadger.com/badges/image/zeroc0d3/docker-rails-nginx-unicorn.svg)](https://microbadger.com/images/zeroc0d3/docker-rails-nginx-unicorn "Layers") [![](https://images.microbadger.com/badges/version/zeroc0d3/docker-rails-nginx-unicorn.svg)](https://microbadger.com/images/zeroc0d3/docker-rails-nginx-unicorn "Latest")

Docker Rails + Nginx + Unicorn (from Ubuntu 16.04 &amp; Ruby 2.4.0). Easy useable docker for rails. less configuration, affordable production.

## What's include

* unicorn, nginx, foreman
* mysql, postgresql lib

# Usage

* Create `Dockerfile` to your project and paste below code.

```
# Dockerfile
FROM zeroc0d3/docker-rails-nginx-unicorn

MAINTAINER ZeroC0D3 Team (zeroc0d3.0912@gmail.com)

EXPOSE 80
```

* Add `unicorn` gem (add/uncomment `gem 'unicorn'` in `Gemfile`)

## Build and run docker

```
# build your dockerfile
$ docker build -t your/project .

# run container
$ docker run -d -p 80:80 -e SECRET_KEY_BASE=secretkey your/project
```

# Custom pre-install lib

if your rails app required pre-install lib like imagemagick (or others) use [`rails-nginx-unicorn-pro`](https://github.com/zeroc0d3/docker-rails-nginx-unicorn-pro)


# Customize Nginx, Unicorn, Foreman config

## Nginx

```
# your Dockerfile
...
ADD config/your-custom-nginx.conf /etc/nginx/sites-enabled/default
...
```

## Unicorn

place your unicorn config to `config/unicorn.rb`

## foreman

place your Procfile to app root


# Use a specific version of Ruby, Nginx

Change `FROM` instruction your Dockerfile

```
# Dockerfile
FROM zeroc0d3/docker-rails-nginx-unicorn:ruby2.4.0-nginx1.10.3
...
```

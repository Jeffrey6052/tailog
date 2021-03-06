# TAILOG

[![Gem Version](https://img.shields.io/gem/v/tailog.svg)](https://rubygems.org/gems/tailog)
[![Build Status](https://img.shields.io/travis/bbtfr/tailog.svg)](http://travis-ci.org/bbtfr/tailog)
[![Code Climate](https://img.shields.io/codeclimate/github/bbtfr/tailog.svg)](https://codeclimate.com/github/bbtfr/tailog)

Sinatra App to serve log in browser

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'tailog'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install tailog

## Usage

In `config.ru`

```ruby
require 'tailog'

run Rack::URLMap.new(
  '/'         => Your::App,
  '/tailog'   => Tailog::App
)
```

You can turn on authentication by adding:

```ruby
require 'tailog'

Tailog::App.use Rack::Auth::Basic do |username, password|
  username == 'username' && password == 'password'
end

run Rack::URLMap.new(
  '/'         => Your::App,
  '/tailog'   => Tailog::App
)
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/bbtfr/tailog. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.


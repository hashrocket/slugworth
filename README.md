# Slugworth

[![Gem Version](https://badge.fury.io/rb/slugworth.png)](http://badge.fury.io/rb/sluggle)
[![Build Status](https://travis-ci.org/mattpolito/slugworth.png?branch=master)](https://travis-ci.org/mattpolito/sluggle)
[![Code Climate](https://codeclimate.com/github/mattpolito/slugworth.png)](https://codeclimate.com/github/mattpolito/sluggle)

Simple slug functionality for your ActiveRecord objects

## Installation

Add this line to your application's Gemfile:

```shell
  gem 'slugworth'
```

and then execute

```shell
  bundle
```

or

install it yourself with

```shell
  gem install slugworth
```

## Usage

Getting started is easy! Just ensure that your model has a database column of type `String` called `slug`

To use just add two declarations to your module and away you go!

```ruby
class User < ActiveRecord::Base
  include Slugworth
  slugged_with :name
end
```

This provides most of the default slug functionality you would need.

* A finder `.find_by_slug` is provided. This will, of course, do what you expect and find a single record by the slug attribute provided. However, it will throw an `ActiveRecord::RecordNotFound` exception... if not found.
* `#to_param` has been defined as a paramaterized version of the attribute declared to `slugged_with`.
* Validations stating that slug is present and unique in the database.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

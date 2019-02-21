# Thor::Repl

Easily create a REPL for any [Thor CLI](https://github.com/erikhuda/thor)

[![Maintainability](https://api.codeclimate.com/v1/badges/2b2cd7ca322d7e1c1370/maintainability)](https://codeclimate.com/github/mikfreedman/thor_repl/maintainability)
[![Gem Version](https://badge.fury.io/rb/thor_repl.svg)](https://badge.fury.io/rb/thor_repl)
[![CircleCI](https://circleci.com/gh/mikfreedman/thor_repl.svg?style=shield)](https://circleci.com/gh/mikfreedman/thor_repl)

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'thor_repl'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install thor_repl

## Usage

This Gem assumes you have a class that inherits from `Thor` describing your commands in your CLI, as described in Thor's [Getting Started guide](https://github.com/erikhuda/thor/wiki/Getting-Started#a-simple-example)

Add a new method to trigger an interactive console like so:

```ruby
require 'thor_repl'

class MyCLI < Thor
  desc "interactive", "interactive console"
  def interactive
    ThorRepl.start(self.class, prompt: "my-cli>")
  end
end
```

Then, from your command line enjoy REPL goodness!

```bash
$ ./bin/my-cli interactive
my-cli> help
```

Checkout [/example](example) for a working example of this gem.

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/thor_repl. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the Thor::Repl project’s codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/[USERNAME]/thor-repl/blob/master/CODE_OF_CONDUCT.md).

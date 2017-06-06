# KanjiMaster

[![Gem Version](https://badge.fury.io/rb/kanji_master.svg)](https://badge.fury.io/rb/kanji_master)
[![Build Status](https://travis-ci.org/ToUMenu/kanji-master.svg?branch=master)](https://travis-ci.org/ToUMenu/kanji-master)
[![Coverage Status](https://coveralls.io/repos/github/ToUMenu/kanji-master/badge.svg?branch=master)](https://coveralls.io/github/ToUMenu/kanji-master?branch=master)

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'kanji_master'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install kanji_master

## Usage

### Reader

```ruby
reader = KanjiMaster::Reader.new
reader.alphabet?('word')
# => true
reader.maybe_kanji?('漢字')
# => true

analyzed_text = reader.read_text('漢字alphabet898989')
analyzed_text.numbers    # => "898989"
analyzed_text.alphabets  # => "alphabet"
analyzed_text.kanjis     # => "漢字"
```

### Counter

```ruby
counter = KanjiMaster::Counter.new
counter.kanji(3)
# => '三'
```

### Converter

```ruby
converter = KanjiMaster::Conveter.new
converter.kana('すし') #=> 'スシ'
converter.kana('sushi') #=> 'スシ'
converter.hira('スシ') #=> 'すし'
converter.hira('sushi') #=> 'すし'
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/kanji_master. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.


## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

# BoardEffect
<a href="http://boardeffect.com"><img src="http://www.boardeffect.com/wp-content/uploads/2015/10/BE.png" alt="BoardEffect" width="250"></a>

Ruby client for [Version 3 of the BoardEffect API].

## Supported Ruby Versions

Ruby 1.9.3 or greater

## Installation ##

Install BoardEffect as a gem:

```
gem install boardeffect
```

or add to your Gemfile:

```ruby
# Gemfile
gem 'boardeffect'
```

and run `bundle install` to install the dependency.

## Overview ##

You can use the boardeffect gem to communicate with the BoardEffect API by first logging in as an administrator and going to Settings -> Integrations -> Custom Applications and setting up an API Key. Once you have the API key, you can interact with any of the calls provided at https://yourportalname.boardeffect.com/apidocs/


## Examples ##
```ruby
require 'boardeffect'

boardeffect = BoardEffect::Client.new(access_token: 'API KEY', host: 'https://yourportalname.boardeffect.com/')

# Create a workroom announcement
announcement = boardeffect.create_announcement({title: "This is a test from the console", body: "This is a body description"}, { workroom_id: 2 })
p announcement.inspect

# Get a list of workroom events
events = boardeffect.get_events(workroom_id: 2 )
p events[:data].inspect
```

## Support

Bug reports and feature requests should be filed on the [GitHub issue tracking page](https://github.com/magicmarkker/boardeffect/issues). 

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new pull request
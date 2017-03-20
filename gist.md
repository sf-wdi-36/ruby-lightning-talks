# HTTP Party

The power of api requests, made easy with HTTP Party!

## What's So Great About HTTP Party?

* Setting all the headers!
* Making life easy with apis!
* JSON on JSON on JSON!

## Why use HTTP Party

From Treehouse: *"When you’re developing with Ruby, it’s pretty inevitable that at some point you come across an HTTP API that doesn’t have a gem available. While writing Hopefully Sunny I ran into just that situation with World Weather Online’s weather API. It’s often really tempting to go searching for a different API to use instead, but it’s actually not so hard to just write your own wrapper library. Let’s take a look at one of my favorite libraries for working with HTTP APIs, HTTParty, and in the process we’ll figure out how to write our own simple API wrapper libraries."*

We've used plenty of HTTP APIs in our MEAN stack days; this lets us use all the same APIs in Ruby, and gives us a nice wrapper to make those calls (what used to be AJAX calls) in Ruby.
## Demo the awesomeness of this gem!

> At this stage of your presentation, you would probably show us your demo app that uses httparty calls to these two API endpoints. *

* `httparty "https://api.stackexchange.com/2.2/questions?site=stackoverflow"`
* `httparty "http://food2fork.com/api/search?key=ac89596132bf565718f0859218dadf7f&q=shredded%20cheese"`

## Examples

Need to send authorization tokes and ids?!

```Ruby
auth = {
  user_id: "dt_SAMPLETOKENd88ffc342dde5c195df4019f90d6ed",
  token: "super_s3cr3t_h@$hed_t0k3n_h3Re"
}
options = { basic_auth: auth }

result = HTTParty.get("https://api.stackexchange.com/2.2/questions?site=stackoverflow", options)
```

**Or**

```Ruby
key = "ac89596132bf565718f0859218dadf7f"

HTTParty.get("http://food2fork.com/api/search?key=" + key + "&q=shredded%20cheese")
```

**Finally, the official setup in RoR**

```Ruby
require 'httparty'

class Twitter
  include HTTParty
  base_uri 'twitter.com'
  basic_auth 'username', 'password'
end

puts Twitter.post('/statuses/update.json', :query => {:status => "It's an HTTParty and everyone is invited!"}).inspect
```

## Setup?

Just do: `gem install httparty`

If you want to use this in a rails app, be sure to add the gem to your Gemfile.

## Resources

* [Github and Docs](https://github.com/jnunemaker/httparty)
* [Treehouse blog about setup](http://blog.teamtreehouse.com/its-time-to-httparty)

##Zero to API Hero: Consuming 3rd Party APIs Like a Pro!

Just like there’s an app for that, there’s an API for that! But not all APIs are created equal, and some APIs are harder to work with than others. In this #RailsConf 2016 talk, I will walk through some common gotchas developers encounter when consuming a 3rd party API. I will explain why it’s important to familiarize yourself with the API you’re consuming prior to coding, as well as share tools to help you get acquainted with an API much faster. Lastly, I will go over debugging and testing the API you’re consuming!

###API basics

* [Super basic intro to APIs by Zapier](https://zapier.com/learn/apis/)

###HTTP status codes

* [HTTP Statuses](https://httpstatuses.com/): very user friendly website where to read status codes and meaning.
* [RFC 7231](https://tools.ietf.org/html/rfc7231): the spec outlining status codes.
* [W3.org](https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html): Status code definitions by the W3, a little less dense than the actual spec.

###HTTP clients / libraries

* [HTTParty](https://github.com/jnunemaker/httparty)
* [Faraday](https://github.com/lostisland/faraday)
* [HTTP: The Gem!](https://github.com/httprb/http)
* [Great post on HTTP libraries by Julia Evans](http://jvns.ca/blog/2016/03/04/whats-up-with-ruby-http-libraries/)
* [Comparison of Ruby HTTP libraries by Hiroshi Nakamura](http://www.slideshare.net/HiroshiNakamura/rubyhttp-clients-comparison)

###Sample calls

####No auth required calls

Try making these calls in cURL:

`https://api.meetup.com/2/events?key=APIKEY?group_urlname=GROUP-NAME?sign=true`

`http://omdbapi.com/?s=MOVIE-NAME`

####Oauth 1.0 call

This call to the Twitter API requires Oauth 1.0 HMAC-SHA1. Try using POSTMAN to make this call (you must sign up for a Twitter API key).

Base url: `https://api.twitter.com/1.1/users/show.json?`

Params: `screen_name=USERNAME`

Using the Authorization builder, pass in your consumer key and secret. Timestamp, nonce, and version should be selected / pre-populated. Make sure "encode oauth signature" is checked. Click on "update request" to populate this info into the call.

####Oauth Rails example

* [Sample app](https://github.com/cecyc/sample-cio-app) using Context.IO API to test authenticating a user with OAuth.

###Tools for testing / debugging

* [VCR](https://github.com/vcr/vcr)
* [Mockbin](http://mockbin.com/)
* [Request Bin](http://requestb.in/)
* [Runscope](https://www.runscope.com/)

websocket-client-simple
=======================
Simple WebSocket Client for Ruby

- https://github.com/shokai/websocket-client-simple
- https://rubygems.org/gems/websocket-client-simple

[![Build Status](https://travis-ci.org/shokai/websocket-client-simple.png)](https://travis-ci.org/shokai/websocket-client-simple)


Installation
------------

    gem install websocket-client-simple


Usage
-----
```ruby
require 'rubygems'
require 'websocket-client-simple'

ws = WebSocket::Client::Simple.connect 'ws://example.com:8888'

ws.on :message do |msg|
  puts msg.data
end

ws.on :open do
  ws.send 'hello!!!'
end

ws.on :close do |e|
  p e
  exit 1
end

loop do
  ws.send STDIN.gets.strip
end
```


Sample
------
[websocket chat](https://github.com/shokai/websocket-client-simple/tree/master/sample)


Test
----

    % gem install bundler
    % bundle install
    % export WS_PORT=8888
    % rake test


Contributing
------------
1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

mruby-esp32-wifi
============

Wi-Fi library for mruby-esp32.

## Installation
Add the line below to your `build_config.rb`:

```ruby
  conf.gem :github => 'mruby-esp32/mruby-esp32-wifi'
```

## Example
```ruby
puts "Getting ready to start wifi"

wifi = ESP32::WiFi.new

wifi.on_connected do |ip|
  puts "Connected: #{ip}"
end

wifi.on_disconnected do
  puts "Disconnected"
end

puts "Connecting to wifi"
wifi.connect('SSID', 'password')

#
# Loop forever otherwise the script ends
#
while true do
  mem = ESP32::System.available_memory() / 1000
  puts "Free heap: #{mem}K"
  ESP32::System.delay(10000)
end
```

## License

Copyright (c) 2016 Carson McDonald

Permission is hereby granted, free of charge, to any person obtaining a 
copy of this software and associated documentation files (the "Software"), 
to deal in the Software without restriction, including without limitation 
the rights to use, copy, modify, merge, publish, distribute, sublicense, 
and/or sell copies of the Software, and to permit persons to whom the 
Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in 
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR 
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, 
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE 
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER 
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING 
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER 
DEALINGS IN THE SOFTWARE.

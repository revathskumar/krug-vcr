##  setup

```ruby
# test/test_helper.rb
require 'vcr'
require 'webmock/minitest'

VCR.configure do | c |
    c.cassette_library_dir = 'test/fixtures/vcr_cassettes'
    c.hook_into :webmock
end
```

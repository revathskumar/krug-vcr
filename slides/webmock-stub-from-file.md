## stubbing from file

```ruby
# test/test_helper.rb
require 'webmock/test_unit'

class ActiveSupport::TestCase
    def load_fixtures name
        path = File.join(Rails.root, "test", "fixtures", "#{name}.json")
        return nil unless File.exists?(path)
        File.read path
    end
end
```
<br>
```ruby

stub_request(:any, "www.example.com").
  to_return(:body => load_fixtures('get_products'), :status => 200)
```

##  stubbing

```ruby
stub_request(:post, "www.example.com").
  with(:body => {:data => {:a => '1', :b => 'five'}})
```
<br>
```ruby
stub_request(:get, "www.example.com").
    to_return(body: "{:data => {:a => '1', :b => 'five'}}", status: 200)
```

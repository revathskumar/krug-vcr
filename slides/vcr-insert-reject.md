```ruby
class UsersControllerTest < ActionController::TestCase
  def setup
    VCR.insert_cassette 'users', record: :new_episodes
  end

  def teardown
    VCR.eject_cassette 'users'
  end

  ...
end
```

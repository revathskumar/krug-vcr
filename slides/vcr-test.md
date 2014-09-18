
```ruby
VCR.use_cassette 'carts/empty', record: :new_episodes do
  get :show, format: :json

  assert_response :success
  assert_template 'show.json'
  assert_equal 0, JSON.parse(@response.body)['count']
end
```

##  Request matching

```ruby
VCR.use_cassette 'carts/empty', record: :new_episodes,
    match_requests_on: [:method, :uri, :body] do
  get :show, format: :json

  assert_response :success
  assert_template 'show.json'
  assert_equal 0, JSON.parse(@response.body)['count']
end
```
* :method
* :uri
* :body
* :host
* :path
* :headers
* :query

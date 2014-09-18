
```ruby
  test 'remove item' do
    VCR.use_cassette 'carts/delete', record: :new_episodes do
      item = {"id"=>"2816", "uri"=>"",..}
      store = {"id"=>"prestige", "name"=>"Prestige Smart Kitchen"}
      post :create, format: :json, item: item, store: store_fixture


      delete :destroy, format: :json, id: 2816, store: 'prestige'

      assert_response :success
      assert_template 'show.json'
      assert_equal 0, JSON.parse(@response.body)['count']
    end
  end
```

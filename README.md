# README

A simple Rails app with Dresssed-ives integration.

0. `cp config/env.sample.rb config/env.rb`
0. Edit `config/env.rb` to have YOUR dresssed license key (the last segment of the source URL)
0. `bundle install`
0. `bin/rails db:migrate`
0. `bin/rails s`

You can see the dashboard at the root path.

Try `/users` to see scaffolding within the Side nav layout. To achieve this I just took the following snippet out of the `application` layout:

```eruby
  <div class="page-header">
    <div class='container'>
      <div class="row row-same-height">
        <div class="col-md-12 col-sm-height col-middle">
          <h2 class='m0'><%= @title %></h2>
          <%= yield :description %>
        </div>
        <div class="col-md-2 col-sm-height col-middle">
          <%= yield :actions %>
        </div>
      </div>
    </div>
  </div><!-- /.page-header -->
```

You can then use `content_for` to inject a description text or anything like buttons into the action field.

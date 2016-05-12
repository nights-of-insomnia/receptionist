# Receptionist

Needing to show users admin-generated alerts and messages? This is for you.

TODO: Delete this and the text above, and describe your gem

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'receptionist'
```

And then execute:

    $ bundle

## Usage

Generate the initializer file and the migrations needed with:

    $ rails generate receptionist:install

This will generate: migrations, an initializer file and build the engine routes on your routes.rb file.

Set config.authorization_required to false if you don't need authorization to manage messages

If you need authorization, set a boolean helper_method that will be used to check authorization
Set config.check_authorization_method = :your_method

Run the migrations with:

    $ bundle exec rake db:migrate

Start up the server and head to /receptionist/messages
Create a message, head over to whichever view you want to place your message on (application.html.erb?) and add
```ruby
<%= receptionist_latest %>
```

Run the page and you should see something like
<p class='info'>Your Message</p>

You can change the template for the message by creating a template_for_receptionist method on your application controller like this:
```ruby
module ApplicationHelper

  def template_for_receptionist(message, message_type)
    content_tag(:p, message, class: message_type)
  end
end
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake test` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/noitesdeinsonia/receptionist. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.


## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
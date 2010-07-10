# Heroku::Autoscale

## Installation

    # Gemfile
    gem 'heroku-autoscale'

## Usage (Rails 2.x)

    # config/environment.rb
    config.middleware.use Heroku::Autoscale,
      :username  => ENV["HEROKU_USERNAME"],
      :password  => ENV["HEROKU_PASSWORD"],
      :app_name  => ENV["HEROKU_APP_NAME"],
      :min_dynos => 2,
      :max_dynos => 5,
      :queue_wait_low  => 100,  # milliseconds
      :queue_wait_high => 5000, # milliseconds
      :min_frequency   => 10    # seconds
    
## Usage (Rails 3 / Rack)

    # config.ru
    use Heroku::Autoscale,
      :username  => ENV["HEROKU_USERNAME"],
      :password  => ENV["HEROKU_PASSWORD"],
      :app_name  => ENV["HEROKU_APP_NAME"],
      :min_dynos => 2,
      :max_dynos => 5,
      :queue_wait_low  => 100,  # milliseconds
      :queue_wait_high => 5000, # milliseconds
      :min_frequency   => 10    # seconds
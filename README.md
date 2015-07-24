## Home Wrecker
home_wrecker is a gem meant for load testing that utilizes siege https://www.joedog.org/siege-home/

Make sure you have siege installed with `brew install siege` or some other flavor of install

This is currently working with siege 3.0.7, ruby 2.0.1


install the gem
```sh
  $ gem install home_wrecker`
```

you should see
  ```sh
  $ confing file created. Please update config.rb and try again"
  ```
open the config.rb file that was created and update for your needs
```ruby
  #!/usr/bin/env ruby
  $endpoints = [
    # example 'users/13',
    # example 'users/4',
  ]
  $urls = [
    #'https://api.example.com',
    #'https://api.example2.com'
  ]
  # $extra_args = " example: -H 'Authorization: Token token=\"example_token\"' -H 'X_API_EMAIL: example@example.com'"
  $verbose = false
  $seconds = '3'
```
run the home_wrecker wreck command
```sh
$ home_wrecker wreck
```
output should be
```sh
$ hitting https://api.example.com/users/13 for 3 seconds
$ hitting https://api.example2.com/users/13 for 3 seconds
$ hitting https://api.example.com/users/4 for 3 seconds
$ hitting https://api.example2.com/users/4 for 3 seconds
...
```
then a fomatted html file should open, showing you the results of the test

## TODO:
Find a better way to assign the variables.  Globals probably aren't the best. Perhaps a yml file?

Prettier html
Remove verbose option and use javascript to hide / show requests






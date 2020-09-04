# Ruby on Rails Tutorial sample application

This is the sample application for
[*Ruby on Rails Tutorial:
Learn Web Development with Rails*](http://www.railstutorial.org/)
by [Michael Hartl](http://www.michaelhartl.com/).

## License

All source code in the [Ruby on Rails Tutorial](http://railstutorial.org/)
is available jointly under the MIT License and the Beerware License. See
[LICENSE.md](LICENSE.md) for details.

## Getting started

### REQUIRED RUBY VERSION: >= 2.2.2

#### To get started with the app, clone the repo and then install the needed gems:
Without sudo:
```
$ bundle install --path vendor/bundle
```
With sudo:
```
$ sudo bundle install
```
#### Next, migrate the database:
Without sudo:
```
$ bundle exec rails db:migrate
```
With sudo:
```
$ sudo rails db:migrate
```
#### Then, seed database for some data
Without sudo:
```
$ bundle exec rails db:seed
```
With sudo:
```
$ sudo rails db:seed
```

#### If the all steps passed, you'll be ready to run the app in a local server:
Without sudo:
```
$ bundle exec rails server
```
With sudo:
```
$ sudo rails s
```
##### Additional info
```
$ bundle exec rails server
```
or
```
$ sudo rails s
```
equals to 
```
$ bundle exec puma -C config/puma.rb
```
or
```
$ sudo puma -C config/puma.rb
```

## Login/Password
```
email: "example@railstutorial.org"
password: "foobar"
```
For more information, see the
[*Ruby on Rails Tutorial* book](http://www.railstutorial.org/book).

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

## Useful tips

#### Don't forget to install sqlite

#### Install Ruby with rbenv in Vagrant provisioning
```
## Do not install rbenv under SUDO
sudo apt update ## Update system
sudo apt install git curl libssl-dev libreadline-dev zlib1g-dev autoconf bison build-essential libyaml-dev libreadline-dev libncurses5-dev libffi-dev libgdbm-dev gcc make nodejs -y ## install dependencies
## Also dont forget to install `sqlite`
git clone https://github.com/sstephenson/rbenv.git ~/.rbenv ## install rbenv
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build ## see https://github.com/rbenv/rbenv Basic Github Checkout for this and next some steps
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
. ~/.bashrc
## `sudo -H -u vagrant bash -i -c` is using because provision doesn't see aliases for commands in way like simple command `rbenv install 2.6.0` 
sudo -H -u vagrant bash -i -c 'rbenv install 2.6.0' ## rbenv install ANY_OTHER_VERSION_YOU_LIKE
sudo -H -u vagrant bash -i -c 'rbenv global 2.6.0' ## use installed version
sudo -H -u vagrant bash -i -c 'gem install bundle' ## this is for installing gems in future
```

#### Install Rails app dependencies in provisioning and service it
```
git clone https://github.com/lwwwr/sample_app.git
cd sample_app
mkdir tmp/pids
sudo -H -u vagrant bash -i -c 'bundle install' && cd ../ ## Like in previous case with provision
## Also, another one step - make `rails db:migrate`
## And, `rails db:seed`
## Make Servicefile for application
## Dont forget to make symbolic link for servicefile
## Reload daemon and start service
```

#### Tips for Rails app servicefile
```
## Service runs under root
## So use full pathes to puma, because root user have no rails app dependency installations.
## By default, Rails app runs on 3000 port
## Use pid file for checking rails app process id
## For running app, use: /path_to_bundle exec puma -C /path_to_app/config/puma.rb/puma.rb
## For stopping, lets google about pumactl and pid
## For restarting, lets google about pumactl and phased-restart
## Dont forget to forward output and errors in log files
```
## Login/Password
```
email: "example@railstutorial.org"
password: "foobar"
```
For more information, see the
[*Ruby on Rails Tutorial* book](http://www.railstutorial.org/book).

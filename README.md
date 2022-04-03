# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...




reference
https://www.railstutorial.org/book
https://github.com/rvm/ubuntu_rvm
https://docs.microsoft.com/en-us/windows/dev-environment/javascript/nodejs-on-wsl


curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

nvm install 16.13.0

sudo apt-add-repository -y ppa:rael-gc/rvm
sudo apt-get update
sudo apt-get install rvm

sudo usermod -a -G rvm $USER


rvm install 2.7.5

echo "gem: --no-document" >> ~/.gemrc

gem install rails -v 6.1.4.6

gem install bundler -v 2.2.17

# skip following 2 lines

source <(curl -sL https://cdn.learnenough.com/resize)
source <(curl -sL https://cdn.learnenough.com/yarn_install)


curl -o- -L https://yarnpkg.com/install.sh | bash

# create lock file

 yarn install --check-files

 cd

 mkdir environment 
 cd environment


 rails _6.1.4.6_ new hello_app --skip-bundle



https://www.railstutorial.org/book#sec-bundler

app/	Core application (app) code, including models, views, controllers, and helpers
app/assets	Applications assets such as Cascading Style Sheets (CSS) and images
bin/	Binary executable files
config/	Application configuration
db/	Database files
doc/	Documentation for the application
lib/	Library modules
log/	Application log files
public/	Data accessible to the public (e.g., via web browsers), such as error pages
bin/rails	A program for generating code, opening console sessions, or starting a local server
test/	Application tests
tmp/	Temporary files
README.md	A brief description of the application
Gemfile	Gem requirements for this app
Gemfile.lock	A list of gems used to ensure that all copies of the app use the same gem versions


# evalute GemFile

# continue with installation
cd hello_app/
bundle _2.2.17_ update
bundle _2.2.17_ install

# install javascript package manager 
rails webpacker:install 

# add following to the end of (before last end) development.rb to allow connections from local
  # Allow connections to local server.
  config.hosts.clear

# start the server
rails server

# add hello action to controller ->  controllers/application_controller.rb

  def hello
    render html: "hello, world!"
  end

  def goodbye
    render html: "goodbye, world!"
  end


# add config/routes.rb; the controller name is application and the action name is hello

root 'application#hello'



# install heroku

source <(curl -sL https://cdn.learnenough.com/heroku_install)


# new toy app
rails _6.1.4.6_ new toy_app --skip-bundle
bundle _2.2.17_ config set --local without 'production'
bundle _2.2.17_ install


# git initial setup
git config --global user.name "tofumocha"
git config --global user.email chang.weicheng@gmail.com
git config --global init.defaultBranch main
git config --global alias.co checkout
git config --global credential.helper "cache --timeout=86400"

# git

$ git init
$ git add -A
$ git commit -m "Initialize repository"


# github.com setup



git remote add origin https://github.com/tofumocha/toy_app.git
% git branch -M main
git push --set-upstream origin master
% git push -u origin main

# modify application_controller.rb and routes.rb

git commit -am "Add hello"


# install heroku
source <(curl -sL https://cdn.learnenough.com/heroku_install)


# modify Gemfile

group :production do
  gem 'pg', '1.2.3'
end



# deploy
heroku create
git push && git push heroku


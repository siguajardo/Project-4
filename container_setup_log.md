Commands to get a container up and running (with Docker installed, of course):
# Getting started
## Starting the container
(From docker-machine)
* `docker pull ubuntu:14.04` # Get Ubuntu 14.04
* `docker run -ti ubuntu:14.04 bash` # Start a new container from the ubuntu:14.04 image
* `sudo apt-get install vim` OR `sudo apt-get install nano` # Getting a text editor
* `sudo apt-get install curl`

## Setting up Ubuntu
(now we're inside the container we just made)
* `sudo apt-get update` # Update the apt cache
* `sudo apt-get install git` # Install git
* `git --version` # To see if git installed correctly

## Setting up Ruby and RVM
following [this tutorial using RVM](http://railsapps.github.io/installrubyonrails-ubuntu.html)
(This command will probably throw an error, but it will recommend a fix)
* `\curl -L https://get.rvm.io | bash -s stable --ruby` # Installing RVM
* `source /usr/local/rvm/scripts/rvm`
* `gem update --system`
* `rvm gemset use global`
* `gem update`
(optional. This will not download the documentation for ruby gems. Should speed up downloads)
* `echo "gem: --no-document" >> ~/.gemrc`

### Installing NodeJS
* `sudo apt-get install nodejs`
(and set nodejs to path)

### Install Bundler
* `gem install bundler`
* `bundle --version`

### Install Nokogiri
* `gem install nokogiri`

## Finishing Ruby and Setting up Rails
* `rvm install ruby-2.3.1` # Install Ruby-2.3.1
* `rvm use ruby-2.3.1@rails5.0 --create`
* `gem install rails` # Installing rails
* `rails -v` # See if rails installed correctly

## Setting up Locomotive
* `cd ~`
* `git clone git://github.com/locomotivecms/steam.git` # Clone Steam
* `git clone git://github.com/locomotivecms/wagon.git` # Clone Wagon
* `cd wagon`
* `bundle install`
* `bundle exec rake spec` # Run the built-in tests
* `bundle exec bin/wagon serve spec/fixtures/default` # Run a rails server
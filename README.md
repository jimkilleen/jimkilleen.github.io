# JimKilleen.com
Jim's site reboot.

## Getting Started
This guide is meant for building the site on a Windows machine using Ruby and Jekyll.

### Installations

#### Install Ruby via RubyInstaller
* Download the latest x64 version of Ruby from <https://rubyinstaller.org/downloads/>
 * At the time of this writing, that's `2.3.3 (x64)`
* Run the download
* Accept the license
* Allow the install to go to `C:\tools\ruby23` (trust me, it's easier later)
* Check the box to `Add Ruby Executables to your PATH`
* Complete the installation.

#### Install Ruby DevKit 2
* Download the latest DevKit version from <http://rubyinstaller.org/downloads/>
 * NOTE: The download will be on the left-hand side mid-way down the page, under a heading called "Development Kit"
 * The correct version will say `For Use With Ruby 2.0 and above (x64 - 64 bits only)
* Run the installer. Install to `C:\tools\DevKit2`.

### Environment Setup

#### Ensure Ruby is present on your path
* Open a new command prompt or powershell window
 * Must be new so that the updated `PATH` variable will take effect.
* Run `ruby --version`

You should see a result along the lines of `ruby 2.3.3p222 (2016-11-21 revision 56859) [x64-mingw32]`.

#### Initialize DevKit
* Open a new command prompt or powershell window
* Move to the `C:\tools\DevKit2` directory
* Run `ruby dk.rb init`. 
    This will use one of DevKit's files to initialize itself and create a config file.

#### Add Your Ruby Install to the DevKit Config

* Open the file at `C:\tools\DevKit2\config.yml`
* Add a line for your ruby folder, such as `- C:/tools/ruby23`
 * NOTE: The dash is important. It denotes a list item (YML format). Don't leave it off.
* Save the file.

#### Link KevKit to your Ruby Install
* Open a command prompt or powershell window
* Move to the `C:\tools\DevKit2` directory
* Run `ruby dk.rb install`.

You should see a message about DevKit being installed.

#### Install the Bundler gem
In simplified terms, Bundler is like nuget for Ruby. You'll use it to manage the packages that sit in the `gemfile`.

NOTE: For Github pages setup, you'll rarely have to do much with this, because GitHub pages dependencies all live in the one package which is already in the `gemfile`.

To install bundler, run `gem install bundler` from the command prompt. This should install it globally.

## How to Build and Run this Site Locally
Assuming you've followed the installation steps above, you should be able to do the following:

* Open a command prompt
* Open the root directory of this repository
* Run `bundle install`.
 * The github-pages related bundles should install.
 * If you see any errors at this point, you'll want to stop and dig further.
* Once the gems have installed, run `bundle exec jekyll serve`

After Jekyll builds the site, you'll see it hosted at `http://localhost:4000` (the default).
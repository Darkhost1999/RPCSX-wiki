# RPCSX Wiki

## Installation

- Install Ruby:
We recommend using Ruby Version Manager (RVM) to [Install Ruby](https://rvm.io/rvm/install)

- Clone and set up wiki:
```
git clone https://github.com/RPCSX/wiki
cd wiki
```
Note: Do not run Bundler as root. Installing your bundle as root will break this application for all
non-root users on your machine.
```
gem install bundler
bundle install
```

### Development

- Run Jekyll Server:

Note: Hot reloading is unsupported, refresh the page to see changes.
```
bundle exec jekyll serve
```
### Before Pushing Changes

Run `rubocop` on your local files.

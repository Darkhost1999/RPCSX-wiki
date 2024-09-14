# RPCSX Wiki

## Installation
Tested on Ubuntu WSL
- Update your repository lists and packages:
```
sudo apt update && sudo apt upgrade -y
```

- Install dependencies:
```
sudo apt-get install ruby-full build-essential dh-autoreconf libffi-dev libssl-dev
```

- Clone and set up wiki:
```
git clone https://github.com/RPCSX/wiki
cd wiki
```
Note: Do not run Bundler as root. Installing your bundle as root will break this application for all
non-root users on your machine.
```
gem install bundler
```
```
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

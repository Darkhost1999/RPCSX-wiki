# RPCSX Wiki

This is the repository for hosting and maintaining the RPCSX Wiki.
All documentation or information to help you have the best possible experience using RPCSX is housed here.
You can visit the site at anytime from https://rpcsx.github.io/wiki/

## Compiling the Site for Development or Local Hosting Purposes

- Install Ruby:

We recommend using Ruby Version Manager (RVM) to [Install Ruby](https://rvm.io/rvm/install)

- Clone and set up wiki:

```sh

git clone https://github.com/RPCSX/wiki
cd wiki

```

Note: Do not run Bundler as root. Installing your bundle as root will break this application for all
non-root users on your machine.

```sh

gem install bundler
bundle install
```

### Running the Site for Development or Local Hosting Purposes

- Run Jekyll Server:

Note: Hot reloading is unsupported, refresh the page to see changes.

```sh
bundle exec jekyll serve
```

### Before Pushing Changes to the Repository

Run ```rubocop``` on your local files.

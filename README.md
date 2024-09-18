# homebrew-risingwave

Homebrew tap for [RisingWave](https://github.com/risingwavelabs/risingwave), a distributed SQL database for stream processing.

## Installation

Install [Homebrew](https://brew.sh/) first. Then, tap this repository:

```shell
$ brew tap risingwavelabs/risingwave
```

To install the latest release version:

```shell
$ brew install risingwave
```

Or, to install the latest development version:

```shell
$ brew install risingwave --HEAD
```

You can now start the RisingWave playground and connect to it with the Postgres interactive terminal `psql`:

```shell
$ risingwave playground

# In another terminal...
$ psql -h localhost -p 4566 -d dev -U root
```

### Install old versions

```shell
$ brew install risingwave@1.2

# If you haven't installed other versions, it's available as `risingwave`
$ risingwave --version
# If you have installed other versions, you can find it with `brew --prefix`
$ $(brew --prefix risingwave@1.2)/bin/risingwave --version
```

## Contributing

```bash
# 1. Bump the version in the formula
brew bump-formula-pr risingwave --version x.y.z

# 2. Switch to the newly created branch
git switch bump-risingwave-x.y.z

# 3. Manually update the `resource "connector"` section in `Formula/risingwave.rb`
code Formula/risingwave.rb
```

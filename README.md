## Keepassx

[![GitHub license](https://img.shields.io/github/license/pitluga/keepassx.svg)](https://github.com/pitluga/keepassx/blob/master/LICENSE)
[![GitHub release](https://img.shields.io/github/release/pitluga/keepassx.svg)](https://github.com/pitluga/keepassx/releases/latest)
[![Build Status](https://travis-ci.org/pitluga/keepassx.svg?branch=master)](https://travis-ci.org/pitluga/keepassx)
[![Code Climate](https://codeclimate.com/github/pitluga/keepassx/badges/gpa.svg)](https://codeclimate.com/github/pitluga/keepassx)
[![Test Coverage](https://codeclimate.com/github/pitluga/keepassx/badges/coverage.svg)](https://codeclimate.com/github/pitluga/keepassx/coverage)
[![Dependency Status](https://gemnasium.com/pitluga/keepassx.svg)](https://gemnasium.com/pitluga/keepassx)

### A Ruby library to read and write [KeePassX](http://www.keepassx.org/) databases.

## Installation

```sh
gem install keepassx
```

or if you use bundler

```ruby
gem 'keepassx'
```

## Usage

```ruby
require 'keepassx'

database = Keepassx::Database.open("/path/to/database.kdb")
database.unlock("the master password")
puts database.entry("entry's title").password
```

## Security Warning

No attempt is made to protect the memory used by this library; there may be something we can do with libgcrypt's secure-malloc functions, but right now your master password is unencrypted in ram that could possibly be paged to disk.

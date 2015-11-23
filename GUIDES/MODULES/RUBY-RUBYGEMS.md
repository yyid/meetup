# RUBY + RUBYGEMS

## Requirements

* [Ruby](https://www.ruby-lang.org/en/documentation/installation/)

You can check if you have a working installation of Ruby with:

```shell
$ ruby -v
```

## How to Package a Module

Replace `mmm` with your module's name.

### Recommended File Structure

    .
    ├── package.json
    └── src
        └── mmm.js

You should also add information and documentation to your module, by adding a `README.md`, a `LICENSE.txt`, and a `CHANGELOG.md` file.

### `mmm.gemspec`

The `.gemspec` file contains your module's meta data.

[Documentation](http://guides.rubygems.org/specification-reference/)

```ruby
# -*- encoding: utf-8 -*-

require File.expand_path('../lib/mmm/version', __FILE__)

Gem::Specification.new do |gem|
  gem.name          = "mmm"
  gem.version       = Mmm::VERSION
  gem.summary       = "Text summary."
  gem.description   = "Longer text summary."
  gem.license       = "MIT"
  gem.authors       = ["Jane Doe", "Max Mustermann"]
  gem.email         = "mail@moremicromodules.org"
  gem.homepage      = "https://github.com/mmm/meetup"

  gem.files         = Dir['{**/}{.*,*}'].select { |path| File.file?(path) }
  gem.executables   = gem.files.grep(%r{^bin/}).map{ |f| File.basename(f) }
  gem.test_files    = gem.files.grep(%r{^(test|spec|features)/})
  gem.require_paths = ['lib']

  gem.add_development_dependency 'rake', '~> 10.4'
  # gem.add_dependency 'dependency', '~> 1.0'
end
```

Use multiple `gem.add_dependency` to add other modules that your module depends on.


### `lib/mmm.rb`

This is where your code lives.

```ruby
require_relative 'mmm/version'

module Mmm
  # Your code
end
```

### `lib/mmm/version.rb`

It is a best practice to define a version constant, which is also loaded by your main code. Having it in a separate file enables you access the version from the `.gemspec` file.

```ruby
module Mmm
  VERSION = "0.1.0".freeze
end
```

### `Gemfile`

[Bundler](http://bundler.io/) is a quasi standard for managing an application's dependencies. While it is not required for gems, it is useful for the module development itself. By calling the `gemspec` method, bundler will use the dependencies defined in the `.gemspec` file.

```ruby
source 'https://rubygems.org'

gemspec
```

### `Rakefile`

You can add project-related tasks to a Rakefile. This is an example file you can use to

* Build your gem
* Start IRB with your code loaded

[Documentation](https://github.com/ruby/rake)

```ruby
# # #
# Get gemspec info

gemspec_file = Dir['*.gemspec'].first 
gemspec = eval File.read(gemspec_file), binding, gemspec_file
info = "#{gemspec.name} | #{gemspec.version} | " \
       "#{gemspec.runtime_dependencies.size} dependencies | " \
       "#{gemspec.files.size} files"


# # #
# Gem build and install task

desc info
task :gem do
  puts info + "\n\n"
  print "  "; sh "gem build #{gemspec_file}"
  FileUtils.mkdir_p 'pkg'
  FileUtils.mv "#{gemspec.name}-#{gemspec.version}.gem", 'pkg'
  puts; sh %{gem install --no-document pkg/#{gemspec.name}-#{gemspec.version}.gem}
end


# # #
# Start an IRB session with the gem loaded

desc "#{gemspec.name} | IRB"
task :irb do
  sh "irb -I ./lib -r #{gemspec.name.gsub '-','/'}"
end
```

## How to Publish a Module

### Build the gem

```sh
$ gem build mmm.gemspec
```

This will create a `mmm-version.gem` file.

### Publish to *rubygems.org*

TBD

## Resources

* http://ruby-lang.org
* http://guides.rubygems.org

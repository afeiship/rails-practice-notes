# rails-install:

## install rails:
```shell
rvm gemset create rails4.2
rvm use 2.2.0@rails4.2 --default
gem install rails -v 4.2.0 --no-document
```

## errors: when 
~~~
gem install rails -v 4.2.0 --no-document
~~~
+ https://stackoverflow.com/questions/32353715/invalid-gem-package-is-corrupt-while-installing-rails-in-osx-yosemite-10-10

## my solution:
~~~
rm -rf ~/.rvm/gems/ruby-2.2.0@rails4.2/cache/nokogiri-1.8.2.gem
brew install libiconv
gem install nokogiri
~~~
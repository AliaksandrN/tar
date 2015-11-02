## Dokumentacja do RSpec

[RSpec documentation](http://rspec.info/):

* [rspec-expectations](https://github.com/rspec/rspec-expectations)
* [rspec-collection_matchers](https://github.com/rspec/rspec-collection_matchers)
* [rspec-mocks](https://github.com/rspec/rspec-mocks)
* [rspec-core](https://github.com/rspec/rspec-core)


Testy uruchamiamy w następujący sposób:

```sh
rspec       # tylko kropki
rspec -cfd  # więcej szczegółów
```

## Podpinanie aplikacji do [Travisa](https://travis-ci.org/)

* [getting started](http://docs.travis-ci.com/)
* gem *travis-lint*
* [status images](http://docs.travis-ci.com/user/status-images/)

Przykładowy plik *.travis.yml*:

```yaml
language: ruby
rvm:
- 2.2.2
env:
- DB=postgresql
cache: bundler
before_script:
- psql -c "CREATE DATABASE dbreview_test;" -U postgres
- cp config/database.yml.travis config/database.yml
- bundle exec rake db:test:load
script:
- bundle exec rspec
```

## Linki do klas/modułów Ruby

* [Array](http://www.ruby-doc.org/core-2.1.1/Array.html)
* [Hash](http://www.ruby-doc.org/core-2.1.1/Hash.html)
* [Enumerable](http://www.ruby-doc.org/core-2.1.1/Enumerable.html)
* [String](http://www.ruby-doc.org/core-2.1.1/String.html)
* [Regexp](http://www.ruby-doc.org/core-2.1.1/Regexp.html)

# Libsodium Nanobox Failure

This is an example of how adding rbnacl-libsodium as a dependency in a rails app breaks nanobox.

Running `nanobox run rails c` gives the following exception:

```
Using rbnacl-libsodium 1.0.16 from https://github.com/crypto-rb/rbnacl-libsodium.git (at c1ee4d6@c1ee4d6)
Gem::Ext::BuildError: ERROR: Failed to build gem native extension.

current directory:
/app/vendor/bundle/ruby/2.3.0/bundler/gems/rbnacl-libsodium-c1ee4d621b2e/ext/rbnacl
/data/bin/ruby -r ./siteconf20180417-984-14el4ip.rb extconf.rb
extconf.rb:22:in `<main>': can't modify frozen Array (RuntimeError)

extconf failed, exit code 1
```

The only difference between this and nanobox-rails is the addition of the `rbnacl-libsodium` dependency. See [diff here](https://github.com/nanobox-quickstarts/nanobox-rails/compare/master...steveklebanoff:master).

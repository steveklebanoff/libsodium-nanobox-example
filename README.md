# Libsodium Nanobox Failure

This is an example of how adding rbnacl-libsodium as a dependency in a rails app breaks nanobox.

Running `nanobox run rails c` gives the following exception:

```
/app/vendor/bundle/ruby/2.3.0/gems/rbnacl-libsodium-1.0.16/lib/rbnacl/libsodium.rb:22:in `join': no implicit conversion of nil into String (TypeError)
	from /app/vendor/bundle/ruby/2.3.0/gems/rbnacl-libsodium-1.0.16/lib/rbnacl/libsodium.rb:22:in `<module:Libsodium>'
	from /app/vendor/bundle/ruby/2.3.0/gems/rbnacl-libsodium-1.0.16/lib/rbnacl/libsodium.rb:4:in `<module:RbNaCl>'
	from /app/vendor/bundle/ruby/2.3.0/gems/rbnacl-libsodium-1.0.16/lib/rbnacl/libsodium.rb:3:in `<top (required)>'
	from /data/lib/ruby/gems/2.3.0/gems/bundler-1.16.1/lib/bundler/runtime.rb:95:in `require'
	from /data/lib/ruby/gems/2.3.0/gems/bundler-1.16.1/lib/bundler/runtime.rb:95:in `rescue in block in require'
	from /data/lib/ruby/gems/2.3.0/gems/bundler-1.16.1/lib/bundler/runtime.rb:72:in `block in require'
	from /data/lib/ruby/gems/2.3.0/gems/bundler-1.16.1/lib/bundler/runtime.rb:65:in `each'
	from /data/lib/ruby/gems/2.3.0/gems/bundler-1.16.1/lib/bundler/runtime.rb:65:in `require'
	from /data/lib/ruby/gems/2.3.0/gems/bundler-1.16.1/lib/bundler.rb:114:in `require'
	from /app/config/application.rb:7:in `<top (required)>'
	from /app/vendor/bundle/ruby/2.3.0/gems/railties-5.1.4/lib/rails/command/actions.rb:15:in `require'
	from /app/vendor/bundle/ruby/2.3.0/gems/railties-5.1.4/lib/rails/command/actions.rb:15:in `require_application_and_environment!'
	from /app/vendor/bundle/ruby/2.3.0/gems/railties-5.1.4/lib/rails/commands/console/console_command.rb:96:in `perform'
	from /app/vendor/bundle/ruby/2.3.0/gems/thor-0.20.0/lib/thor/command.rb:27:in `run'
	from /app/vendor/bundle/ruby/2.3.0/gems/thor-0.20.0/lib/thor/invocation.rb:126:in `invoke_command'
	from /app/vendor/bundle/ruby/2.3.0/gems/thor-0.20.0/lib/thor.rb:387:in `dispatch'
	from /app/vendor/bundle/ruby/2.3.0/gems/railties-5.1.4/lib/rails/command/base.rb:63:in `perform'
	from /app/vendor/bundle/ruby/2.3.0/gems/railties-5.1.4/lib/rails/command.rb:44:in `invoke'
	from /app/vendor/bundle/ruby/2.3.0/gems/railties-5.1.4/lib/rails/commands.rb:16:in `<top (required)>'
	from bin/rails:4:in `require'
	from bin/rails:4:in `<main>'
```

The only difference between this and nanobox-rails is the addition of the `rbnacl-libsodium` dependency. See [diff here](https://github.com/nanobox-quickstarts/nanobox-rails/compare/master...steveklebanoff:master).

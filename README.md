###  Install Ruby on Rails in OpenBSD
####  Here you can see instruction.

1. Install Ruby

```ruby

 $ pkg_add ruby
 #I choose 2.3.1
```
2. Install Gems

```ruby

$ pkg_add ruby-gems
```
For running Gem you need type in terminal  ` $ gem23 `

Better to create link with this command:

`$ ln -sf /usr/local/bin/gem23 /usr/local/bin/gem`

3. Add ~/.gem/ruby/2.3/bin to PATH

```ruby

PATH="~/.gem/ruby/2.3/bin:"$PATH

```
For running Ruby you need type in terminal  ` $ ruby23 `


Better to create link with this command:

`$ ln -sf /usr/local/bin/ruby23 /usr/local/bin/ruby`


4. Install Bundle

```ruby
$ gem install --user-install bundler
```

5. Install Nokogiri (or run into problems installing rails)

```
$ pkg_add ruby-nokogiri
```

6. Install Rails

```
$ gem install --user-install rails
```
For running Rails you need type in terminal  ` $ rails23 `


Better to create link with this command:

`$ ln -sf /usr/local/bin/rails23 /usr/local/bin/rails`


7. Create project with next command:

```rails new <projectname> ```

  will throw an issue with nokogiri so...

  ```
  $ gem install --user-install nokogiri

  ```
9. Install node.js

```
$ pkg_add node
```

10. Add node to the Gemfile

```ruby
gem 'node'

```

11. Run bundle install to install your gems!

```ruby

$ bundle install --path=~/.gem

```

12. Profit!!

The gem install --user-install bundler puts the bundler local to the user. Adding the directory to the path allows for bundler to be used where it was installed. If you want to go a step further you can soft link /usr/local/bin/ruby23 to /usr/local/bin/ruby and do something similar with /usr/local/bin/rails23 and ~/.gem/ruby/2.4/bin/bundle(r)23. I just run the commands as they are right now.

I also ran into an issue with the rubyracer, for some reason bundle didn't find python or python2 (or something like that). Instead I used the node gem, and installed nodejs on my server.

Original version : https://gist.github.com/desnudopenguino/cc4e675f931bcf5a83dac8596f9e84e7

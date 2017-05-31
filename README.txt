1. Install Ruby
pkg_add ruby
- I chose 2.3.0
2. Install gems
pkg_add ruby-gems
3. Add ~/.gem/ruby/2.3/bin to PATH 
PATH="~/.gem/ruby/2.3/bin:"$PATH
4. Install bundle
gem23 install --user-install bundler
5. Install nokogiri (or run into problems installing rails)
pkg_add ruby23-nokogiri
6. Install rails
gem23 install --user-install rails
7. rails23 new <projectname> - will throw an issue with nokogiri so...
8. gem23 install --user-install nokogiri -- --use-system-libraries --with-xml2-config=/usr/local/bin/xml2-config --with-xslt-config=/usr/local/bin/xslt-config
9. Install node.js
pkg_add node
10. Add node to the gemfile
gem 'node'
11. ???
12. Run bundle install to install your gems!
bundle23 install --path=~/.gem
13. Profit!!

the gem install --user-install bundler puts the bundler local to the user. Adding the directory to the path allows for bundler to be used where it was installed. If you want to go a step further you can soft link /usr/local/bin/ruby23 to /usr/local/bin/ruby and do something similar with /usr/local/bin/rails23 and ~/.gem/ruby/2.4/bin/bundle(r)23. I just run the commands as they are right now.

I also ran into an issue with therubyracer, for some reason bundle didn't find python or python2 (or something like that). Instead I used the node gem, and installed nodejs on my server. 

Original version : https://gist.github.com/desnudopenguino/cc4e675f931bcf5a83dac8596f9e84e7

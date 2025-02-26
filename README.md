
### Run Locally

#### Setup
```bash
brew install chruby ruby-install

ruby-install ruby 3.4.1

echo "source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc
echo "source $(brew --prefix)/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc
echo "chruby ruby-3.4.1" >> ~/.zshrc

#  Check version
ruby -v

```

#### Run
```bash
bundle install
bundle exec jekyll serve
```


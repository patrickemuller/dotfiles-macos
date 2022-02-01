# dotfiles-macos
Specific dotfiles for MacOS, iterm and RubyMine

## Install dependencies

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/patrickmuller/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
echo $SHELL
brew install zsh
echo $SHELL
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
brew install romkatv/powerlevel10k/powerlevel10k
echo "source $(brew --prefix)/opt/powerlevel10k/powerlevel10k.zsh-theme" >>~/.zshrc

git clone https://github.com/supercrabtree/k $ZSH_CUSTOM/plugins/k
git clone https://github.com/zsh-users/zsh-completions ${ZSH_CUSTOM:=~/.oh-my-zsh/custom}/plugins/zsh-completions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# Open ZSHRC and add this plugins

command-not-found
zsh-completions
zsh-autosuggestions
rails
heroku
git
k
zsh-syntax-highlighting

brew install asdf
echo -e "\n. $(brew --prefix asdf)/libexec/asdf.sh" >> ~/.zshrc
echo -e "\n. $(brew --prefix asdf)/etc/bash_completion.d/asdf.bash" >> ~/.zshrc

asdf plugin add ruby https://github.com/asdf-vm/asdf-ruby.git
asdf install ruby 2.7.2
asdf global ruby 2.7.2

asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git
asdf install nodejs latest
asdf global nodejs latest

asdf plugin-add yarn
asdf install yarn latest
asdf global yarn latest

# close and open terminal

brew doctor
brew update
brew install postgres cmake pkg-config shared-mime-info redis coreutils imagemagick gpg postgis
brew tap elastic/tap
brew install elastic/tap/elasticsearch-full
# open code /opt/homebrew/Cellar/elasticsearch-full/7.16.2/libexec/config/jvm.options
# comment the lines 31 and 32 and set the max memory heap size

brew install --cask stats
```

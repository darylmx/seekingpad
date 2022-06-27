# install zsh
`sudo apt install zsh`

#install oh-my-zsh
`sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`

#install power10k
`git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k`
Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc.`

## reload zsh
`. ~/.zshrc`

## configure p10k
`p10k configure`


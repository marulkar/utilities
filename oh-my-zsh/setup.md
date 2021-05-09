* Install ZSH
    * apt install zsh
* Install Oh My Zsh
    * curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh; zsh
 * change the shell to ZSH
    * chsh -s $(which zsh)

### Add utilities to OMZ:

Utility | how to install | how to incorporate as a plugin (~/.zshrc)
---------|----------|---------
 syntax highlighting | git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting | zsh-syntax-highlighting
 autosuggestions | git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions | zsh-autosuggestions
 fuzzy finder | git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf && ~/.fzf/install | fzf

 more on the way..

 Thanks: https://medium.com/@ivanaugustobd/your-terminal-can-be-much-much-more-productive-5256424658e8

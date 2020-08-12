# Mac-Setup

My mac setup after a reboot or new buy

### Before anything

Search for Updates ( → Syst. Preferences → Software Update)

### Mac Preferences

Dock (⌘+space → Dock):
  - Remove apps
  - Change size
  - Hide
  - Clip to left/right side
  
Finder Preferences (Finder → ⌘,): 
  - Open new finder windows on Home (General)
  - Edit Sidebar
  - Show Path Bar
  
 Trackpad: 
  - Point&Click → Tap to click

## Dev setup

Install Homebrew:
  - /bin/bash -c “$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
  
iTerm: 
  - brew cask install iterm2

Rectangle:
  - brew cask install rectangle
  
Alfred:
  - brew cask install alfred

Firefox/Chrome:
  - Privacy badger
  - UBlock Origin

Git: 
  - brew install git
  
Zsh: 
  - brew install zsh
  - edit shells: sudo nano /etc/shells
  - add /usr/local/bin/zsh
  - chsh -s /usr/local/bin/zsh or Users&Groups → left-click username → Advanced Options → Choose shell
  - which zsh to make sure
 
Oh-My-ZSH:
  - sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  
Terminal settings:
  - Dracula theme: 
    - git clone https://github.com/dracula/terminal-app.git
    - terminal → Preferences → Profiles → Colors → Presets... → Import Dracula.() → Choose dracula
  - Spaceship theme:
    - Install FiraCode (or any PowerLine font): Download zip (https://github.com/tonsky/FiraCode) → ttf folder → select all fonts → left-click + Open → install → Set terminal to use fira code on Preferences → Profiles → text
    - git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"
    - ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
    - edit .zshrc and set ZSH_THEME="spaceship"
    - edit order and functionalities https://denysdovhan.com/spaceship-prompt/docs/Options.html#exit-code-exit_code or copy settings from my SPACESHIP_PROMPT_ORDER.txt file
  - Zsh Plugins:
    - Install ZInit plugin manager: sh -c "$(curl -fsSL https://raw.githubusercontent.com/zdharma/zinit/master/doc/install.sh)"
    - Open .zshrc and at the end add:
      - For syntax highlighting: zinit light zdharma/fast-syntax-highlighting
      - For auto-suggestions history: zinit light zsh-users/zsh-autosuggestions
      - For commands auto-completions: zinit light zsh-users/zsh-completions
  
VS-Code:
  - brew cask install visual-studio-code





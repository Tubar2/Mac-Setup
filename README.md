When buying or rebooting a Mac set up environment using the following instructions

# Before anything

Search for new updates

 → System Preferences → Software Update

---

# Overall Mac Appearence

## Dock

⌘space → Dock

- Reduce app's size
- Clip dock to left/right side of screen
- Hide dock
- Remove barely used apps

## Finder

⌘space → Finder → ⌘,

- New finder windows open on $Home
- Edit finder sidebar
- View → Show Path Bar

## Trackpad

⌘space → Trackpad → Point & Click → Tap to click

---

# Overall Dev Setup

## Dev folder

Development folder for all code in home directory

```bash
mkdir $HOME/dev
```

## Home-Brew

[Home-Brew Basic Command Guide](https://www.notion.so/Home-Brew-Basic-Command-Guide-5cb419e99a924e8e92087ba99dc3f6a2)

- Why use?

```bash
/bin/bash -c “$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

## iTerm2

Substitute for mac terminal

```bash
brew cask install iterm2
```

## Rectangle

Window size manager

```bash
brew cask install rectangle
```

## Alfred

Substitute for mac Spotlight

```bash
brew cask install alfred
```

## Firefox/Chrome

Browser for usage instead of Safari

- Extensions

```bash
brew cask install firefox
brew cask install google-chrome
```

## VS-Code

```bash
brew cask install visual-studio-code
```

### VS-Code Plugins

- Material Icon Theme
- Prettier - Code Formatter
- ES Lint
- Live Server
- Dracula Official
- C/C++
- Go
- Todo Tree

## Other apps

### HyperSwitch

Shows applications window preview

### Helium

View videos in picture mode

---

# Setting Up ZSH and Terminal

- Install ZSH using home-brew

```bash
brew install zsh
```

- Edit shells and add `/usr/local/bin/zsh` to the end of file

```bash
sudo nano /etc/shells
```

- Choose zsh shell by
    - Command: `chsh -s /usr/local/bin/zsh` or
    - Users&Groups → left-click username → Advanced Options → Choose shell
- To make sure it's been selected, use `which zsh` on terminal

## Oh-My-Zsh

- Install oh my zsh

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Set Up iTerm

### Dracula Color Scheme:

- Clone repo

```bash
git clone https://github.com/dracula/iterm.git
```

- iTerm → Preferences → Profiles → Colors → Presets... → Import Dracula.(something) → Choose dracula

### Spaceship Theme:

- Install a PowerLine font (FiraCode)
    - Download zip ([https://github.com/tonsky/FiraCode](https://github.com/tonsky/FiraCode)) → ttf folder → select all fonts → left-click + Open → install → Set terminal to use fira code on Preferences → Profiles → text
- Clone spaceship theme repo

```bash
git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt"
```

- Load theme into config files

```bash
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
```

- edit .zshrc and set ZSH_THEME="spaceship"
- edit order and functionalities
    - [https://denysdovhan.com/spaceship-prompt/docs/Options.html#exit-code-exit_code](https://denysdovhan.com/spaceship-prompt/docs/Options.html#exit-code-exit_code) or
    - copy settings from my SPACESHIP_PROMPT_ORDER.txt

        [Spaceship_Prompt_Order](https://www.notion.so/Spaceship_Prompt_Order-6b6de9ea82d545e6a3a91a74e9dc373c)

### Zsh Plugins

- Install ZInit plugin manager

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/zdharma/zinit/master/doc/install.sh)"
```

- Edit .zshrc file and add to end:
    - For syntax highlighting: zinit light zdharma/fast-syntax-highlighting
    - For auto-suggestions history: zinit light zsh-users/zsh-autosuggestions
    - For commands auto-completions: zinit light zsh-users/zsh-completions

---

# Programming Languages Installation

## Go-lang

[Golang](https://www.notion.so/Golang-80d26929a7fd4428b17a6926061fa7f6)

Installing go with homebrew doesn't always gets the earliest version

Use brew to install golang

```bash
brew install golang

go version

# Make sure go env is set up correctly
go env
```

Create go workspace folder

```bash
mkdir -p $HOME/dev/go/src
```

- Edit shell config file `~/.zshrc` if go env isn't set up correctly

```bash
nano ~/.zshrc

# Add the following to the end of it
export GOPATH=$HOME/dev/go
export PATH=$PATH:$(go env GOPATH)/bin

# export GOROOT="$(brew --prefix golang)/libexec"
# export PATH="$PATH:${GOPATH}/bin:${GOROOT}/bin"

# Reload settings with
source $HOME/.zshrc
```

Create a project

```bash
mkdir $HOME/dev/go/src/hello

touch $HOME/dev/go/src/hello/main.go
```

Add to main.go

```go
package main

import (
	"fmt"
)

func main() {
	fmt.Println("Hello, World")
}
```

Inside the created folder install the program and run it

```bash
go install .
./hello
```

go get a package

```bash
go get -u github.com/gorilla/mux
```

Create a new project using the package and run it

```go
package main

import (
    "github.com/gorilla/mux" // Your imported package
    "net/http"
)

func yourHandler(w http.ResponseWriter, r *http.Request) {
    w.Write([]byte("Gorilla!\n"))
}

func main() {
    r := mux.NewRouter()
    // Routes consist of a path and a handler function.
    r.HandleFunc("/", yourHandler)

    // Bind to a port and pass our router in
    panic(http.ListenAndServe(":8000", r))
}
```

## Python3

Install python3 with home-brew

```bash
brew install python3
```

Python scripts will be put in `/usr/local/share/python`, make sure it's on PATH!

Packages installed with pip are stored globally, so versioning becomes difficult, so having isolated environments makes it easier 

Install Pipenv for handling virtual environments in Python

```bash
brew install pipenv
```

Managing python packages on dedicated projects

```bash
mkdir -p $HOME/dev/python3/<new-project-name>
```

Installing packages

```bash
pipenv install [package names]
pipenv install <packagename>==<version>

# To activate enviroment
pipenv shell

# To exit enviroment
exit

# To remove a package from environment
pipenv uninstall [package name]
pipenv uninstall --all

# To completely erase a environment
rm -r <project-folder>
```

Click [here](https://realpython.com/pipenv-guide/) for more on pipenv

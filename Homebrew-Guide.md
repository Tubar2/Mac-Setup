## Updating Home-Brew

Command that updates home-brew to latest version

```bash
brew update
```

## Installing Packages

Packages are called formulas. So installing a package means installing a formula

All formulas can be searched for in the [home-brew website](https://formulae.brew.sh/)

```bash
brew install <formula>

brew install node
```

## Upgrading Installed Packages

```bash
brew upgrade <formula>

brew upgrade
```

## Deleting Installed Packages

- Usages

```bash
brew uninstall <formula>

brew unistall --force <formula>

brew uninstall --ignore-dependencies <formula>
```

## Cleanup

Removes outdated downloads

```bash
brew cleanup
```

## Installing Third-Party Packages

Third party packages must be beforehand tapped into

```bash
brew tap mongodb/brew
brew install mongodb-community
```

## Installing GUI-like Applications

```bash
brew cask install <formula>
```

## Cheatsheet

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9a8a3c0a-26c7-4571-85a4-654880a58d14/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9a8a3c0a-26c7-4571-85a4-654880a58d14/Untitled.png)

---

## Creating Your Own Formulas with Ruby

[See here](https://docs.brew.sh/Formula-Cookbook#:~:text=A%20formula%20is%20a%20package,provides%20various%20Homebrew%2Dspecific%20helpers.)

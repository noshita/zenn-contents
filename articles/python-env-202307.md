---
title: "研究開発向けPython環境構築 2023.07"
emoji: "💻"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["Python", "Homebrew", "pyenv", "Poetry"]
published: false
---

## 概要

* OSはmacOS, Linuxを利用する（LinuxディストリビューションはUbuntu）．Windowsの場合はWSL2でLinux環境を用意する．
* シェルは[zsh](https://www.zsh.org/)を利用する．
* ミドルウェアなどのパッケージ管理は[Homebrew](https://brew.sh/)でおこなう．
* テキストエディタは[Visual Studio Code](https://code.visualstudio.com/)を利用する．
* Pythonバージョンの切り替えは[pyenv](https://github.com/pyenv/pyenv)でおこなう．
* Pythonの仮想環境構築とパッケージの依存管理は[Poetry](https://python-poetry.org/)でおこなう．
* ディレクトリ構成は[Cookiecutter Data Science](https://github.com/drivendata/cookiecutter-data-science)をベースにする．

## Homebrew
### macOS

事前にCommand Line Tools for Xcodeをインストールしておく．

```sh
xcode-select --install 
```

### Ubuntu

事前に必要なツール群をインストールしておく．

```sh
sudo apt-get install build-essential procps curl file git
```

### インストール

公式のインストールコマンドを実行．

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

パスを通す．

```sh

```

* [Homebrew](https://brew.sh/)
  * [Installation | Homebrew](https://docs.brew.sh/Installation)


## Visual Studio Code

Homebrewでインストールする．

```sh
brew install visual-studio-code
```

## pyenv

Homebrewでインストールする．

```sh
brew install pyenv
```

パスを通す．

```sh
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
```

非インタラクティブシェル用として`.zprofile`にも追加しておく．

```sh
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zprofile
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zprofile
echo 'eval "$(pyenv init -)"' >> ~/.zprofile
```

* [pyenv | GitHub](https://github.com/pyenv/pyenv)
  * [Set up your shell environment for Pyenv](https://github.com/pyenv/pyenv#set-up-your-shell-environment-for-pyenv)

## Poetry



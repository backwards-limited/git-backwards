# Setup

Apologies I shall only cover **Mac** - One day I may include Linux and Windows.

Install [Homebrew](https://brew.sh) for easy package management on Mac:

```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Install essentials:

```bash
brew install git
```

## Configure

```bash
$ git config --global --list
user.name=David Ainslie
user.email=dainslie@gmail.com
...
```

If your Github name and email have not been setup (and this goes for other remote git repositories):

```bash
$ git config --global user.name "David Ainslie"
$ git config --global user.email "dainslie@gmail.com"
```

```bash
$ cat ~/.gitconfig
[user]
	name = David Ainslie
	email = dainslie@gmail.com
[core]
	excludesfile = /Users/davidainslie/.gitignore_global
	autocrlf = input
[difftool "sourcetree"]
	cmd = opendiff \"$LOCAL\" \"$REMOTE\"
	path =
[mergetool "sourcetree"]
	cmd = /Applications/SourceTree.app/Contents/Resources/opendiff-w.sh \"$LOCAL\" \"$REMOTE\" -ancestor \"$BASE\" -merge \"$MERGED\"
	trustExitCode = true
[filter "media"]
	required = true
	clean = git media clean %f
	smudge = git media smudge %f
[merge]
	tool = diffmerge
[filter "hawser"]
	clean = git hawser clean %f
	smudge = git hawser smudge %f
	required = true
[filter "lfs"]
	clean = git-lfs clean -- %f
	smudge = git-lfs smudge -- %f
	required = true
	process = git-lfs filter-process
```


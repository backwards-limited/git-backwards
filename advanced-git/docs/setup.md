# Setup

## Editor

```bash
$ git config --global -e
```

The result will appear in **vim** or whatever your default editor is set to. Let's change that:

```bash
$ git config --global core.editor code
```

## Merge & Diff

We set up VSCode as our default editor - we will do the same for merge and diff. However, we could use one of many alternatives such as **P4Merge**, which can be installed by:

```bash
$ brew cask install p4v
```

What is the current diff tool used by git?

```bash
$ git config --global --get diff.tool
```

And if we get nothing, then no default diff tool has been set up. Let's do this for VSCode, by first modifying our config file with a named default diff tool:

```bash
$ git config --global diff.tool default-difftool

$ git config --global --get diff.tool
default-difftool
```

And let's actually set this **default-difftool** in our config by using VSCode itself:

```bash
$ git config --global -e
```

We'll see the following in the editor:

```sh
[diff]
	tool = default-difftool
```

and we'll add the following:

```sh
[difftool "default-difftool"]
  cmd = code --wait --diff $LOCAL $REMOTE
```

E.g. we want to diff commits as:

```bash
$ git difftool ac79961 a8f60f8

Viewing (1/1): 'details.html'
Launch 'default-difftool' [Y/n]?
```

Noting a diff directly from the command line:

```bash
$ git diff HEAD
```

Let's next switch off the *launch* prompt:

```bash
$ git config --global difftool.prompt false
```

and check the new setting:

```bash
$ git config --global --get difftool.prompt
false
```




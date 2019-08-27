# Git Tips and Tricks

Here you can find some tips how to customize the git for your developing processes easily.
I show you alias commands to make your life easier.

## Usage

Find your `gitconfig` file. Insert the later introduced commands in the `alias` section. For example:
```
[alias]
    new-command-name = "git-commands"
```

## Commands

### start-review

Can be useful for reviewing. Only the new changes will be not committed so an IDE can mark only the changed line.
For example in IntelliJ you can set it via File > Settings > Version Control and set "Show directories with changed descendants".

It requires a branch name (one to review) as a parameter.
It creates a `review` branch from the latest `master` and merges the reviewed branch into it but does not commit.

```
start-review = "!f() { git fetch; git checkout master; git pull; git checkout -b review; git merge origin/$1 --no-ff --no-commit;  }; f"
```
# Overleaf clone

Clone an Overleaf project into a named folder. If the project has no `.gitignore`,
the command copies [latex.gitignore](latex.gitignore) into the clone as `.gitignore`.

## Install

From this repository, run the following in a POSIX shell such as Git Bash on Windows.

```sh
mkdir -p "$HOME/.local/bin"
install -m 755 overleaf "$HOME/.local/bin/overleaf"
install -m 644 latex.gitignore "$HOME/.local/bin/latex.gitignore"
export PATH="$HOME/.local/bin:$PATH"
```

Add the `export` line to your shell profile to keep the command available in new terminals.

## Clone a project

Copy the ID after `/project/` in the Overleaf project URL. By default, the folder name is the project ID.

```sh
overleaf clone 1234567
```

Use `-n` or `--name` to choose a different folder name. Quote names that contain spaces.

```sh
overleaf clone 1234567 --name "My thesis"
```

This runs `git clone https://git.overleaf.com/1234567 "My thesis"`.
The project needs Overleaf Git integration. If Git asks for a username, enter
`git`. When it asks for a password, enter
your [Overleaf Git authentication token](https://docs.overleaf.com/integrations-and-add-ons/git-integration-and-github-synchronization/git-integration/git-integration-authentication-tokens).

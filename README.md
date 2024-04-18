# standalone copr command
This Tool is not made or supported by the Fedora Project,
but aims to reproduce the `dnf copr` functionalities for easily adding COPRs on Fedora Atomic.

It does everything rootless (unlike `dnf copr`) and only requires privilege escalation using `pkexec` for writing the repo file. Thus is also works without `sudo`.

```
Usage: copr [OPTION] [ARGUMENT]

Options:
  enable    Add COPR repository.
  remove    Remove COPR repository after backing it up.
  list      List all COPR repositories in your repo folder.
  search    Search for a COPR repository by name (in your Browser)
  disable   Keep a repo but disable it
  enable    Make a disabled repo active
  help      Display this help text.

Arguments:
  [ARGUMENT]  Name of the COPR repository (for search) or `author/repo` (for install and remove)

Examples:
  copr enable kdesig/kde-nightly-qt6
  copr remove kdesig/kde-nightly-qt6
  copr list
  copr search uutils
```

Install:

```
wget https://raw.githubusercontent.com/trytomakeyouprivate/COPR-OSTree/main/copr -P ~/.local/bin/ &&\
chmod +x ~/.local/bin/copr
```

> NOTE: Afaik the `dnf copr` and also this tool don't support updating currently installed COPR repositories. This would be really useful, and could be done with `sed` and a prompt to remove outdated repos and their associated packages. PRs welcome!

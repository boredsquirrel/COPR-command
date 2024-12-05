# standalone copr command
> [!NOTE]
> This Tool is not made or supported by the Fedora Project,
but aims to reproduce the `dnf copr` functionalities for easily adding COPRs on Fedora Atomic Desktops, IoT and CoreOS.

It does most actions rootless (unlike `dnf copr`) and only requires privilege escalation using `pkexec` for writing the repo file. Thus it also works without `sudo`.

```
Usage: copr [OPTION] [ARGUMENT]

Options:
  enable    Add COPR repository
  disable   Keep a repo but disable it
  remove    Remove COPR repository after backing it up
  list      List all COPR repositories in your repo folder
  search    Search for a COPR repository by name (in your Browser)
  help      Display this help text

Argument:
  Name of the COPR repository (for search) or "author/repo" (for install and remove)

Examples:
  copr enable kdesig/kde-nightly-qt6
  copr remove kdesig/kde-nightly-qt6
  copr list
  copr search bubblejail
```

Install:

```
wget https://raw.githubusercontent.com/boredsquirrel/COPR-command/main/copr -P ~/.local/bin/ &&\
chmod +x ~/.local/bin/copr
```

> [!NOTE]
> COPR repos are version-independent, but there is always a chance that they are unmaintained and thus dont support the current version.
> A solution like warning about that, or even removing them, could be useful.
> I did not test such a case on Fedora Atomic, and guess such a package would result in an `rpm-ostree` error.

> [!WARNING]
> COPR repositories can contain anything. Only add them if you trust the developers and know the repo really belongs to them.

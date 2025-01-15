# standalone copr command
> [!NOTE]
> This Tool is not made or supported by the Fedora Project,
but aims to reproduce the `dnf copr` functionalities for easily adding COPRs on Fedora Atomic Desktops, IoT and CoreOS.

It does most actions rootless (unlike `dnf copr`) and only requires privilege escalation using `run0` for writing or changing the repo file. Thus it also works without `sudo`.

The tool also fixes SELinux contexts and filesystem permissions, to secure the repo files from tampering. Atomic Desktops allow unprivileged updates from existing repos, so this is important.

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
  copr enable kwizart/kernel-longterm-6.6
  copr remove kdesig/kde-nightly-qt6
  copr list
  copr search bubblejail
```

Install:

```
curl https://raw.githubusercontent.com/boredsquirrel/COPR-command/main/copr -O ./copr
run0 sh -c '
  mkdir /var/usrlocal/bin
  mv ./copr /var/usrlocal/bin
  chown -R root:root /var/usrlocal/bin
  chcon -R system_u:object_r:bin_t:s0 /var/usrlocal/bin
  chmod +x /var/usrlocal/bin/copr
'
```

> [!NOTE]
> COPR repos are version-independent, but there is always a chance that they are unmaintained and thus dont support the current version.
> A solution like warning about that, or even removing them, could be useful.
> I did not test such a case on Fedora Atomic, and guess such a package would result in an `rpm-ostree` error.

> [!WARNING]
> COPR repositories can contain anything. Only add them if you trust the developers and know the repo really belongs to them.

# COPR-OSTree
A small script reenabling the "COPR" command on Fedora distros not including it. It allows you to add custom repositories for example on Silverblue/Kinoite.

![Fedora COPR image](https://copr.fedorainfracloud.org/static/copr_logo.png)

Install:

```
wget https://raw.githubusercontent.com/trytomakeyouprivate/COPR-OSTree/main/copr -P ~/local/bin/
```

Usage: as you would normally use it
- [Find a repo you like](https://copr.fedorainfracloud.org/coprs/)
- sudo copr enable author/repo
- install packages with `dnf` or `rpm-ostree`

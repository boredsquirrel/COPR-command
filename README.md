# COPR-standalone
A small script reenabling the "COPR" command on Fedora distros not including it. It allows you to add custom repositories for example on Silverblue/Kinoite.

New: It doesnt use sudo anymore but pkexec!

![Fedora COPR image](https://copr.fedorainfracloud.org/static/copr_logo.png)

Install:

```
wget https://raw.githubusercontent.com/trytomakeyouprivate/COPR-OSTree/main/copr -P ~/.local/bin/ &&\
chmod +x ~/.local/bin/copr
```

Usage: as you would normally use it
- [Find a repo you like](https://copr.fedorainfracloud.org/coprs/)
- `copr enable author/name`
- install packages with `dnf` or `rpm-ostree`

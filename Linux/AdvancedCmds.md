# Advanced Commands

:construction::factory:

## grep

from help:

```
-F, --fixed-strings       PATTERN is a set of newline-separated strings
```

examples:

```
; -n 	show line numbers
; -C 2	show 2 lines before and after match
apt-cache show network-manager.gnome | grep -n -C 2 dev
```

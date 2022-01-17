# bash-commands

## read from json
```bash
property=$(echo $(grep -A 1 -m1 "property" config.json | cut -f2 -d":" | tail -1 | sed 's/[,"]//g'))
```

with jq:
```bash
property=$(cat config.json | jq '.parameters | from_entries | .property')
```

## Overview
- https://wiki.ubuntuusers.de/Shell/Befehls%C3%BCbersicht/

## Perl Regexp
https://www.perlmonks.org/?node_id=518444
allows lookbehinds, so you do not need cut in grep commands after executing command.

e.g.
```bash
grep -Po "(?<=UBUNTU_CODENAME=).*" /etc/os-release
```

## for loops
https://www.cyberciti.biz/faq/bash-for-loop/

## bash functions
https://linuxize.com/post/bash-functions/
https://stackoverflow.com/a/16159057/9698518

## parameter expansion
https://linuxhint.com/bash_parameter_expansion

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
- https://www.perlmonks.org/?node_id=518444
allows lookbehinds, so you do not need cut in grep commands after executing command.

e.g.
```bash
grep -Po "(?<=UBUNTU_CODENAME=).*" /etc/os-release
```

## for loops
- https://www.cyberciti.biz/faq/bash-for-loop/

## bash functions
- https://linuxize.com/post/bash-functions/
- https://stackoverflow.com/a/16159057/9698518

## parameter expansion
- https://linuxhint.com/bash_parameter_expansion

## tar GitLab artifact archive
```shell
# Downloads folder via wget using requests Certificate Authority BUNDLE and Gitlab Personal Access Token (PRIVATE_TOKEN) to retrieve the <dir>/<subdir1>/<subdir2> folder and strip it 3 levels deep so that only the contents of subdir2 remain in the current directory.
wget --ca-certificate $REQUESTS_CA_BUNDLE -L --header "PRIVATE-TOKEN: $PRIVATE_TOKEN" "https://gitlab.com/api/v4/projects/<project id>/repository/archive.<format>?ref=<ref>&path=<subdir1>/<subdir2>" -qO - | tar -xzf - --strip-components=3
```
tar options:
- `x` extract
- `f` file
- `z` for gunzip files (i.e. for unzipping the .gz)

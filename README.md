# bash-commands

## read from json
```bash
property=$(echo $(grep -A 1 -m1 "property" config.json | cut -f2 -d":" | tail -1 | sed 's/[,"]//g'))
```

with jq:
```bash
property=$(cat config.json | jq '.parameters | from_entries | .property')
```

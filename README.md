# bash-commands

## read from json
property = $(echo $(grep -A 1 -m1 "property" config.json | cut -f2 -d":" | tail -1 | sed 's/[,"]//g'))

with jq:
property=$(cat config.json | jq '.parameters | from_entries | .projectName')

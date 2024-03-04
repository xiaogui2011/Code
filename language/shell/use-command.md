# use-command

```sh
#!/bin/bash

output=$(date)
echo "${output}" >>ddd

VAR1="$1"

MOREF=$(sudo run command against "$VAR1" | grep name | cut -c7-)
echo "$MOREF"

```

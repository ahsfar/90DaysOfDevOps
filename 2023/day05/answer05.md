

#!/bin/bash

echo "Dir name: "$1
echo "First Dir name: "$1$2
echo "Last Dir name: "$1$3
count=$(($3 - $2 + 1))

for ((n=$2; n<=$3; n++)); do
  mkdir "${1}${n}"
done

echo "Total "$count" directories are created"

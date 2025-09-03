#!/bin/bash
# filepath: Scripts/enhanced_numbers.sh

# Check for correct number of arguments
if [ $# -ne 3 ]; then
  echo "Usage: $0 <start> <end> <step>"
  exit 1
fi

start=$1
end=$2
step=$3

# Validate that step is positive
if [ "$step" -le 0 ]; then
  echo "Error: Step must be a positive integer."
  exit 1
fi

# Print numbers from start to end with given step
for ((i=start; i<=end; i+=step))
do
  echo $i
done
# LAB3.md

## Script: enhanced_numbers.sh

### Original Behavior (print_numbers.sh)
- Prints numbers from 1 to 5, one per line.
- No user input; range is fixed.

### New Behavior (enhanced_numbers.sh)
- User provides **start**, **end**, and **step** as command-line arguments.
- Script checks that exactly 3 arguments are given and that step is positive.
- Prints numbers from start to end, incrementing by step.

---

### Example Runs

**Valid input:**
```shell
$ ./enhanced_numbers.sh 2 10 2
2
4
6
8
10
```

**Invalid step:**
```shell
$ ./enhanced_numbers.sh 1 5 0
Error: Step must be a positive integer.
```

**Missing arguments:**
```shell
$ ./enhanced_numbers.sh 1 5
Usage: ./enhanced_numbers.sh <start> <end> <step>
```

---

## Screenshot

![screenshot of ct](ct.png)




---

## Extra Questions

**1. Difference between `$1`, `$@`, and `$#` in bash?**
- `$1`: The first command-line argument to the script.
- `$@`: All command-line arguments as separate words.
- `$#`: The number of command-line arguments.

**2. What does `exit 1` mean in a script?**
- Exits the script immediately with a status code of 1, indicating an
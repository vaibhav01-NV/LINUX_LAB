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

# Validate that start and end are integers
if ! [[ "$start" =~ ^-?[0-9]+$ ]] || ! [[ "$end" =~ ^-?[0-9]+$ ]]; then
  echo "Error: Start and end must be integers."
  exit 1
fi

# Print numbers from start to end with given step
for ((i=start; i<=end; i+=step))
do
  echo $i
done
# LAB3.md

## Script Comparison

### Original Script: print_numbers.sh

- **Behavior:** Prints numbers from 1 to 5, one per line.
- **Input:** No user input; range is fixed in the script.
- **Example Output:**
  ```
  1
  2
  3
  4
  5
  ```

---

### Enhanced Script: enhanced_numbers.sh

- **Behavior:** Prints numbers from a user-specified start to end, incrementing by a user-specified step.
- **Input:** User provides start, end, and step as command-line arguments.
- **Validation:** 
  - Checks that exactly 3 arguments are given.
  - Checks that start and end are integers.
  - Checks that step is a positive integer.
- **Example Runs:**

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

  **Non-integer input:**
  ```shell
  $ ./enhanced_numbers.sh a 5 1
  Error: Start and end must be integers.
  ```

  **Missing arguments:**
  ```shell
  $ ./enhanced_numbers.sh 1 5
  Usage: ./enhanced_numbers.sh <start> <end> <step>
  ```

---

## Extra Questions

**1. Difference between `$1`, `$@`, and `$#` in bash?**
- `$1`: The first command-line argument to the script.
- `$@`: All command-line arguments as separate words.
- `$#`: The number of command-line arguments.

**2. What does `exit 1` mean in a script?**
- Exits the script immediately with a status code of 1, indicating an error.
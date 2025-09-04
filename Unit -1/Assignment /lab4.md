#!/bin/bash
# filepath: Scripts/backup.sh

# Create backup directory if it doesn't exist
mkdir -p backup

# Get current timestamp
timestamp=$(date +"%Y%m%d_%H%M%S")

# Find and copy all .txt files with timestamp in filename
for file in *.txt; do
  if [ -f "$file" ]; then
    cp "$file" "backup/${file%.txt}_$timestamp.txt"
  fi
done
# LAB5.md

## Script: backup.sh

### How the script works
- Creates a `backup/` directory if it doesn't exist.
- Gets the current timestamp.
- Finds all `.txt` files in the current directory.
- Copies each `.txt` file into `backup/`, appending the timestamp to the filename.

---

### Example Run

**Create test files:**
```shell
$ echo "Hello" > file1.txt
$ echo "World" > file2.txt
```

**Run the script:**
```shell
$ ./backup.sh
```

**Result:**
Files like `backup/file1_20250910_153045.txt` and `backup/file2_20250910_153045.txt` are created.

--
![alt text](ew.png)

## Extra Questions

**1. What is the difference between `cp`, `mv`, and `rsync`?**
- `cp`: Copies files or directories.
- `mv`: Moves (renames) files or directories.
- `rsync`: Efficiently syncs files/directories, can copy, move, and mirror with options for incremental updates.

**2. How can you schedule scripts to run automatically?**
- Use `cron` jobs (with `crontab -e`) to schedule scripts at specific times.
- Example: `0 2 * * * /path/to/backup.sh` runs the script daily at
#!/bin/bash
# filepath: Scripts/starter_kit.sh

# Create folders
mkdir -p project/scripts
mkdir -p project/docs
mkdir -p project/data

# Add placeholder README.md in each folder
echo "# Scripts" > project/scripts/README.md
echo "# Docs" > project/docs/README.md
echo "# Data" > project/data/README.md

# Print completion message
echo "Starter Kit Ready!"
# LAB_extra.md

## Purpose of script

The script automates the creation of a starter project structure with `scripts/`, `docs/`, and `data/` subfolders inside a `project/` directory. It also adds a placeholder `README.md` file in each subfolder for documentation.

---

## Example run screenshot

![screenshot of xz](xz.png)




---

## Extra Questions

**1. What does `mkdir -p` do?**  
It creates the specified directory and any necessary parent directories. If the directory already exists, no error is shown.

**2. Why is automation useful in DevOps?**  
Automation reduces manual effort, minimizes errors, speeds up processes, ensures consistency, and enables reliable,
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
The script automates the creation of a standard project folder structure with placeholder README.md files in each subfolder.

## Example Run
![alt text](<Screenshot 2025-09-13 at 4.17.23 PM-1.png>)

## Extra Questions

**1. What does `mkdir -p` do?**  
It creates the specified directory and any necessary parent directories. If the directory already exists, it does nothing and does not show an error.

**2. Why is automation useful in DevOps?**  
Automation saves time, reduces human error, ensures consistency, and speeds up repetitive tasks such as environment setup, deployment, and testing.
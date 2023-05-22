# Greetings!

## Exploring the `find` command
Today we will explore the `find` command, and its several use cases. The `find` command is a tool used for searching files or directories within a given directory or its subdirectories. Although it is quite simple, we can do many special things with this command, improving our quality of life.

### Option 1: `-name`
The `-name` option allows us to search for files based off their file name.

**Example 1:**
```bash
find ./technical -name "*.txt"
```
This command searches for all files that end with ".txt" within `./technical` directory and its subdirectories. 

**Example 2:**
```bash
find ./technical -name "file*"
```
This command searches for all files that start with "file" within `./technical` directory and its subdirectories. 

### Option 2: `-size`
The `-size` option allows searching for files based on their size.

**Example 1:**
```bash
find ./technical -size +100K
```
This command searches for all files within the `./technical` directory and its subdirectories that are larger than 100 kilobytes. The `+100K` parameter specifies the size criterion.

**Example 2:**
```bash
find ./technical -size -100K
```
This command searches for all files within the `./technical` directory and its subdirectories that are smaller than 100 kilobytes. The `-100k` parameter specifies the size criterion.

### Option 3: `-type`
The `-type` option allows us to search based on file type

**Example 1:**
```bash
find ./technical -type f
```
This command searches for all normal files within the `./technical` directory and its subdirectories. The `-type f` option filters the search to only include regular files.

**Example 2:**
```bash
find ./technical -type d
```
This command searches for all directories within the `./technical` directory and its subdirectories. The `-type d` option filters the search to only include directories.

### Option 4: `-exec`
The `-exec` option allows us to include an extra command after using `-find`. It essentially makes a two liner a one liner. 

**Example 1:**
```bash
find ./technical -name "*.txt" -exec cat {} \;
```
This command searches for all files that end with ".txt" within `./technical` directory and its subdirectories. It then executes the `cat` command on each found file, displaying them , `{}` being their placeholder.

**Example 2:**
```bash
find ./technical -type f -exec rm {} \;
```
This command searches for all normal files within the `./technical` directory and its subdirectories. It then executes the `rm` command on each found file, removing them , `{}` being their placeholder.


---
title: Bash tricks
description: bash,tricks,development
---

Bash tricks or just code snippets for quick reusage.

#### Arguments

Passing argument in the bash script

```bash
# -p purpose
# -r report 
# -w workspace
# -d debug
while getopts p:r:w:d: flag; do
  case "${flag}" in
  p) purpose=${OPTARG} ;;
  r) report=${OPTARG} ;;
  w) workspace=${OPTARG} ;;
  d) debug=${OPTARG} ;;
  *) echo "Does not support additional arguments" ;;
  esac
done
```

Usage:

```bash
$ ./my_script.sh -p my_project -r my_report -w /home/workspace -d true
```

#### Checking boolean argument

Function for the usage in if block

```bash
function isTrue() {
  if [[ "${@^^}" =~ ^(TRUE|true|OUI|Y|O$|ON$|[1-9]) ]]; then return 0; fi
  return 1
}
```

Usage

```bash
#somewhere
debug=true

if isTrue "$debug"; then
  echo "[DEBUG] Message information"
fi
```

#### Loop through files

```bash
for file in /path_to_the_folder/*; do
  ....
  continue #if needed
  ....
done
```

#### Check the file is a file

```bash
if test -f "$file_path"; then
  echo "$file_path is a file."
fi
```

#### Check the file is a directory

```bash
if test -d "$file_path"; then
  echo "$file_path is a directory."
fi
```

#### Get the folder name from a file path

```bash
file_path="/some/path/to/the/folder"
...
folder_name="${file_path##*/}"
```

#### Create folder or folders
```bash
mkdir /path/to/folder
```
Create all folders in a path if they are not exist
```bash
mkdir -p /path/to/folder/and/not/existed/folders
```


---

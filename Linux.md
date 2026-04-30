## File System Basics
- A directory is like a folder, which can hold files and other directories
- The current directory is represented by the path `.`
- The current directory's parent directory (the directory it is located in) is represented by the path `..`
  - The parent directory's parent is represented by `../..`, and so on 
### Navigating the File System
- `ls` will list all the files and directories in your current working directory
- `cd <dir>` will navigate into the directory `dir`
  - `cd ..` will navigate to the parent directory
- `pwd` will print the current directory's path
### Creating, Moving, and Deleting Files
- `touch <filename>` will create a new file named `filename`
- `mkdir <dirname>` is used to create a new directory named `dirname`. It will be located in the current working directory.
- `rm <filename>` will delete the file at path `filename`
  - `rm -r <dirname>` will recursively delete the contents of a directory and the directory itself
- `cp <oldpath> <newpath>` will copy the file at `oldpath` to the location indicated by `newpath`
  - `cp example.txt ../example.txt` will copy a file `example.txt` from the working directory into the parent directory
- `mv <oldpath> <newpath>` will move the file at `oldpath` to the location indicated by `newpath`
  - This is also used to rename files: `mv example.txt example1.txt` will rename `example.txt` to `example1.txt`
### More useful File Operations
- `diff <file1> <file2>` will list the differences between `file1` and `file2`
- `grep <pattern> <file>` will search for instances of the RegEx `pattern` in `file`
  - Check out this resource ([link]([url](https://www.geeksforgeeks.org/linux-unix/grep-command-in-unixlinux/))) for more info about using grep

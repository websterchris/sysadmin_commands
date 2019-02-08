# Common Symbols

```  bash
### STDOUT (Standard Output) ###
    Write the output of a programme into a file
    >
    # Example 
    ls > ls.txt (Will store the output of ls into ls.txt)

```

# File Management
``` bash

# Create Directory
mkdir {directory_name}

# Create File 
touch {file_name}.{file_extension}

# Remove File
rm {file_name}.{file_extension}

# Remove directory and its contents
rm -rf {directory}
```


# MYSQL

## Dump Database

``` bash
# Dump all databases
mysqldump -u {user} -p --all-databases > {dump_filename}.sql

# Dump single database
mysqldump -u {user} -p {db_name} > {dump_filename}.sql

# Dump specific tables in a database
mysqldump -u {user} -p {db_name} {table_1} {table_2} > {dump_filename}.sql

# Dump remote database
mysqldump -P {port} -p -h {host} -u {user} {db_name} > {dump_filename}.sql

# Gzip dump output (recommended)
mysqldump -u {user} -p {db_name} | gzip > {dump_filename}.sql.gz
```


## Restore Database from dump

``` bash
# Dump uncompressed database dump
mysql -u {user} -p {db_name} < {dump_filename}.sql

# Dump uncompressed database dump
mysql -P {port} -h {host} -u {user} -p {db_name} < {dump_filename}.sql

# Dump gzipped database dump
gunzip < {dump_filename}.sql.gz | mysql -u {user} -p {db_name}
```

## Note:
1. If you do not specify a password with the `-p` flag it will prompt for a password. It is not recommended to include a password as it may be logged and easily retrieved by malware or hackers.
2. **Lowercase** `-p` is password. **Uppercase**  `-P` is port



# Searching Files

``` bash
# Search for a string within a directory
grep -r '{pattern}' {directory}
# Search for a string within a file
grep -r '{pattern}' {filename}.{file_extension}
```

# SSH 

# Users

``` bash
# Create a user (Must be root / su)
adduser {username}

# Add user to sudo group (Allows them to execute commands as root)
adduser {username} sudo
```

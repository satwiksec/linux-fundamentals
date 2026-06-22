# Permissions in Linux

Linux uses a permission system to control who can read, modify, or execute files and directories. Permissions are commonly managed using the `chmod` command.

## Viewing Permissions

Permissions can be viewed using:

```bash
ls -l
```

Example output:

```text
-rwx-wx-rwx
```
![](images/permission.png)

## Understanding the Permission String

A permission string consists of 10 characters.

### File Type

The first character indicates the file type:

```text
- = Regular file
d = Directory
```

Examples:

```text
-rwx-wx-rwx
drwxr-xr-x
```


### Permission Types

```text
r = Read
w = Write
x = Execute
```

## Modifying Permissions

Permissions can be modified using the `chmod` command.

### Grant Permissions

```bash
chmod u+rwx myscript.sh
```

This command grants the owner (`u` = user) permission to:

- Read (`r`)
- Write (`w`)
- Execute (`x`)

the file `myscript.sh`.

### Remove Permissions

```bash
chmod u-r myscript.sh
```

This command removes the read permission from the owner of the file.

## Common Symbols

```text
u = User (Owner)
g = Group
o = Others
a = All
```

Example:

```bash
chmod a+rwx myscript.sh
```

This grants read, write, and execute permissions to everyone.

## Cybersecurity Relevance

File permissions are one of the most important security mechanisms in Linux.

Proper permissions help:

- Prevent unauthorized access to files
- Restrict modification of sensitive data
- Protect system configuration files
- Reduce the impact of compromised user accounts

Misconfigured permissions can allow attackers to read, modify, or execute files they should not have access to.

## Summary

Key concepts:

```text
r = Read
w = Write
x = Execute

u = User
g = Group
o = Others
a = All
```

Useful commands:

```bash
ls -l
chmod u+rwx myscript.sh
chmod u-r myscript.sh
chmod a+rwx myscript.sh
```

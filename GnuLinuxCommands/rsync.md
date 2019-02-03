You can use `rsync` instead of `cp`. It is more reliable for copy/backup a large number of files.

# Using trailing Slash

Note the following two commands:

```
rsync ~/foo ~/backup
rsync ~/foo/ ~/backup
```

In the first command directory `~/foo` will becopied into `/backup/foo`. In the second command all contents of `~/foo` will be copied into `~/backup`. You can think of a trailing / on a source as meaning "copy the contents of this directory" as opposed to "copy the directory by name". In other words, the following two commands have the same structure in the target directory:

```
rsync ~/foo ~/backup
rsync ~/foo/ ~/backup/foo
```

# Archive Mode

Like `cp`, you can use rsync with `-a` flag which means archive mode.

# Dry run

You can use `-n` or `--dry-run` flag to perform a trial run with no changes made. It is recommended to run in this mode for avoiding unwanted results.

# Updating Extended attributes

If you want to preserve extended attributes you can use `-X` or `--xattrs` flag.

# Backup a Directory Regularly

I usually use the following command to backup my data directory:

```
rsync -aX --delete --progress --exclude-from=./exclude-NixData --delete-excluded /path/to/data /path/to/backup 

```


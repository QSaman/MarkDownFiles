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

If you want to preserve extended attributes you can use `-X` or `--xattrs` flag. If you want to preserve extended attributes in NTFS, use `--fake-super` to avoid rsync from hanging.

# Backup a Directory Regularly

I usually use the following command to backup my data directory:

```
rsync -aAX --delete --progress --fake-super --exclude-from=./exclude-NixData --delete-excluded /path/to/data /path/to/backup 
rsync -aAX --fake-super --progress source dest
```
If you want the remove the source files after synching, you can use the following command:

```
rsync -aAX --fake-super --remove-source-files --progress source dest
```
Note the the above command only removes files and not directories. To remove empty directories run the following command:

```
find -type d -empty -delete
```


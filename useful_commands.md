## Image Conversion
Command to converting images from jpg to png in a directory.
```
cd to/the/slected/ditrectory
mogrify -format png *.jpg    
```
## [Move all files with a certain extension from multiple subdirectories into one directory](https://unix.stackexchange.com/questions/67503/move-all-files-with-a-certain-extension-from-multiple-subdirectories-into-one-di)

This one is safe when moving data and error free which supported most of all distro regardless versions. This command will scan subdirectories and then move or copy to your new destination directory.
```
find . -name *.jpg -exec mv '{}' "./jpg/" ";"
```

* Run this command at the main directory that contains sub-directories with the files you wish to move.

* Where you can change `*.jpg` to anything like `*.zip` in your case. Or `*.doc` just any extension works.
* and `mv` is the command to move files, or you can use `cp` to copy data instead of moving.
* `./jpg/` is the destination directory that I want to move all `jpg` files to. You can also give it a full path like `/home/myid/jpg/`

## Add Suffix to all files in a folder

```
for f in * ; do mv -- "$f" "PRE_$f" ; done
```
or
For adding prefix or suffix for files(directories), you could use the simple and powerful way by xargs:
 ```
 ls | xargs -I {} mv {} PRE_{}

 ls | xargs -I {} mv {} {}_SUF
```

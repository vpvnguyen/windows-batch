# windows-batch

## xcopy
### copy all files to folder
```
@echo off
xcopy /s c:\source d:\target
```
/s/e - recursive copy, including copying empty directories.
/v - add this to verify the copy against the original. slower, but for the paranoid.
/h - copy system and hidden files.
/k - copy read-only attributes along with files. otherwise, all files become read-write.
/x - if you care about permissions, you might want /o or /x.
/y - don't prompt before overwriting existing files.
/z - if you think the copy might fail and you want to restart it, use this. It places a marker on each file as it copies, so you can rerun the xcopy command to pick up from where it left off.
If you think the xcopy might fail partway through (like when you are copying over a flaky network connection), or that you have to stop it and want to continue it later, you can use xcopy /s/z c:\source d:\target.

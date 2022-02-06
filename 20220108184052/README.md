# script to manage scratch buffers

The idea is to create a bash script that creates a scratch buffers with
particular extension file type on the `/tmp` folder, with that we can
just open on every place

Will be pretty simple actually, I'll just create the file and return the
path so I can pipe it to vim or just get the content on command line.

```sh
#!/bin/bash

path="/tmp/scratch.$1"

if [ -z $path ]; then
	touch $path
	echo $path
else
	echo $path
fi
```

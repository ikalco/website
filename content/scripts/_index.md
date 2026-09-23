+++
draft = false
title = 'Scripts'
+++

Bash

Directory Size: will list one level of subdirectories and their sizes in human readable form
```bash
drsz () {
	do_dir="." 
	extra="" 
	while test $# != 0
	do
		if [ -d $1 ]
		then
			do_dir=$1 
		else
			extra="$extra $1" 
		fi
		shift
	done
	(
		cd $do_dir
		pwd
		eval "du$extra -d1 -c -h -x 2>/dev/null | sort -h"
	)
}
```

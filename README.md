# ebadblocks

`ebadblocks` is a version of [`badblocks`](https://git.kernel.org/pub/scm/fs/ext2/e2fsprogs.git/tree/misc/badblocks.c) with extended functionality.

## Features
### Continuing the last run
`badblocks` potentially takes a (very) long time to run.
`ebadblocks` provides support for keeping track of where the last run was stopped in order to easily continue later.

`ebadblocks` achieves this by saving the last completed block in the `./.ebadblocks` file. The run can then be continued from the last completed block by passing the `--continue` flag.

Example:
```
sudo ./ebadblocks -vnf /dev/loop0 1000000 100
# Kill the process by pressing Ctrl + C
sudo ./ebadblocks -vnf --continue /dev/loop0 1000000
```

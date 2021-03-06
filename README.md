## HDFS-CLI

HDFS-CLI is an interactive command line shell that makes interacting with the Hadoop Distribted Filesystem (HDFS)
simpler and more intuitive than the standard command-line tools that come with Hadoop. If you are familiar with OS X, Linux, or even Windows terminal/console-based applications, then you are likely familiar with features such as tab completion, command history, and ANSI formatting.

### Basic Usage
HDFS-CLI works much like a command-line ftp client: You first establish a connection to a remote HDFS filesystem,
then manage local/remote files and transfers.

To start HDFS-CLI, run the following command:

	java -jar hdfs-cli-2.1.0-SNAPSHOT-shaded.jar

### Release Notes

#### 2.0.0

	- Initial Forked Release of P. Taylor Goetz.
	- Update to 2.6.0 Hadoop Libraries
	- Re-wrote Command Implementation to use FSShell as basis for issuing commands.
	- Provide Context Feedback in command window to show local and remote context.
	- Added several missing hdfs dfs commands that didn't exist earlier.

#### 2.1.0

	- Added support for create/delete/rename Snapshot

#### Local vs. Remote Commands
When working within a HDFS-CLI session, you manage both local (on your computer) and remote (HDFS) files. By convention, commands that apply to both local and remote filesystems are differentiated by prepending an `l`
character to the name to denote "local".

For example:

`lls` lists local files in the local current working directory.

`ls` lists remote files in the remote current working directory.

Every HDFS-CLI session keeps track of both the local and remote current working directories.

### Binary Package

[All-in-One Distributable Jar](https://github.com/dstreev/hdfs-cli/raw/master/lib/hdfs-cli-2.1.0-SNAPSHOT-shaded.jar)

### Available Commands

#### Common Commands
	connect		connect to a remote HDFS instance
	help		display help information
	put			upload local files to the remote HDFS
    get			(todo) retrieve remote files from HDFS to Local Filesystem

#### Remote (HDFS) Commands
	cd		 change current working directory
	ls		 list directory contents
	rm		 delete files/directories
	pwd		 print working directory path
	cat		 print file contents
	chown	 change ownership
	chmod	 change permissions
	chgrp	 change group
	head	 print first few lines of a file
	mkdir	 create directories
	count    Count the number of directories, files and bytes under the paths that match the specified file pattern.
	stat     Print statistics about the file/directory at <path> in the specified format.
	tail     Displays last kilobyte of the file to stdout.
	text	 Takes a source file and outputs the file in text format.
	touchz Create a file of zero length.
	usage	 Return the help for an individual command.

	createSnapshot	Create Snapshot
	deleteSnapshot	Delete Snapshot
	renameSnapshot	Rename Snapshot

#### Local (Local File System) Commands
	lcd		 change current working directory
	lls		 list directory contents
	lrm		 delete files/directories
	lpwd	 print working directory path
	lcat	 print file contents
	lhead	 print first few lines of a file
	lmkdir	 create directories
	
### Command Documentation
Help for any command can be obtained by executing the `help` command:

	help pwd

Note that currently, documentation may be limited.


### Known Bugs/Limitations

* No support for paths containing spaces
* No support for Windows XP
* Path Completion for chown, chmod, chgrp is broken

### Road Map

- Support input script
- Support input variables
- Expand to support Extended ACL's (get/set)
- Add Support for setrep
- HA Commands
	- NN and RM
	





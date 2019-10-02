#Command Line

## reminder of some tools
* `wc` - count the number of lines,words,characters
* `tail` - see the last N lines of a file
* `head` - see the first N lines of a file
* `cat` - print out entire file to screen
* `sed` - 'stream editor' - edit data stream on the fly
* `curl` - downloading tool for web/ftp data streams
* `which` - list path to a program based on the $PATH
* `pwd` - print the current working directory
* `ps` - processes running on the system
* `man` - view manual pages about a command or program
* `date` - date and time
* `time` - prefix a command/program, report how long it took to run
* `find` - find files/folders by name or other property
* `du` - reports disk usage (e.g. how big a file or folder is)
* `awk` - a simple language for processing files/great for column delimited data

## Reminder of some commands while at the command line

* `^` means "Control key"
* cancel a running application: `^C`
* end a session: `^D` (End of File message)
* Tab to try to autocomplete (applications, filenames, directories)
* While typing on cmdline - jump to end of line: `^E`
* Get back to the beginning of line: `^A`
* Up and down keys cycle through history of commands
* Type `!!` to execute the last command
* Type `history` to see list of previous commands
* Type `!NUMBER` to excute cmd from that list
* Type `!g` to run the last command that started with `g`

## Processes

UNIX allows multiple processes (programs) to be run at the same time. While at the command line you can run a specific process, but your command line will be blocked until that program is finished.

Try this which will run a task which just pauses for 30 seconds.

```bash
sleep 30
```

Jobs are run in the foreground by default. While a job is running use `^Z` to suspend job.

```bash
sleep 30
^Z
[1]+  Stopped                 sleep 30
```

To keep the job running but put it in the **background** use the command `bg` which will puts process in background.
```
$ bg 
[1]+ sleep 30 &
```

If you want to put the job back in the foreground so you can interact with it or force cancel it use the command `fg`.
```bash
$ fg
fg
sleep 30
```

To launch a job directly into the background put an `&` at the end.

```bash
$ sleep 30 &
```

It can still be brought to the foreground with `fg`.

A typical use if you are using a tool which generates graphical
interface that you will interact with is to launch it in
background. It will print out the process id of the command that is
running.

```bash
$ emacs &
[1] 25341
```

# More file manipulation

## Copying files

To copy a file use the command `cp`.

```bash
$ cp one.txt two.txt# copy one file to another
$ mkdir books # make a directory
$ cp one.txt books        # copy into a directory
$ ls books                # list the contents
one.txt
$ cp books more_books     # copy the folder, will fail
cp: books is a directory (not copied).
$ cp -r books more_books  # recursive copy succeeds
$ cp one.txt two.txt books # can copy more than one at a time
                           # will also OVERWRITE the previous
                           # one.txt that was in the folder
$ ls books
$ ls more_books
```

The command `rsync` can also be used to copy files between folders or between computers.

Here we copy a file that is located on your laptop called LOCALFILE onto the HPCC and will put it in the folder bigdata which is located in your home directory.

```bash
[your laptop] $ rsync -a --progress LOCALFILE USER@cluster.hpcc.ucr.edu:bigdata/
```

Can also specify an explicit path (starts with `/`). 
```bash
[your laptop] $ rsync -a --progress LOCALFILE USER@cluster.hpcc.ucr.edu:/bigdata/gen220/USER/
```

Can copy FROM HPCC to your local computer
```bash
[your laptop] $ rsync -a --progress USER@cluster.hpcc.ucr.edu:/bigdata/gen220/share/simple/yeast_gene_names.txt
```

## Moving files

Moving files is just renaming them.

```bash
$ mv one.txt three.txt     # rename one.txt to three.txt
$ mv three.txt books       # relocate three.txt to books folder
$ cd books
$ mv one.txt two.txt three.txt .. # move these files back UP one
directory
$ ls                       # nothing in the 'books' directory
$ cd ..                    # go back
$ ls                       # these files are in the current folder
one.txt two.txt three.txt books more_books
$ ls books                 # is now empty, we moved everything
                           # out of there
```


# Running programs

How does UNIX determine what program to run?

Try typing `echo $PATH` to see your search directory.
Also do `env` to see all environment variables.

You can use the command `which` to tell you where a program is located
```bash
which nano # will tell you where the nano program
           # is located
```



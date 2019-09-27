# Logging into Cluster

Existing documentation and tutorial available at http://hpcc.ucr.edu/

See the [Linux Basics](http://hpcc.ucr.edu/manuals_linux-basics_intro.html)

# Local access

Still need to connect to the server 

# Web Access with Jupyter

sbatch /bigdata/gen220


# Set some aliases in your environment

Edit your ~/.bash_aliases file

add
```
alias sq='squeue -u $USER -o "%.18i %.9P %.8j %.8u %.8T %.10M %.9l %.6D %C %m %R"'
```

Edit your ~/.bashrc, add the lines to the bottom if you do not already have
any mention of .bash_aliases in there

```
if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
fi
```

# awesome-terminal
A list of terminal and bash commands and tweaks that I frequently use.

#### Find and delete all file with certain names
```sh
find . -name .ipynb_checkpoints -prune
find . -name .ipynb_checkpoints -prune -exec rm -rf {} \;
```

#### Mounting rmeote directory via ssh
```sh
sudo sshfs -o allow_other,default_permissions user@remote_address:/path/to/remote_directory /path/to/local_directory
```

#### Connect remote localhost to my localhost (Usefull for running Jupyter Notebooks via remote connection  )
```sh
ssh -N -f -L localhost:8890:localhost:8889 user@remote_address
```

#### Start Jupyter Notebooks without browser
```sh
jupyter notebook --no-browser --port=8887
```

#### Add shorter-commands for big command line instruction using aliases
Add the following line inside `~/.bash_aliases`
```sh
alias jupyter-notebook-remote='ssh -N -f -L localhost:8890:localhost:8889 user@remote_address'
```

#### Looping through folders in the current directory
```sh
for dir in "${array[@]}"; do cd $dir && pwd && cd ..; done
```

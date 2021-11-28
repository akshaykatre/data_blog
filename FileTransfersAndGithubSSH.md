### Brace expansions in file transfers 

If you want to selectively transfer files using scp/ rsync, the following can be used: 
```shell
scp -r <source directory>/*{<extensions or file names>} <target location> 
```

Example: 

```shell
scp -r test/*{.py,.json,.db,assets} user@destinationip:/home/user/testfolder/
```

The above will transfer the files with extensions .py, .json, .db and any file/ folder ending with the name assets. 


### Github SSH 

The information is based from here: [Generating SSH keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

Create your SSH key (on linux machine) with the following: 
```shell
$ ssh-keygen -t ed25519 -C <info about machine as identifier> 
```

Example: 
```shell
$ ssh-keygen -t ed25519 -C user@raspberrypi
```
The idea is that you could create a SSH key for every machine you work on. 



https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

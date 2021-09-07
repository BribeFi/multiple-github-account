# how to setup the multiple github account

As defi surface grows and ideas are bigger than your day job can handle.  
So many defi teams choose to be anonymous in various reasons.  
And for developers, it is critical to separate the day job github account and shadowy super coder github account  
So here is the instruction how to handle this situation without authoring the commit with the inapropriate account  

## Instruction
for this instruction, i'm going to **ONLY** explain how to do this with ssh protocol, don't expect me to fix/test this for https  
**I'm not going to test this in some other envrionments like windows or linux, this is for mac**
### prerequisites

1. Use mac
2. Create secondary account
3. Create ssh file for secondary account  
    `ssh-keygen -t ed25519 -C "secondary@protonmail.com"`  
    remember where it is going to be stored. let's assume it is stored in `~/.ssh/id_ed25519_secondary`  
    also add this in your github account. see [here](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh) for detailed explanation
4. install [homebrew](https://brew.sh/)

### separating the directory

make sure your secondary account related project are staying in the same folder.  
And make sure non-related projects are not included there.

For me, i just made a `Bribe.fi` folder in `~/`.

And i'm going to assume that you've made a directory like `~/Secondary`

### direnv

we are going to use `direnv` to separate environments easily.

`brew install direnv`

### setting the envrionment variables

by using direnv, it is possible to set the envrionment variables set per directory

since we've made a separate directory for secondary account, let's set the envrionment there.

make your `~/Secondary/.envrc` are filled like this

```
export GIT_AUTHOR_NAME=secondary
export GIT_AUTHOR_EMAIL=secondary@protonmail.com
export GIT_COMMITTER_NAME=secondary
export GIT_COMMITTER_EMAIL=secondary@protonmail.com
export GIT_SSH_COMMAND="ssh -i ~/.ssh/id_ed25519_secondary"
```

and activate the .envrc

run `direnv allow` inside `~/Secondary`

that's it! you are now able to commit as secondary account whenever you are working inside the `~/Secondary`.

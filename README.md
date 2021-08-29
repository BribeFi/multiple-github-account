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
    `ssh-keygen -t ed25519 -C "yourmail@protonmail.com"`  
    remember where it is going to be stored. let's assume it is stored in `~/.ssh/id_ed25519_secondary`
### 

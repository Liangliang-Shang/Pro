# Remote repository - GitHub
## Config SSH
1. Generate Keys
    ```
    @Liangliang-Shang ➜ ~ $ ls -la .ssh
    ls: cannot access '.ssh': No such file or directory

    @Liangliang-Shang ➜ ~ $ ssh-keygen -t rsa -C liangliang.shang@icloud.com
    Generating public/private rsa key pair.
    Enter file in which to save the key (/home/codespace/.ssh/id_rsa): 
    Created directory '/home/codespace/.ssh'.
    Enter passphrase (empty for no passphrase): 
    Enter same passphrase again: 
    Your identification has been saved in /home/codespace/.ssh/id_rsa
    Your public key has been saved in /home/codespace/.ssh/id_rsa.pub
    The key fingerprint is:
    SHA256:NeE3ExKQUeyGSRcuib/XB9/QjzJHjaYPy1p4iZIkdS0 liangliang.shang@icloud.com
    The key's randomart image is:
    +---[RSA 3072]----+
    |        o**o.    |
    |       .o+o+ .   |
    |      ..+=E =    |
    |       oo+o+ o + |
    |      . S.  . = o|
    |       o o + B +.|
    |        + + X = o|
    |         o + O   |
    |          ..o .  |
    +----[SHA256]-----+

    @Liangliang-Shang ➜ ~ $ ls -la .ssh
    total 20
    drwx--S--- 2 codespace codespace 4096 Mar  7 15:14 .
    drwxrwsr-x 1 codespace codespace 4096 Mar  7 15:14 ..
    -rw------- 1 codespace codespace 2610 Mar  7 15:14 id_rsa
    -rw-r--r-- 1 codespace codespace  581 Mar  7 15:14 id_rsa.pub

    @Liangliang-Shang ➜ ~ $ ssh -T git@github.com
    The authenticity of host 'github.com (20.205.243.166)' can't be established.
    ECDSA key fingerprint is SHA256:p2QAMXNIC1TJYWeIOttrVc98/R1BUFWu3/LiyKgUfQM.
    Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
    Warning: Permanently added 'github.com,20.205.243.166' (ECDSA) to the list of known hosts.
    git@github.com: Permission denied (publickey).

    @Liangliang-Shang ➜ ~ $ ssh -T git@github.com
    git@github.com: Permission denied (publickey).

    # No publickey on GitHub!!?
    ```
1. Distribute the pub key to the target
    ```
    # Copy the content of id_rsa.pub to New SSH Key on https://github.com/settings/keys
    ```
1. Test SSH Connection
    ```
    @Liangliang-Shang ➜ ~ $ ssh -T git@github.com
    The authenticity of host 'github.com (20.205.243.166)' can't be established.
    ECDSA key fingerprint is SHA256:p2QAMXNIC1TJYWeIOttrVc98/R1BUFWu3/LiyKgUfQM.
    Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
    Warning: Permanently added 'github.com,20.205.243.166' (ECDSA) to the list of known hosts.
    Hi Liangliang-Shang! You've successfully authenticated, but GitHub does not provide shell access.

    @Liangliang-Shang ➜ ~ $ ssh -T git@github.com
    Hi Liangliang-Shang! You've successfully authenticated, but GitHub does not provide shell access.
    ```

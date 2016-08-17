Spacedock
=========

This repo controls my Docker cluster(s).

Setup
-----

### Adding Linode Nodes

1. Boot new Ubuntu instance.
2. Set up pbyrne user:
    1. `useradd pbyrne`
    2. `echo "pbyrne ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/pbyrne`
3. Configure SSH for pbyrne:
    1. `su pbyrne`
    2. `mkdir ~/.ssh && touch ~/.ssh/authorized_keys && chmod -R 700 ~/.ssh`
    3. `curl https://github.com/pbyrne.keys > ~/.ssh/authorized_keys`
4. Verify SSH for pbyrne: `ssh pbyrne@$SERVER_IP`.
5. Lock down SSH by editing `/etc/ssh/sshd_config`:
    1. Change the line `PermitRootLogin yes` to `PermitRootLogin no`
    2. Change the line `#PasswordAuthentication yes` to `PasswordAuthentication no`
    3. `service sshd restart`
3. Install Docker server components: TK

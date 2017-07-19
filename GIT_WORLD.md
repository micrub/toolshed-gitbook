# Git World

## Gitlab Community edition - self hosting

### Installation

```
sudo apt-get install curl openssh-server ca-certificates postfix

curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | sudo bash
```

Install using apt-get:
```
sudo apt-get install gitlab-ce
```

Or:
```
dpkg -i gitlab-ce-XXX.deb
```
Configure Gitlab:

```
sudo gitlab-ctl reconfigure

```

### Verify - Browse to the hostname and login

Use following address in browser [ http://localhost/ ](http://localhost/) , configure appropriate
firewall rules to get access from external interface if necessary. By default gitlab
installed on port 80.

On your first visit, you'll be redirected to a password reset screen to provide
the password for the initial administrator account. Enter your desired password
and you'll be redirected back to the login screen.

The default account's username is **root**. Provide the password you created earlier
and login. After login you can change the username if you wish.

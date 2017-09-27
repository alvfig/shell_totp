# shell_totp
Shell script to show time-based one-time passwords - TOTP. It's like Google Authenticator on a TTY. You execute `tokens` command and view your 2FA codes with a countdown timer.
```
2017-09-25T12:41:12-03:00
Remaining :     18 ::::::::::::::::::............

Facebook  : 916476
Google    : 738429
Twitter   : 551011

Type Ctrl-C to exit
```
## Install
It depends on `oathtool` package. You must install it first, like the example below for Debian based distros.
```
$ sudo apt install oathtool
```
Copy the `tokens` file to a PATH directory and make it executable.
```
$ cp tokens ~/bin/
$ chmod +x ~/bin/tokens
```
Copy the `.tokensrc` setup file to your home directory.
```
$ cp .tokensrc ~/
```
## Configure
Create a secrets file like the provided sample one, with a name and a secret at each line, separated by a space.
```
Facebook XXXXXXXXXXXXXXXX
Google YYYYYYYYYYYYYYYY
Twitter ZZZZZZZZZZZZZZZZ
```
Edit the `~/.tokensrc` configuration file, adjusting the variables `secretsfile` and `barstyle` according to your setup.

The variable `secretsfile` contains the path and name of the secrets file above, like the excerpt below.
```
secretsfile=~/bin/tokens.secrets
```
You can play with the variable `barstyle` too, if you dare.
```
barstyle='#_'
```
Finally, it's not a bad idea to give some protection to your secrets file.
```
$ chmod 0600 ~/bin/tokens.secrets
```
That's it!

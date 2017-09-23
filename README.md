# shell_totp
Shell scritp to show time-based one-time passwords - TOTP. It's like Google Authenticator on a TTY. You execute `tokens` command and view your 2FA codes with a countdown timer.
```
2017-09-22T22:20:12-03:00
Remaining :     18

Facebook  : 421785
Google    : 584399
Twitter   : 772316

Type Ctrl-C to exit
```
## Installing
It depends on oathtool package. You must install it first like the example bellow to Debian based distros.
```
$ sudo apt install oathtool
```
Copy the `tokens` file to a PATH directory and make it executable.
```
$ cp tokens ~/bin/
$ chmod +x ~/bin/tokens
```
## Configuring
Create a secrets file like the sample one, with a name and a secret at each line, separated by a space.
```
Facebook XXXXXXXXXXXXXXXX
Google YYYYYYYYYYYYYYYY
Twitter ZZZZZZZZZZZZZZZZ
```
Edit the `tokens` executable file putting the secrets file on the variable `secretsfile`, like the excerpt bellow.
```
secretsfile=~/bin/tokens.secrets
```

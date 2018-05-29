# shell_totp
Shell script to show time-based one-time passwords - TOTP. It's like Google Authenticator on a TTY. You execute `tokens` command and view your 2FA codes with a countdown timer.

If `xclip` or `xsel` are installed, you can copy a token to clipboard pressing its correspondig key. Paste with the middle button of the mouse.

Press `0` (zero) to exit.
```
1) Facebook  : 983696       3) Twitter   : 729450       5) Linkdn    : 394880
2) Google    : 755636       4) Github    : 957090       6) Tumblr    : 538786

0) Exit

   Remaining :      5 :::::.........................  2018-05-28 20:56:25
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
Github GGGGGGGGGGGGGGGG
Linkdn LLLLLLLLLLLLLLLL
Tumblr TTTTTTTTTTTTTTTT
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
Finally, it's not a bad idea to give some privacy to your secrets file.
```
$ chmod 0600 ~/bin/tokens.secrets
```
## Troubleshoot
Remember that the clock of the system must be correct.

Currently, there is a limit of 61 tokens.

That's it!

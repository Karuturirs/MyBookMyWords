## Bash world

#### Bash shortcuts
```cmd
shopt -s cdspell    //(corrects typoos)
ctrl + _            //(undo)
ctrl + arrow        //(move forward a word)
ctrl + a            //(move cursor to start)
ctrl + e            //(move cursor to end)
ctrl + k            //(cuts everything after the cursor)
ctrl + l            //(clears screen)
ctrl + q            //(resume command that is in the foreground)
ctrl + s            //(pause a long running command in the foreground)
ctrl + t            //(swap two characters)
ctrl + u            //(cuts everything before the cursor)
ctrl + x + ctrl + e //(opens the command string in an editor so that you can edit it before it runs)
ctrl + x + *        //(expand glob/star)
ctrl + xx           //(move to the opposite end of the line)
ctrl + y            //(pastes from the buffer)
ctrl + shift + c/v  //(copy/paste into terminal)
```

#### Running commands in sequence
> && (run second command if the first is successful)
> ; (run second command regardless of success of first one)

#### Redirecting I/O
> 2>&1 (redirect stdout and stderr to a file)

#### check for open ports
```echo > /dev/tcp/<server ip>/<port>```

#### Examine executable
which <command>
file <path/to/file>
command -V <some command binary> (tells you whether <some binary> is a built-in, binary or alias)


#### History related
```cmd
ctrl + r (reverse search)
!! (rerun last command)
!* (reuse arguments from previous command)
!$ (use last argument of last command)
shopt -s histappend (allow multiple terminals to write to the history file)
history | awk 'BEGIN {FS="[ \t]+|\\|"} {print $3}' | sort | uniq -c | sort -nr | head (list the most used history commands)
history | awk '{print $1}' | sort  | uniq -c | sort --numeric-sort --reverse | head -10
```

#### File and navigation
```cmd
cp /home/foo/realllylongname.cpp{,-old}
cd -
rename 's/text_to_find/been_renamed/' *.txt
export CDPATH='/var/log:~' (variable is used with the cd built-in.)
```

#### enable colors
```cmd
eval "`dircolors -b`"
```

#### force ls to always use color and type indicators
```cmd
alias ls='ls -hF --color=auto'
```
#### make the dir command work kinda like in windows (long format)
```cmd
alias dir='ls --color=auto --format=long'
```
#### make grep highlight results using color
```cmd
export GREP_OPTIONS='--color=auto'

export LESS_TERMCAP_mb=$'\E[01;31m'
export LESS_TERMCAP_md=$'\E[01;33m'
export LESS_TERMCAP_me=$'\E[0m'
export LESS_TERMCAP_se=$'\E[0m' # end the info box
export LESS_TERMCAP_so=$'\E[01;42;30m' # begin the info box
export LESS_TERMCAP_ue=$'\E[0m'
export LESS_TERMCAP_us=$'\E[01;36m'
```

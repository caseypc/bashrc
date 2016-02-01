# ~/.bashrc: executed by bash(1) for non-login shells.
# see /usr/share/doc/bash/examples/startup-files (in the package bash-doc)
# for examples

# If not running interactively, don't do anything
case $- in
    *i*) ;;
      *) return;;
esac

# don't put duplicate lines or lines starting with space in the history.
# See bash(1) for more options
HISTCONTROL=ignoreboth

# append to the history file, don't overwrite it
shopt -s histappend

# for setting history length see HISTSIZE and HISTFILESIZE in bash(1)
HISTSIZE=1000
HISTFILESIZE=2000

# check the window size after each command and, if necessary,
# update the values of LINES and COLUMNS.
shopt -s checkwinsize

# If set, the pattern "**" used in a pathname expansion context will
# match all files and zero or more directories and subdirectories.
#shopt -s globstar

# make less more friendly for non-text input files, see lesspipe(1)
[ -x /usr/bin/lesspipe ] && eval "$(SHELL=/bin/sh lesspipe)"

# set variable identifying the chroot you work in (used in the prompt below)
if [ -z "${debian_chroot:-}" ] && [ -r /etc/debian_chroot ]; then
    debian_chroot=$(cat /etc/debian_chroot)
fi

# set a fancy prompt (non-color, unless we know we "want" color)
case "$TERM" in
    xterm-color) color_prompt=yes;;
esac

# uncomment for a colored prompt, if the terminal has the capability; turned
# off by default to not distract the user: the focus in a terminal window
# should be on the output of commands, not on the prompt
#force_color_prompt=yes

if [ -n "$force_color_prompt" ]; then
    if [ -x /usr/bin/tput ] && tput setaf 1 >&/dev/null; then
    # We have color support; assume it's compliant with Ecma-48
    # (ISO/IEC-6429). (Lack of such support is extremely rare, and such
    # a case would tend to support setf rather than setaf.)
    color_prompt=yes
    else
    color_prompt=
    fi
fi

if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
fi
unset color_prompt force_color_prompt

# If this is an xterm set the title to user@host:dir
case "$TERM" in
xterm*|rxvt*)
    PS1="\[\e]0;${debian_chroot:+($debian_chroot)}\u@\h: \w\a\]$PS1"
    ;;
*)
    ;;
esac

# enable color support of ls and also add handy aliases
if [ -x /usr/bin/dircolors ]; then
    test -r ~/.dircolors && eval "$(dircolors -b ~/.dircolors)" || eval "$(dircolors -b)"
    alias ls='ls --color=auto'
    #alias dir='dir --color=auto'
    #alias vdir='vdir --color=auto'

    alias grep='grep --color=auto'
    alias fgrep='fgrep --color=auto'
    alias egrep='egrep --color=auto'
fi

# some more ls aliases
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'

# Add an "alert" alias for long running commands.  Use like so:
#   sleep 10; alert
alias alert='notify-send --urgency=low -i "$([ $? = 0 ] && echo terminal || echo error)" "$(history|tail -n1|sed -e '\''s/^\s*[0-9]\+\s*//;s/[;&|]\s*alert$//'\'')"'

# Alias definitions.
# You may want to put all your additions into a separate file like
# ~/.bash_aliases, instead of adding them here directly.
# See /usr/share/doc/bash-doc/examples in the bash-doc package.

if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
fi

# enable programmable completion features (you don't need to enable
# this, if it's already enabled in /etc/bash.bashrc and /etc/profile
# sources /etc/bash.bashrc).
if ! shopt -oq posix; then
  if [ -f /usr/share/bash-completion/bash_completion ]; then
    . /usr/share/bash-completion/bash_completion
  elif [ -f /etc/bash_completion ]; then
    . /etc/bash_completion
  fi
fi


###############################################################
###   CUSTOM
###############################################################

archey



if [ "$PS1" ]; then # if running interactively, then run till 'fi' at EOF:

# source ~/.bashlocalrc # settings that vary per workstation
OS=$(uname)     # for resolving pesky os differing switches





######################################################################################################################################################
###### COMMAND PROMPT & CLI ###### COMMAND PROMPT & CLI ###### COMMAND PROMPT & CLI ###### COMMAND PROMPT & CLI ###### COMMAND PROMPT & CLI ######
######################################################################################################################################################








##################################################
# Prompt escapes                 #
##################################################

# Bash allows these prompt strings to be customized by inserting a
# number of backslash-escaped special characters that are
# decoded as follows:

#  \a         an ASCII bell character (07)
#  \d         the date in "Weekday Month Date" format (e.g., "Tue May 26")
#  \D{format} the format is passed to strftime(3) and the result
#             is inserted into the prompt string an empty format
#             results in a locale-specific time representation.
#             The braces are required
#  \e         an ASCII escape character (033)
#  \h         the hostname up to the first `.'
#  \H         the hostname
#  \j         the number of jobs currently managed by the shell
#  \l         the basename of the shell's terminal device name
#  \n         newline
#  \r         carriage return
#  \s         the name of the shell, the basename of $0 (the portion following
#             the final slash)
#  \t         the current time in 24-hour HH:MM:SS format
#  \T         the current time in 12-hour HH:MM:SS format
#  \@         the current time in 12-hour am/pm format
#  \A         the current time in 24-hour HH:MM format
#  \u         the username of the current user
#  \v         the version of bash (e.g., 2.00)
#  \V         the release of bash, version + patch level (e.g., 2.00.0)
#  \w         the current working directory, with $HOME abbreviated with a tilde
#  \W         the basename of the current working directory, with $HOME
#             abbreviated with a tilde
#  \!         the history number of this command
#  \#         the command number of this command
#  \$         if the effective UID is 0, a #, otherwise a $
#  \nnn       the character corresponding to the octal number nnn
#  \\         a backslash
#  \[         begin a sequence of non-printing characters, which could be used
#             to embed a terminal control sequence into the prompt
#  \]         end a sequence of non-printing characters
#
#  The command number and the history number are usually different:
#  the history number of a command is its position in the history
#  list, which may include commands restored from the history file
#  (see HISTORY below), while the command number is the position in
#  the sequence of commands executed during the current shell session.
#  After the string is decoded, it is expanded via parameter
#  expansion, command substitution, arithmetic expansion, and quote
#  removal, subject to the value of the promptvars shell option (see
#  the description of the shopt command under SHELL BUILTIN COMMANDS
#  below).



##################################################
# Color chart                    #
##################################################

txtblk='\e[0;30m' # Black - Regular
txtred='\e[0;31m' # Red
txtgrn='\e[0;32m' # Green
txtylw='\e[0;33m' # Yellow
txtblu='\e[0;34m' # Blue
txtpur='\e[0;35m' # Purple
txtcyn='\e[0;36m' # Cyan
txtwht='\e[0;37m' # White
bldblk='\e[1;30m' # Black - Bold
bldred='\e[1;31m' # Red
bldgrn='\e[1;32m' # Green
bldylw='\e[1;33m' # Yellow
bldblu='\e[1;34m' # Blue
bldpur='\e[1;35m' # Purple
bldcyn='\e[1;36m' # Cyan
bldwht='\e[1;37m' # White
unkblk='\e[4;30m' # Black - Underline
undred='\e[4;31m' # Red
undgrn='\e[4;32m' # Green
undylw='\e[4;33m' # Yellow
undblu='\e[4;34m' # Blue
undpur='\e[4;35m' # Purple
undcyn='\e[4;36m' # Cyan
undwht='\e[4;37m' # White
bakblk='\e[40m'   # Black - Background
bakred='\e[41m'   # Red
badgrn='\e[42m'   # Green
bakylw='\e[43m'   # Yellow
bakblu='\e[44m'   # Blue
bakpur='\e[45m'   # Purple
bakcyn='\e[46m'   # Cyan
bakwht='\e[47m'   # White
txtrst='\e[0m'    # Text Reset



##################################################
# This bashrc's current prompt           #
##################################################

# PS1='\[\033]0;\w\007\]\[\e[35;1m\]\u\[\e[0m\]\[\e[32m\]@\h\[\e[34m\]\w \[\e[33m\]\$ \[\e[0m\]'  # purple, green, blue prompt w/default black & dir title

# PS1='\[\e[1;32m\]\u@\H:\[\e[m\] \[\e[1;37m\]\w\[\e[m\]\n\[\e[1;33m\]hist:\! \[\e[0;33m\] \[\e[1;31m\]jobs:\j \$\[\e[m\] ' # green, yellow, red, w/black output (2-tier) w/background job count

#PS1="\[\e]2;\u@\H \w\a\e[30;1m\]>\[\e[0m\] "
# trimmed up prompt w/black arrow & title is current dir.


# PS1="\`if [ \$? = 0 ]; then echo \[\e[33m\]^_^\[\e[0m\]; else echo \[\e[31m\]O_O\[\e[0m\]; fi\`[\u@\h:\w]\\$ "  # all black with happy face (yellow/red) upon successful completion

# PS1="\n\[\033[32;1m\]It's \t\[\033[33;1m\] Currently browsing \[\033[1;36m\]\w \[\033[33;1m\]directory\n\[\033[34;1m\]\`if [ \$? = 0 ]; then echo \[\e[37m\]Last Command Was Successfully Executed \[\e[32m\]^_^\[\e[0m\]; else echo \[\e[37m\]Smeggin Hell !!! Last Command Was Unknown \[\e[32m\]O_O\[\e[0m\]; fi\` \n\[\033[31m\]What is thy bidding, my master? \n\n\[\033[34;1m\]"               # green, yellow, grey, green, red, w/cyan output (3-tier) Star Wars version

# PS1="\n\[\e[30;1m\]\[\016\]l\[\017\](\[\e[34;1m\]\u@\h\[\e[30;1m\])-(\[\e[34;1m\]\j\[\e[30;1m\])-(\[\e[34;1m\]\@ \d\[\e[30;1m\])->\[\e[30;1m\]\n\[\016\]m\[\017\]-(\[\[\e[32;1m\]\w\[\e[30;1m\])-(\[\e[32;1m\]\$(/bin/ls -1 | /usr/bin/wc -l | /bin/sed 's: ::g') files, \$(/bin/ls -lah | /bin/grep -m 1 total | /bin/sed 's/total //')b\[\e[30;1m\])--> \[\e[0m\]"              # grey, cyan, green, w/black output (2-tier) w/ dir. info

#PROMPT_COMMAND=prepare_prompt

#prepare_prompt() {
#    if (( $? )); then
#        smiley='\[\e[37m\]You fucked up !!! \[\e[32m\]O_O\[\e[0m\]'
#    else
#        smiley='\[\e[32m\]^_^\[\e[0m\]'
#    fi
    #files=(*)
    #count=$#{files[@]}
    #count=$(ls -1 | wc -l | sed 's: ::g')
    #size=$(ls -lah | awk 'NR==1 {print $2} 1 {quit}')
    #size=$(ls -lah | grep -m 1 total | sed 's/total //')b
#}

#PS1='\n\[\e[30;1m\]\[\017\](\[\e[34;1m\]\u@\h\[\e[30;1m\])-(\[\e[34;1m\]Jobs \j\[\e[30;1m\])-(\[\e[34;1m\]\ \d\[\e[30;1m\])->\[\e[30;1m\]\n\[\017\](\[\e[32;1m\]\w\[\e[30;1m\])-(\[\e[32;1m\]$count files, $size b\[\e[30;1m\])\n$smiley \[\e[30;1m\]--> \[\e[0m\]'

#PS1="\n\[\e[30;1m\]\[\017\](\[\e[34;1m\]\u@\h\[\e[30;1m\])-(\[\e[34;1m\]Jobs: \j\[\e[30;1m\])-(\[\e[34;1m\]\@ \d\[\e[30;1m\])->\[\e[30;1m\]\n\[\017\](\[\e[32;1m\]$PWD\[\e[30;1m\])-(\[\e[32;1m\]$count files, $size\[\e[30;1m\])\n$smiley \[\e[30;1m\]--> \[\e[0m\]"


# PS1="\n\[\e[30;1m\]\[\017\](\[\e[34;1m\]\u@\h\[\e[30;1m\])-(\[\e[34;1m\]Jobs: \j\[\e[30;1m\])-(\[\e[34;1m\]\@ \d\[\e[30;1m\])->\[\e[30;1m\]\n\[\017\](\[\e[32;1m\]\w\[\e[30;1m\])-(\[\e[32;1m\]\$(/bin/ls -1 | /usr/bin/wc -l | /bin/sed 's: ::g') files, \$(/bin/ls -lah | /bin/grep -m 1 total | /bin/sed 's/total //')b\[\e[30;1m\])\n $smiley \[\e[30;1m\]--> \[\e[0m\]"



#lastcmd="\$?"

#PS1="\n\[\e[30;1m\]\[\017\](\[\e[34;1m\]\u@\h\[\e[30;1m\])-(\[\e[34;1m\]Jobs: \j\[\e[30;1m\])-(\[\e[34;1m\]\@ \d\[\e[30;1m\])->\[\e[30;1m\]\n\[\017\](\[\e[32;1m\]$PWD\[\e[30;1m\])-(\[\e[32;1m\]\$(/bin/ls -1 | /usr/bin/wc -l | /bin/sed 's: ::g') files, \$(/bin/ls -lah | /bin/grep -m 1 total | /bin/sed 's/total //')b\[\e[30;1m\])\n\$(if [[ ${lastcmd} == 0 ]]; then echo \" \[\e[32m\]^_^\[\e[0m\]\"; else echo \"\[\e[37m\]You fucked up !!! \[\e[32m\]O_O\[\e[0m\]\"; fi) \[\e[30;1m\]--> \[\e[0m\]"


#return value visualisation
#PS1="\$? \$(if [[ \$? == 0 ]]; then echo \"\[\033[0;32m\];)\"; else echo \"\[\033[0;31m\];(\"; fi)\[\033[00m\] : "

###### Shows the return value of the last executed command (using smileys as to whether it was successful or not)
# PROMPT_COMMAND='RET=$?; if [[ $RET -eq 0 ]]; then echo -ne "\033[0;32m$RET\033[0m ;)"; else echo -ne "\033[0;31m$RET\033[0m ;("; fi; echo -n " "'

###### Shows memory, load average, and history
# PROMPT_COMMAND='history -a;echo -en "\033[m\033[38;5;2m"$(( `sed -nu "s/MemFree:[\t ]\+\([0-9]\+\) kB/\1/p" /proc/meminfo`/1024))"\033[38;5;22m/"$((`sed -nu "s/MemTotal:[\t ]\+\([0-9]\+\) kB/\1/Ip" /proc/meminfo`/1024 ))MB"\t\033[m\033[38;5;55m$(< /proc/loadavg)\033[m"'


user="whoami"
host=$(echo -n $HOSTNAME | sed -e "s/[\.].*//")

function pre_prompt {
    newPWD="${PWD}"
    datenow=$(date "+%a, %d %b %y")
    filecount=$(/bin/ls -1 | /usr/bin/wc -l | /bin/sed 's: ::g')
    dirsize=$(/bin/ls -lah | /bin/grep -m 1 total | /bin/sed 's/total //')
    let promptsize=$(echo -n "--( $user@$host )-( ${PWD} )-( ${filecount} files )-( ${dirsize} )--" | wc -c | tr -d " ")
    let fillsize=${COLUMNS}-${promptsize}
    fill=""
    while [ "$fillsize" -gt "0" ]
        do
            fill="${fill}─"
            let fillsize=${fillsize}-1
    done
    if [ "$fillsize" -lt "0" ]
    then
        let cutt=3-${fillsize}
        xPWD="...${PWD:${cutt}}"
    fi
}

PROMPT_COMMAND=pre_prompt

# PS1="\e[36m┌─( \e[92m\u@\h\e[36m )─\${fill}─( \e[92m\$newPWD\e[36m )─( \e[92m\${filecount}files\e[36m )─( \e[92m\${dirsize}\e[36m )─<\n└─( \e[92m\$\e[36m )─>\[\e[0m\]"

PS1="\[\e[1;36m\]┌─( \[\e[1;92m\]\u@\H\[\e[1;36m\] )─\${fill}─( \[\e[1;92m\]\${newPWD}\[\e[1;36m\] )─( \[\e[1;92m\]\${filecount}files\[\e[1;36m\] )─( \[\e[1;92m\]\${dirsize}\[\e[1;36m\] )─<\n└─( \[\e[1;92m\]\$\[\e[1;36m\] )─>\[\e[0m\]"
# PS1='\[\e[1;32m\]\u@\H:\[\e[m\] \[\e[1;37m\]\w\[\e[m\]\n\[\e[1;33m\]hist:\! \[\e[0;33m\] \[\e[1;31m\]jobs:\j \$\[\e[m\]
##################################################
##################################################
##################################################







##################################################
# More PROMPT_COMMANDS               #
##################################################

###### Annoying PROMPT_COMMAND animation
# PROMPT_COMMAND='seq $COLUMNS | xargs -IX printf "%Xs\r" @'



###### Saves terminal commands in history file in real time (for use with 'shopt -s histappend')
if [ ! -f $HOME/.bash_history ];then touch $HOME/.bash_history;fi   # ensure bash history file always there
PROMPT_COMMAND="history -a;$PROMPT_COMMAND" # use with 'shopt -s histappend';save terminal commands in history file in real time


###### Shows the return value of the last executed command (using smileys as to whether it was successful or not)
# PROMPT_COMMAND='RET=$?; if [[ $RET -eq 0 ]]; then echo -ne "\033[0;32m$RET\033[0m ;)"; else echo -ne "\033[0;31m$RET\033[0m ;("; fi; echo -n " "'





######################################################################################################################################################
###### BASH SETTINGS ###### BASH SETTINGS ###### BASH SETTINGS ###### BASH SETTINGS ###### BASH SETTINGS ###### BASH SETTINGS ###### BASH SETTINGS ######
######################################################################################################################################################


export BLOCKSIZE=K              # set blocksize size
export BROWSER='firefox'            # set default browser
# export BROWSER='opera'            # set default browser
# export BROWSER=$(find_alternatives chromium-browser google-chrome opera firefox firefox-bin iceweasel konqueror w3m lynx) # uses function 'find_alternatives'
export CDDIR="$HOME"                # for use with the function 'cd' and the alias 'cdd'
export EDITOR='vi'              # use default text editor
export HISTCONTROL=ignoreboth:erasedups     # for 'ignoreboth': ignore duplicates and /^\s/
export HISTIGNORE='&:bg:fg:ll:h'
export HISTSIZE=10000               # increase or decrease the size of the history to '10,000'
export HISTTIMEFORMAT='%H:%M > '
export HISTTIMEFORMAT='%Y-%m-%d_%H:%M:%S_%a  '  # makes history display in YYYY-MM-DD_HH:MM:SS_3CharWeekdaySpaceSpace format
export HOSTFILE=$HOME/.hosts            # put list of remote hosts in ~/.hosts ...
export LESSCHARSET='latin1'
export LESS='-i -N -w  -z-4 -g -e -M -X -F -R -P%t?f%f \'
export LESSOPEN='|/usr/bin/lesspipe.sh %s 2>&-' # use this if lesspipe.sh exists
export PAGER='less -e'
export TERM='xterm'
export TIMEFORMAT=$'\nreal %3R\tuser %3U\tsys %3S\tpcpu %P\n'
export TMOUT=600                # auto logout after n seconds of inactivity
export VIDEO_FORMAT=NTSC            # for use with creating compatible DVDs ('dvdauthor -x dvdauthor.xml' will fail if this not here)
export VISUAL='vi'
set -b                      # causes output from background processes to be output right away, not on wait for next primary prompt
set -o notify                   # notify when jobs running in background terminate
shopt -s cdable_vars                # set the bash option so that no '$' is required (disallow write access to terminal)
shopt -s cdspell                # this will correct minor spelling errors in a cd command
shopt -s checkhash
shopt -s checkwinsize               # update windows size on command
shopt -s cmdhist                    # save multi-line commands in history as single line
shopt -s extglob                # necessary for bash completion (programmable completion)
shopt -s histappend histreedit histverify
shopt -s mailwarn               # keep an eye on the mail file (access time)
shopt -s nocaseglob                 # pathname expansion will be treated as case-insensitive (auto-corrects the case)
shopt -s no_empty_cmd_completion        # no empty completion (bash>=2.04 only)
shopt -s sourcepath
stty start undef
stty stop undef
ulimit -S -c 0                      # (core file size) don't want any coredumps
unset MAILCHECK                     # don't want my shell to warn me of incoming mail



# autocomplete ssh commands
complete -W "$(echo `cat ~/.bash_history | egrep '^ssh ' | sort | uniq | sed 's/^ssh //'`;)" ssh


##################################################
# Automatically clean up all temporary files in  #
# $HOME directory                #
##################################################

# find "$HOME" -type f \( -name "*~" -or -name ".*~" -or -name "*.old" -or -name "*.bak" -or -name "*.OLD" -or -name "*.BAK" \)|xargs -I{} bash -c "rm -rf \"{}\""



##################################################
# Bashrc greetings               #
##################################################

###### greeting
# # from Jonathan's .bashrc file (by ~71KR117)
# # get current hour (24 clock format i.e. 0-23)
# hour=$(date +"%H")
# # if it is midnight to midafternoon will say G'morning
# if [ $hour -ge 0 -a $hour -lt 12 ]
# then
#   greet="Good Morning, $USER. Welcome back."
# # if it is midafternoon to evening ( before 6 pm) will say G'noon
# elif [ $hour -ge 12 -a $hour -lt 18 ]
# then
#   greet="Good Afternoon, $USER. Welcome back."
# else # it is good evening till midnight
#   greet="Good Evening, $USER. Welcome back."
# fi
# # display greeting
# echo $greet



###### holiday greeting
# # from Jonathan's .bashrc file (by ~71KR117)
# # get current day (Month-Day Format)
# day=$(date +"%B%e")
# # get current year (for new years greeting)
# year=$(date +"%Y")
# # make sure the holiday greeting is displayed (if any)
# hol=1
# # if it is New Year's Day
# if [ "$day" = "January1" ]
# then
#   holgreet="Happy New Years. Have a Happy $year."
# # if it is Groundhog Day
# elif [ "$day" = "February2" ]
# then
#   holgreet="Have a Happy Groundhog Day."
# # if it is Valentine's Day
# elif [ "$day" = "February14" ]
# then
#   holgreet="Have a Happy Valentine's Day."
# # if it is Independance Day
# elif [ "$day" = "July4" ]
# then
#   holgreet="Have a Happy Forth of July."
# # if it is my birthday
# elif [ "$day" = "July19" ]
# then
#   holgreet="Have a Happy Birthday."
# # if it is Halloween
# elif [ "$day" = "October31" ]
# then
#   holgreet="Happy Halloween."
# # if it is Christmas Eve
# elif [ "$day" = "December24" ]
# then
#   holgreet="Merry Christmas Eve."
# # if it is Christmas
# elif [ "$day" = "December25" ]
# then
#   holgreet="Merry Christmas."
# # if it is New Year's Eve
# elif [ "$day" = "December31" ]
# then
#   holgreet="Happy New Year's Eve."
# else
#   hol=0
# fi
# # display holiday greeting
# if [ "$hol" = "1" ]
# then
# echo $holgreet
# elif [ "$hol" = "0" ]
# then
#   randomvarthatsomehowimportant=0
# fi



######################################################################################################################################################
###### COMPLETIONS ###### COMPLETIONS ###### COMPLETIONS ###### COMPLETIONS ###### COMPLETIONS ###### COMPLETIONS ###### COMPLETIONS ###### COMPLETIONS
######################################################################################################################################################

##################################################
# 'Universal' completion function        #
##################################################

######  it works when commands have a so-called 'long options' mode
# ie: 'ls --all' instead of 'ls -a'
# Needs the '-o' option of grep
# (try the commented-out version if not available).
# First, remove '=' from completion word separators
# (this will allow completions like 'ls --color=auto' to work correctly).
COMP_WORDBREAKS=${COMP_WORDBREAKS/=/}




######################################################################################################################################################
###### FUNCTIONS ###### FUNCTIONS ###### FUNCTIONS ###### FUNCTIONS ###### FUNCTIONS ###### FUNCTIONS ###### FUNCTIONS ###### FUNCTIONS ###### FUNCTIONS
######################################################################################################################################################


###### netinfo - shows network information for your system
function netinfo()
{
echo "--------------- Network Information ---------------"
/sbin/ifconfig | awk /'inet addr/ {print $2}'
/sbin/ifconfig | awk /'Bcast/ {print $3}'
/sbin/ifconfig | awk /'inet addr/ {print $4}'
/sbin/ifconfig | awk /'HWaddr/ {print $4,$5}'
myip=`lynx -dump -hiddenlinks=ignore -nolist http://checkip.dyndns.org:8245/ | sed '/^$/d; s/^[ ]*//g; s/[ ]*$//g' `
echo "${myip}"
echo "---------------------------------------------------"
}






##################################################
# Miscellaneous Fun              #
##################################################

###### stupid funny face
function funny_face() {
  _ret=$?; if test $_ret -ne 0; then echo "0_0->ret=$_ret"; set ?=$_ret; unset _ret; else echo "^_^"; fi
}


###### pretend to be busy in office to enjoy a cup of coffee
function grepcolor()
{
cat /dev/urandom | hexdump -C | grep --color=auto "ca fe"
}



###### a simple number guessing game
function hilow()
{
biggest=1000                            # maximum number possible
guess=0                                 # guessed by player
guesses=0                               # number of guesses made
number=$(( $$ % $biggest ))             # random number, 1 .. $biggest
while [ $guess -ne $number ] ; do
  echo -n "Guess? " ; read guess
  if [ "$guess" -lt $number ] ; then
    echo "... bigger!"
  elif [ "$guess" -gt $number ] ; then
    echo "... smaller!"
  fi
  guesses=$(( $guesses + 1 ))
done
echo "Right!! Guessed $number in $guesses guesses."
}



function oneliners()
{
w3m -dump_source http://www.onelinerz.net/random-one-liners/1/ | awk ' /.*<div id=\"oneliner_[0-9].*/ {while (! /\/div/ ) { gsub("\n", ""); getline; }; gsub (/<[^>][^>]*>/, "", $0); print $0}'
}






function hgg()
{
    if [ $# -lt 1 ] || [ $# -gt 1 ]; then
        echo "search bash history"
        echo "usage: mg [search pattern]"
    else
        history | grep -i $1 | grep -v hg
    fi
}




function psg()
{
    if [ $# -lt 1 ] || [ $# -gt 1 ]; then
        echo "grep running processes"
        echo "usage: psg [process]"
    else
        ps aux | grep USER | grep -v grep
        ps aux | grep -i $1 | grep -v grep
    fi
}





##################################################
# Numerical conversions and numbers stuff    #
##################################################


###### Averaging columns of numbers
# Computes a columns average in a file. Input parameters = column number and optional pattern.
function avg() { awk "/$2/{sum += \$$1; lc += 1;} END {printf \"Average over %d lines: %f\n\", lc, sum/lc}"; }





###### Output an ASCII character given its decimal equivalent
function chr() { printf \\$(($1/64*100+$1%64/8*10+$1%8)); }





###### length
function length()
{
    if [ $# -lt 1 ]; then
        echo "count # of chars in arugment"
        echo "usage: length [string]"
    else
        echo -n $@ | wc -c
    fi
}






###### convert normal to unix
function normal2unix()
{
    echo "${@}" | awk '{print mktime($0)}';
}



###### convert unix to normal
function unix2normal()
{
    echo $1 | awk '{print strftime("%Y-%m-%d %H:%M:%S",$1)}';
}



###### Pascal's triangle
function pascal() { l=15;for((i=0;i<$l;i++));do eval "a$i=($(pv=1;v=1;for((j=0;j<$l-$i;j++));do [ $i -eq 0 -o $j -eq 0 ]&&{ v=1 && pv=1; }||v=$((pv+a$((i-1))[$((j))]));echo -n "$v ";pv=$v;done;));";o="$(eval echo "$(for((k=0;k<=$i;k++)); do eval "echo -n \"\$((a\$((i-k))[k])) \""; done)")";echo "$o";s="${#o}"; done; } | while read l; do j=$((s-${#l}/2)); echo "$(while ((i++ < j)); do echo -n " ";done;)$l";done





###### convert to roman numerals
function roman-numeral()
{
python -c 'while True: print (lambda y,x=[],nums={ 1000:"M",900:"CM",500:"D",400:"CD",100:"C",90:"XC",
50:"L",40:"XL",10:"X",9:"IX",5:"V",4:"IV",1:"I"}: (lambda ro=(lambda : map(lambda g,r=lambda b:x.append(
y[-1]/b),t=lambda v:y.append(y[-1]%v):map(eval,["r(g)","t(g)"]),sorted(nums.keys())[::-1]))():"".join(
map(lambda fg: map(lambda ht: nums[ht],sorted(nums.keys())[::-1])[fg] * x[fg],range(len(x)))))())([int(
raw_input("Please enter a number between 1 and 4000: "))])'
}



###### ruler that stretches across the terminal
function ruler() { for s in '....^....|' '1234567890'; do w=${#s}; str=$( for (( i=1; $i<=$(( ($COLUMNS + $w) / $w )) ; i=$i+1 )); do echo -n $s; done ); str=$(echo $str | cut -c -$COLUMNS) ; echo $str; done; }



###### convert seconds to minutes, hours, days, and etc.
# inputs a number of seconds, outputs a string like "2 minutes, 1 second"
# $1: number of seconds
function sec2all()
{
    local millennia=$((0))
    local centuries=$((0))
    local years=$((0))
    local days=$((0))
    local hour=$((0))
    local mins=$((0))
    local secs=$1
    local text=""
    # convert seconds to days, hours, etc
    millennia=$((secs / 31536000000))
    secs=$((secs % 31536000000))
    centuries=$((secs / 3153600000))
    secs=$((secs % 3153600000))
    years=$((secs / 31536000))
    secs=$((secs % 31536000))
    days=$((secs / 86400))
    secs=$((secs % 86400))
    hour=$((secs / 3600))
    secs=$((secs % 3600))
    mins=$((secs / 60))
    secs=$((secs % 60))
    # build full string from unit strings
    text="$text$(seconds-convert-part $millennia "millennia")"
    text="$text$(seconds-convert-part $centuries "century")"
    text="$text$(seconds-convert-part $years "year")"
    text="$text$(seconds-convert-part $days "day")"
    text="$text$(seconds-convert-part $hour "hour")"
    text="$text$(seconds-convert-part $mins "minute")"
    text="$text$(seconds-convert-part $secs "second")"
    # trim leading and trailing whitespace
    text=${text## }
    text=${text%% }
    # special case for zero seconds
    if [ "$text" == "" ]; then
        text="0 seconds"
    fi
    # echo output for the caller
    echo ${text}
}
# formats a time unit into a string
# $1: integer count of units: 0, 6, etc
# $2: unit name: "hour", "minute", etc
function seconds-convert-part()
{
    local unit=$1
    local name=$2
    if [ $unit -ge 2 ]; then
        echo " ${unit} ${name}s"
    elif [ $unit -ge 1 ]; then
        echo " ${unit} ${name}"
    else
        echo ""
    fi
}




##################################################
# Get the headlines of an atom feed      #
##################################################

function atomtitles()
{
curl --silent $1 | xmlstarlet sel -N atom="http://www.w3.org/2005/Atom" -t -m /atom:feed/atom:entry -v atom:title -n
}




##################################################
# Backup .bash* files                #
##################################################

function backup_bashfiles()
{
  ARCHIVE="$HOME/bash_dotfiles_$(date +%Y%m%d_%H%M%S).tar.gz";
  cd ~
  tar -czvf $ARCHIVE .bash_profile .bashrc .bash_functions .bash_aliases .bash_prompt
  echo "All backed up in $ARCHIVE";
}



##################################################
# Creates a backup of the file passed as     #
# parameter with the date and time       #
##################################################

function bak()
{
  cp $1 $1_`date +%H:%M:%S_%d-%m-%Y`
}




##################################################
# Execute a given Linux command on a group of    #
# files                      #
##################################################

###### Example: batchexec sh ls     # lists all files that have the extension 'sh'
# Example: batchexec sh chmod 755   # 'chmod 755' all files that have the extension 'sh'
function batchexec()
{
find . -type f -iname '*.'${1}'' -exec ${@:2}  {} \; ;
}



##################################################
# Clock - A bash clock that can run in your  #
# terminal window.               #
##################################################


###### binary clock
function bclock2()
{
perl -e 'for(;;){@d=split("",`date +%H%M%S`);print"\r";for(0..5){printf"%.4b ",$d[$_]}sleep 1}'
}



function clock()
{
while true;do clear;echo "===========";date +"%r";echo "===========";sleep 1;done
}




##################################################
# Create box of '#' characters around given      #
# string                     #
##################################################

function box() { t="$1xxxx";c=${2:-#}; echo ${t//?/$c}; echo "$c $1 $c"; echo ${t//?/$c}; }





##################################################
# Randomness                     #
##################################################




###### Random wallpaper (add whatever wallpaper directory(s) you wish after 'BACKGROUND_DIRS')
# function randomwp()
# # for GNOME2
# {
# cat > "/tmp/randomwp.py" <<"End-of-message"
# #!/usr/bin/env python
# BACKGROUND_DIRS = ['/usr/share/backgrounds', '~/Pictures/Backgrounds']
# EXTENSIONS = ['jpeg', 'jpg', 'bmp', 'png', 'svg']
# import os, glob, random, itertools, gconf
# files = list(itertools.chain(*[[os.path.join(dirpath, name)
#                                 for name in filenames]
#                                for dirpath, dirnames, filenames in
#                                itertools.chain(*[os.walk(os.path.expanduser(d))
#                                                  for d in BACKGROUND_DIRS])]))
# gconf.client_get_default().set_string(
#     '/desktop/gnome/background/picture_filename',
#     random.choice(files))
# End-of-message
# chmod +x "/tmp/randomwp.py"
# "/tmp/randomwp.py"
# /bin/rm "/tmp/randomwp.py"
# }



function randomwp()
# for GNOME3
{
##################################################
# Random-Gnome3-Wallpaper.sh             #
# Creator:              Inameiname       #
# Major Contributor:    hwttdz           #
#           (did most of work :P)    #
# Version:              1.1          #
# Last modified:        18 October 2011      #
# License:              GPLv3+           #
# Descripton:                    #
# Script to randomly set desktop/gdm background  #
# from files in a directory(s) in GNOME3     #
# Requires: sudo-apt get install randomize-lines #
##################################################
###### just add/remove as many directories as wish
find "/usr/share/backgrounds" "$HOME/Pictures/Backgrounds" -type f \( -name "*.bmp" -or -name "*.BMP" -or -name "*.jpeg" -or -name "*.JPEG" -or -name "*.jpg" -or -name "*.JPG" -or -name "*.png" -or -name "*.PNG" -or -name "*.svg" -or -name "*.SVG" \)|rl|head -n 1|xargs -I{} bash -c "gsettings set org.gnome.desktop.background picture-uri \"file://{}\""
}



function randomwp_()
{
##################################################
# Random-Gnome3-Wallpaper-2.sh           #
# Creator:              Inameiname       #
# Version:              1.0          #
# Last modified:        18 October 2011      #
# License:              GPLv3+           #
# Descripton:                    #
# Script to randomly set desktop/gdm background  #
# from files in a directory(s) in GNOME3     #
##################################################
###### Directories Containing Pictures (to add more folders here, just "/path/to/your/folder")
arr[0]="/usr/share/backgrounds"
arr[1]="$HOME/Pictures/Backgrounds"
# arr[2]=
# arr[3]=
# arr[4]=
# arr[5]=
# arr[6]=
# arr[7]=
# arr[8]=
# arr[9]=
# arr[10]=
###### How many picture folders are there? (currently = 2)
rand=$[ $RANDOM % 2 ]
###### Command to select a random folder
DIR=`echo ${arr[$rand]}`
###### Command to select a random file from directory
# The *.* should select only files (ideally, pictures, if that's all that's inside)
PIC=$(ls $DIR/*.* | shuf -n1)
###### Command to set background Image
gsettings set org.gnome.desktop.background picture-uri "file://$PIC"
}



function randomwpt()
# automatic wallpaper switcher for GNOME2
# Usage: randomwpt "bash directory_name" "timeout_in_seconds"
# for GNOME2 only
{
if [ $# -ne 2 ];then
    echo -n "Usage: $0 directory_name timeout_in_seconds
    Leave the directory name blank for Current Directory
    For you lazy pal, I assume timeout as 5 sec and Directory as current
    Do you want to accept this settings? (Y/n): ";
    read response
    if [[ "$response" =~ ^[^yY] ]];then
        exit 0
    fi
fi
function set_wallpaper() {
    gconftool-2 -s /desktop/gnome/background/picture_options "centered" -t string;
    gconftool-2 -s /desktop/gnome/background/picture_filename "$1" -t string;
}
TIMEOUT=${2-5};
WALL_DIR=${1-`pwd`};
echo "Timeout value is: $TIMEOUT";
echo "Directory is: $WALL_DIR";
echo
if [ ! -d "$WALL_DIR" ];then
    echo "The Directory Specified is invalid..";
    exit 1;
fi
filelst="$(find "$WALL_DIR" -type f -name '*.jpg' -o -name '*.png')";
if [ -z "$filelst" ];then
    echo "No Suitable files found in this location: $WALL_DIR";
    exit 1;
fi
while true;do
    filename=`echo "$filelst" | shuf -n 1`
    set_wallpaper "$filename";
    sleep $TIMEOUT;
done
}



##################################################
# Backup a file with a date-time stamp       #
##################################################

# Usage "bu filename.txt"
function bu() { cp $1 ${1}-`date +%Y%m%d%H%M`.backup ; }



function buf() { cp -v $1 ${1/${1%%.*}/$f-$(date +"%Y%m%d_%H%M%S")}; }




##################################################
# Print working directory after a cd.        #
##################################################

# function cd() {
#     if [[ $@ == '-' ]]; then
#         builtin cd "$@" > /dev/null  # We'll handle pwd.
#     else
#         builtin cd "$@"
#     fi
#     echo -e "   \033[1;30m"`pwd`"\033[0m"
# }



##################################################
# Change directory and list files        #
##################################################

function cds() {
    # only change directory if a directory is specified
    [ -n "${1}" ] && cd $1
    lls
}



##################################################
# Grep, grep, grep               #
##################################################

###### randomize GNU grep's colors 31-36 excluding black and white.
function cgrep() { GREP_COLOR="1;3$((RANDOM%6+1))" grep --color=always "$@" ; }



###### to grep through files found by find, e.g. grepf pattern '*.c'
# note that 'grep -r pattern dir_name' is an alternative if want all files
function grepfind() { find . -type f -name "$2" -print0 | xargs -0 grep "$1" ; }



###### to grep through the /usr/include directory
function grepincl() { (cd /usr/include; find . -type f -name '*.h' -print0 | xargs -0 grep "$1" ) ; }



###### hgrep, hgrepl (I use these so much I miss them not being on my other machines and should copy them over)
function hgrepl() {
history | sed s/.*\ \ // | grep $@
}



function hgrep() {
history | sed s/.*\ \ // | grep $@ | tail -n 30
}



function hhgrep() {
history | egrep "$@" | egrep -v "hgrep $@"
}



##################################################
# Analyze your bash usage            #
##################################################

function check_()
{
cut -f1 -d" " .bash_history | sort | uniq -c | sort -nr | head -n 30
}



##################################################
# Checksum                   #
##################################################

function checksum()
# copyright 2007 - 2010 Christopher Bratusek
{
    action=$1
    shift
    if [[ ( $action == "-c" || $action == "--check" ) && $1 == *.* ]]; then
        type="${1/*./}"
    else    type=$1
        shift
    fi
    case $type in
        md5 )
            checktool=md5sum
        ;;
        sha1 | sha )
            checktool=sha1sum
        ;;
        sha224 )
            checktool=sha224sum
        ;;
        sha256 )
            checktool=sha256sum
        ;;
        sha384 )
            checktool=sha384sum
        ;;
        sha512 )
            checktool=sha512sum
        ;;
    esac
    case $action in
        -g | --generate )
            for file in "${@}"; do
                $checktool "${file}" > "${file}".$type
            done
        ;;
        -c | --check )
            for file in "${@}"; do
                if [[ "${file}" == *.$type ]]; then
                    $checktool --check "${file}"
                else    $checktool --check "${file}".$type
                fi
            done
        ;;
        -h | --help )
        ;;
    esac
}



###### MD5 checksum
function md5()
{
    echo -n $@ | md5sum
}





###### shows the colors in a kewl way...partially stolen from HH
function colors()
{
       # Display ANSI colours.
    esc="\033["
    echo -e "\t  40\t   41\t   42\t    43\t      44       45\t46\t 47"
    for fore in 30 31 32 33 34 35 36 37; do
        line1="$fore  "
        line2="    "
        for back in 40 41 42 43 44 45 46 47; do
            line1="${line1}${esc}${back};${fore}m Normal  ${esc}0m"
            line2="${line2}${esc}${back};${fore};1m Bold    ${esc}0m"
        done
        echo -e "$line1\n$line2"
    done
}



###### displays all 256 possible background colors, using ANSI escape sequences.
# author: Chetankumar Phulpagare
# used in ABS Guide with permission.
function colors2()
{
T1=8
T2=6
T3=36
offset=0
for num1 in {0..7}
do {
   for num2 in {0,1}
       do {
          shownum=`echo "$offset + $T1 * ${num2} + $num1" | bc`
          echo -en "\E[0;48;5;${shownum}m color ${shownum} \E[0m"
          }
       done
   echo
   }
done
offset=16
for num1 in {0..5}
do {
   for num2 in {0..5}
       do {
          for num3 in {0..5}
              do {
                 shownum=`echo "$offset + $T2 * ${num3} \
                 + $num2 + $T3 * ${num1}" | bc`
                 echo -en "\E[0;48;5;${shownum}m color ${shownum} \E[0m"
                 }
               done
          echo
          }
       done
}
done
offset=232
for num1 in {0..23}
do {
   shownum=`expr $offset + $num1`
   echo -en "\E[0;48;5;${shownum}m ${shownum}\E[0m"
}
done
echo
}



###### print all 256 colors for testing TERM or for a quick reference
# show numerical values for each of the 256 colors in bash
function colors2nums()
{
for code in {0..255}; do echo -e "\e[38;05;${code}m $code: Test"; done
}



###### replaces a color in PDF document (useful for removing dark background for printing)
# usage:    remove_color input.pdf output.pdf
function uncolorpdf()
{
convert -density 300 "$1" -fill "rgb(255,255,255)" -opaque "rgb(0,0,0)" "$2"
}





##################################################
# Run command/program using a timer      #
##################################################

###### Run a command until a specified time
# Example: command-timer 04:00
function command-timer() { echo "notify-send TimeToQuit" | at "$@" ; }



###### Run a program on a timer
# Example: program-timer 20 viewnior arg1
function program-timer() { perl -e 'alarm shift; exec @ARGV' "$@" & exit; }



##################################################
# Computer the speed of two commands         #
##################################################

function comp() { # compare the speed of two commands (loop $1 times)
  if [[ $# -ne 3 ]] ; then return 1 ; fi
  echo -n 1
  time for ((i=0;i<$1;i++)) ; do $2 ; done >/dev/null 2>&1
  echo -n 2
  time for ((i=0;i<$1;i++)) ; do $3 ; done >/dev/null 2>&1
}



##################################################
# Remove text from file1 which is in file2 and   #
# store it in an other file          #
##################################################

###### handy if you have file where file1 was the original
# and you want to remove the original data from your file2
# usage: grep -Fvf nameofinputfile1 nameofinputfile2 > nameofoutputfile
function comparenclean() { grep -Fvf $1 $2 > $3 ; }



###### save lines unique to file2
# if both file1 and file2 are already sorted: comm -13 nameofinputfile1 nameofinputfile2 > nameofoutputfile
function comparenclean_() { comm -13 <(sort $1) <(sort $2) > $3 ; }



##################################################
# Compress stuff                 #
##################################################

function compress_() {
   # Credit goes to: Daenyth
   FILE=$1
   shift
   case $FILE in
      *.tar.bz2) tar cjf $FILE $*  ;;
      *.tar.gz)  tar czf $FILE $*  ;;
      *.tgz)     tar czf $FILE $*  ;;
      *.zip)     zip $FILE $*      ;;
      *.rar)     rar $FILE $*      ;;
      *)         echo "Filetype not recognized" ;;
   esac
}




##################################################
# Convert to avi                 #
##################################################

function conv2avi() {
    # copyright 2007 - 2010 Christopher Bratusek
    if [[ $(which mencoder-mt) != "" ]]; then
    mencoder-mt "$1" -lavdopts threads=8 \
      -ovc xvid -xvidencopts fixed_quant=4 -of avi \
      -oac mp3lame -lameopts vbr=3 \
      -o "$1".avi
    else
    mencoder "$1" -lavdopts \
      -ovc xvid -xvidencopts fixed_quant=4 -of avi \
      -oac mp3lame -lameopts vbr=3 \
      -o "$1".avi
    fi
}




##################################################
# Cp with progress bar (using pv)        #
##################################################

function cp_p() {
    if [ `echo "$2" | grep ".*\/$"` ]
    then
        pv "$1" > "$2""$1"
    else
        pv "$1" > "$2"/"$1"
    fi
}




##################################################
# Print a cron formatted time for 2 minutes in   #
# the future (for crontab testing)       #
##################################################

function crontest() { date '-d +2 minutes' +'%M %k %d %m *'; }



##################################################
# Encryption / decryption            #
##################################################

###### do twice to decrypt
# copyright 2007 - 2010 Christopher Bratusek
function crypt() {
    if [[ -e "$1" ]]; then
        tr a-zA-Z n-za-mN-ZA-M < "$1" > "$1".crypt
        rm -f "$1"
        mv "$1".crypt "$1"
    fi
}



###### basic encrypt / decrypt
# example: "encry filename" or "decry filename"
function encry()
{
gpg -ac --no-options "$1"
}



function decry()
{
gpg --no-options "$1"
}



###### More advanced encryption / decryption
# example: "encrypt filename" or "decrypt filename"
function encrypt()
{
# Author: Martin Langasek <cz4160@gmail.com>
case $LANG in
  cs* )
    err_title="Chyba"
    err_files="Neoznačen soubor"
    encrypt="Šifrovat"
    decrypt="Dešifrovat"
    file_msg="soubor:"
    pass_msg="Vložte heslo";;
  * )
    err_title="Error"
    err_files="No file selected"
    encrypt="Encrypt"
    decrypt="Decrypt"
    file_msg="file:"
    pass_msg="Enter passphrase";;
esac
if [ "$1" != "" ]
then
  i=1
  file=`echo "$1" | sed ''$i'!d'`
  while [ "$file" != "" ]
  do
    ext=`echo "$file" | grep [.]gpg$ 2>&1`
    if [ "$ext" != "" ]
    then
      pass_decrypt=`zenity --entry --entry-text "$pass_decrypt" --hide-text --title "$pass_msg" --text "$decrypt $file_msg ${file##*/}" "" 2>&1`
      if [ "$pass_decrypt" != "" ]
      then
        output=${file%.*}
        echo "$pass_decrypt" | gpg -o "$output" --batch --passphrase-fd 0 -d "$file"
      fi
    else
      pass_encrypt=`zenity --entry --hide-text --entry-text "$pass_encrypt" --title "$pass_msg" --text "$encrypt $file_msg ${file##*/}" "" 2>&1`
      if [ "$pass_encrypt" != "" ]
      then
        echo "$pass_encrypt" | gpg --batch --passphrase-fd 0 --cipher-algo aes256 -c "$file"
      fi
    fi
    i=$(($i+1))
    file=`echo "$1" | sed ''$i'!d'`
  done
else
  zenity --error --title "$err_title" --text "$err_files"
fi
}



alias decrypt='encrypt'



###### rot13 ("rotate alphabet 13 places" Caesar-cypher encryption)
function rot13()
{
    if [ $# -lt 1 ] || [ $# -gt 1 ]; then
        echo "Seriously?  You don't know what rot13 does?"
    else
        echo $@ | tr A-Za-z N-ZA-Mn-za-m
    fi
}



###### rot47 ("rotate ASCII characters from '!" to '~' 47 places" Caesar-cypher encryption)
function rot47()
{
    if [ $# -lt 1 ] || [ $# -gt 1 ]; then
        echo "Seriously?  You don't know what rot47 does?"
    else
        echo $@ | tr '!-~' 'P-~!-O'
    fi
}



##################################################
# Google stuff                   #
##################################################

###### define a word - USAGE: define dog
function define() {
  local LNG=$(echo $LANG | cut -d '_' -f 1)
  local CHARSET=$(echo $LANG | cut -d '.' -f 2)
  lynx -accept_all_cookies -dump -hiddenlinks=ignore -nonumbers -assume_charset="$CHARSET" -display_charset="$CHARSET" "http://www.google.com/search?hl=${LNG}&q=define%3A+${1}&btnG=Google+Search" | grep -m 5 -C 2 -A 5 -w "*" > /tmp/define
  if [ ! -s /tmp/define ]; then
    echo "Sorry, google doesn't know this one..."
    rm -f /tmp/define
    return 1
  else
    cat /tmp/define | grep -v Search
    echo ""
  fi
  rm -f /tmp/define
  return 0
}




###### find a location's coordinates
# usage:    findlocation "Las Vegas, Nevada" = coordinates: [ -115.1728160, 36.1146460, 0 ]
function findlocation() { place=`echo $1 | sed 's/ /%20/g'` ; curl -s "http://maps.google.com/maps/geo?output=json&oe=utf-8&q=$place" | grep -e "address" -e "coordinates" | sed -e 's/^ *//' -e 's/"//g' -e 's/address/Full Address/';}



###### your GeoIP location on Google Maps
function geoipme()
{
curl -s http://geoiplookup.wikimedia.org/|awk -F, '{print $3,$4}'|awk -F'"' '{print "http://maps.google.com/maps?q="$4 "," $8}'
}



###### Google search (example: google dog)
function google() {
firefox "http://www.google.com/search?&num=100&q=${@}" &
}



###### Google chart
function google_chart()
{
wget -O chart.png 'http://chart.googleapis.com/chart?chs=250x100&chd=t:60,40&cht=p3&chl=Hello|World'
}



###### Google search (example: google dog)
function google-fonts() {
# Google-Fonts.sh
# Version:      0.1
# Last modified:    04 November 2011
# License:      GPLv3+
# Creator:      Inameiname
#
# Credit also goes to Michalis Georgiou
# <mechmg93@gmail.com> for his original
# google-font script and to Andrew
# http://www.webupd8.org <andrew@webupd8.org> for
# his further modification of it.
#
# Descripton:
# For those who want an extremely easy method to
# download and install the entire Google font
# repository.
###### Installation of Mercurial Needed for Downloading of Fonts ######
sudo apt-get install mercurial
###### Setting of Default Directories ######
_hgroot="https://googlefontdirectory.googlecode.com/hg/"
_hgrepo="googlefontdirectory"
_hgoutdir="google-fonts"
###### Google Font Choice Decision ######
echo "
"
echo -n "What do you want to do with the fonts from Google
once they are downloaded?:

(1)  Download Only (and keep all fonts in a single folder)
(2)  Download Only (and keep all fonts in separate folders (pure hg copy))
(3)  Download and Install

Press 'Enter' for default (default is '1')...

"
read GOOGLE_FONT_CHOICE
###### Actual Downloading of the Google Fonts ######
if [ ! -d $HOME/$_hgrepo ] ; then
echo "
"
echo "Connecting to Mercurial server...."
if [ -d $HOME/$_hgrepo ] ; then
    cd $HOME/$_hgrepo
    hg pull -u || return 1
    echo "The local files have been updated."
    cd ..
else
    hg clone $_hgroot $HOME/$_hgrepo || return 1
fi
echo "Mercurial checkout done or server timeout"
echo "
"
else
echo "The directory $HOME/$_hgrepo already exists."
echo ""
echo "No need to redownload all of the Google fonts."
fi
###### Google Font Choice Selection ######
###### default
if [[ -z $GOOGLE_FONT_CHOICE ]] ; then
    # If no file passed, default to 1
    mkdir -p $HOME/$_hgoutdir/
    find $HOME/$_hgrepo/ -name "*.ttf"|xargs -I{} bash -c "cp -rf \"{}\" $HOME/$_hgoutdir/"
    rm -rf $HOME/$_hgrepo/
fi
###### preset
if [[ $GOOGLE_FONT_CHOICE = 1 ]] ; then
    mkdir -p $HOME/$_hgoutdir/
    find $HOME/$_hgrepo/ -name "*.ttf"|xargs -I{} bash -c "cp -rf \"{}\" $HOME/$_hgoutdir/"
    rm -rf $HOME/$_hgrepo/
fi
if [[ $GOOGLE_FONT_CHOICE = 2 ]] ; then
    mv $HOME/$_hgrepo/ $HOME/$_hgoutdir/
fi
if [[ $GOOGLE_FONT_CHOICE = 3 ]] ; then
    sudo mkdir -p /usr/share/fonts/truetype/google-fonts/
    find $HOME/$_hgrepo/ -name "*.ttf" -exec sudo install -m644 {} /usr/share/fonts/truetype/google-fonts/ \; || return 1
    fc-cache -f > /dev/null
    rm -rf $HOME/$_hgrepo/
fi
###### Wrap Up ######
echo "
"
echo "done."
echo "
"
read -sn 1 -p "You have finished downloading/installing all the Google Fonts currently available. Press any key to finish...
"
}



###### get Google PageRank
function pagerank()
{
curl pagerank.bz/$1
}



###### Google text-to-speech in mp3/wav format
function say() { mplayer -user-agent Mozilla "http://translate.google.com/translate_tts?tl=en&q=$(echo $* | sed 's#\ #\+#g')" > /dev/null 2>&1 ; }




##################################################
# Super stealth background launch        #
##################################################

function daemon()
{
    (exec "$@" >&/dev/null &)
}




##################################################
# Download a web page and show info on what  #
# took time                  #
##################################################

function debug_http() { /usr/bin/curl $@ -o /dev/null -w "dns: %{time_namelookup} connect: %{time_connect} pretransfer: %{time_pretransfer} starttransfer: %{time_starttransfer} total: %{time_total}\n" ; }



##################################################
# Lookup a word with dict.org            #
##################################################

###### define "whatever"
function dic() { curl dict://dict.org/d:"$@" ; }



###### find matches of $1, with optional strat $2 and optional db $3
function ref()
{
    if [[ -z $3 ]]; then
        curl dict://dict.org/m:${1}:english:${2};
    else
        curl dict://dict.org/m:${1}:${3}:${2};
    fi
}



###### look in Webster
function webster() { curl dict://dict.org/d:${1}:web1913; }



###### look in WordNet
function wordnet() { curl dict://dict.org/d:${1}:wn; }




##################################################
# Dirsize - finds directory sizes and lists  #
# them for the current directory         #
##################################################

function dirsize()
{
du -shx * .[a-zA-Z0-9_]* 2> /dev/null | \
egrep '^ *[0-9.]*[MG]' | sort -n > /tmp/list
egrep '^ *[0-9.]*M' /tmp/list
egrep '^ *[0-9.]*G' /tmp/list
rm /tmp/list
}





##################################################
# Lists unique IPs currently connected to    #
# logged-in system & how many concurrent     #
# connections each IP has            #
##################################################

function doscheck()
{
"netstat -ntu | awk '{print $5}' | cut -d: -f1 | sort | uniq -c | sort -n"
}





##################################################
# Size of directories in MB          #
##################################################

function ds()
{
    echo "size of directories in MB"
    if [ $# -lt 1 ] || [ $# -gt 2 ]; then
        echo "you did not specify a directy, using pwd"
        DIR=$(pwd)
        find $DIR -maxdepth 1 -type d -exec du -sm \{\} \; | sort -nr
    else
        find $1 -maxdepth 1 -type d -exec du -sm \{\} \; | sort -nr
    fi
}





##################################################
# URLs ...                   #
##################################################

###### expand shortened URLs
function expandurl() { curl -sIL $1 2>&1 | awk '/^Location/ {print $2}' | tail -n1; }



###### short URLs with is.gd
function isgd() { /usr/bin/wget -qO - "http://is.gd/create.php?format=simple&url=$1" ;}



###### resolve short URLs
function resolve() { curl -Is $1 | sed -n 's/^Location: //p'; }



##################################################
# Passwording                    #
##################################################



###### password file
function pw()
{
    if [ "$OS" = "Linux" ]; then
        gpg $HOME/priv.asc
        vi -n $HOME/priv
        gpg -ea $HOME/priv
        wipe -f $HOME/priv
    elif [ "$OS" = "Darwin" ]; then
        gpg $HOME/Documents/priv.asc
        vi -n $HOME/Documents/priv
        gpg -ea $HOME/Documents/priv
        srm -f $HOME/Documents/priv
    fi
}



###### generate a random password
#   $1 = number of characters; defaults to 32
#   $2 = include special characters; 1 = yes, 0 = no; defaults to 1
# copyright 2007 - 2010 Christopher Bratusek
function randompw() {
    if [[ $2 == "!" ]]; then
        echo $(cat /dev/urandom | tr -cd '[:graph:]' | head -c ${1:-32})
    else    echo $(cat /dev/urandom | tr -cd '[:alnum:]' | head -c ${1:-32})
    fi
}



###### generate a random left-hand password
alias randompwl='</dev/urandom tr -dc '12345!@#$%qwertQWERTasdfgASDFGzxcvbZXCVB' | head -c8; echo ""'



###### generate a unique and secure password for every website that you login to
function sitepass() { echo -n "$@" |  md5sum | sha1sum | sha224sum | sha256sum | sha384sum | sha512sum | gzip - | strings -n 1 | tr -d "[:space:]"  | tr -s '[:print:]' | tr '!-~' 'P-~!-O' | rev | cut -b 2-11; history -d $(($HISTCMD-1)); }



###### generates a unique and secure password with SALT for every website that you login to
function sitepass2()
{
salt="this_salt";pass=`echo -n "$@"`;for i in {1..500};do pass=`echo -n $pass$salt|sha512sum`;done;echo$pass|gzip -|strings -n 1|tr -d "[:space:]"|tr -s '[:print:]' |tr '!-~' 'P-~!-O'|rev|cut -b 2-15;history -d $(($HISTCMD-1));
}





##################################################
# Find a file(s) ...                 #
##################################################

###### ... with pattern $1 in name and Execute $2 on it
function fe() { find . -type f -iname '*'$1'*' -exec "${2:-file}" {} \;  ; }



###### ... under the current directory
function ff() { /usr/bin/find . -name "$@" ; }



###### ... whose name ends with a given string
function ffe() { /usr/bin/find . -name '*'"$@" ; }


###### ... whose name starts with a given string
function ffs() { /usr/bin/find . -name "$@"'*' ; }



###### ... larger than a certain size (in bytes)
function find_larger() { find . -type f -size +${1}c ; }



###### find a file with a pattern in name in the local directory
function fp()
{
    find . -type f -iname '*'$*'*' -ls ;
}




###### searches through the text of all the files in your current directory
# http://seanp2k.com/?p=13
# Good for debugging a PHP script you didn't write and can't trackdown where MySQL connect string actually is
# function grip() {
# grep -ir "$1″ "$PWD"
# }



###### ... who is the newest file in a directory
function newest() { find ${1:-\.} -type f |xargs ls -lrt ; }





##################################################
# Find out the pid of a specified process    #
##################################################

######  note that the command name can be specified via a regex
#    E.g. findPid '/d$/' finds pids of all processes with names ending in 'd'
#    Without the 'sudo' it will only find processes of the current user
function findPid() { sudo /usr/sbin/lsof -t -c "$@" ; }



##################################################
# Edit files in place to ensure Unix line-   #
# endings                    #
##################################################

function fixlines() { /usr/bin/perl -pi~ -e 's/\r\n?/\n/g' "$@" ; }



##################################################
# Fix eclipse mistakes with tabs         #
##################################################

###### Sources files should never use TABs for indenting because they may looks different in different editors
# For example there popular Eclipse IDE use a the non default tab size 4
function fix-tabs() { expand -t 4 "$1" > "$1.expanded"; mv -f "$1.expanded" "$1"; }



##################################################
# Inserts a flag with the specified content  #
##################################################

###### Usage: flag "comment"
# If no comment, inserts the date.
function flag() {
    if [ "$1" == "" ];
    then
        echo -e  "\e[0;31m[====== " `date +"%A %e %B %Y"`, `date +"%H"`h`date +"%M"` " ======]\e[0m"
    else
        echo -e  "\e[0;31m[====== " $@ " ======]\e[0m"
    fi
}



##################################################
# Inserts a flag and executes the command    #
##################################################

###### Example: flagcommand ls
function flagcommand() {
    if [ "$1" == "" ];
    then
        return
    else
        flag $@
        $@
    fi
}




##################################################
# Weather and stuff              #
##################################################

###### 10-day forcast
# USAGE:    forecast 50315
function forecast() {
_ZIP=$1

if   [ $# = 1 ];then
     printf "$_ZIP\n" | egrep '^[0-9][0-9][0-9][0-9][0-9]$' >>/dev/null
     if   [ $? = 0 ];then
          printf "Your 10 Day Weather Forecast as follows:\n";
          lynx -dump "http://www.weather.com/weather/print/$_ZIP" | sed -n '/%$/s/\[.*\]//p';
          printf "\n"
     elif [ $? = 1 ];then
          printf "Bad ZIP code!\n"
     fi
elif [ $# != 1 ];then
     printf "You need to supply a ZIP code!\n"
fi
}





###### weather by US zip code - Can be called two
# ways  # weather 50315 # weather "Des
# Moines"
function weather_()
{
declare -a WEATHERARRAY
WEATHERARRAY=( `lynx -dump http://google.com/search?q=weather+$1 | grep -A 5 '^ *Weather for' | grep -v 'Add to'`)
echo ${WEATHERARRAY[@]}
}





##################################################
# Twitter, Twitter, Twitter          #
##################################################

###### view someone's twitter stream from terminal
function grabtweets() { curl -s "twitter.com/$1" | sed -ne '/entry-content/{s/<[^>]*>//g;s/^[ \t]*//;p}'; }



##################################################
# Get just the HTTP headers from a web page  #
# (and its redirects)                #
##################################################

function http_headers() { /usr/bin/curl -I -L $@ ; }



##################################################
# Convert number of bytes to human readable      #
# filesize                   #
##################################################

function human_filesize() { awk -v sum="$1" ' BEGIN {hum[1024^3]="Gb"; hum[1024^2]="Mb"; hum[1024]="Kb"; for (x=1024^3; x>=1024; x/=1024) { if (sum>=x) { printf "%.2f %s\n",sum/x,hum[x]; break; } } if (sum<1024) print "1kb"; } ' ; }



##################################################
# Show computer information of all sorts     #
# (requires 'gawk': sudo apt-get install gawk)   #
##################################################

###### machine details
function ii()
{
    echo -e "\n${RED}You are logged onto:$NC " ; hostname
    echo -e "\n${RED}Additionnal information:$NC " ; uname -a
    echo -e "\n${RED}Users logged on:$NC " ; w -h
    echo -e "\n${RED}Current date:$NC " ; date
    echo -e "\n${RED}Machine stat:$NC " ; uptime
    echo -e "\n${RED}Disk space:$NC " ; df -h
    echo -e "\n${RED}Memory stats (in MB):$NC " ;
    if [ "$OS" = "Linux" ]; then
        free -m
    elif [ "$OS" = "Darwin" ]; then
        vm_stat
    fi
    echo -e "\n${RED}IPs:$NC " ; ips
}



###### paste hardware list (hwls) in html format into
# pastehtml.com directly from console and return URI
function listhw() { curl -s -S --data-urlencode "txt=$(sudo lshw -html)" "http://pastehtml.com/upload/create?input_type=html&result=address";echo; }



###### full memcache client in under 255 chars (uses dd, sed and nc)
# usage: mem memcache-command [arguments]
# function mem() { { case $1 in st*|[gid]*) printf "%s " "$@";; *) dd if=$3 2>&1|sed '$!d;/^0/d;s/ .*//;s/^/'"$1"' '"$2"' 1 0 /; r '"$3"'' 2>/dev/null;;esac;printf "\r\nquit\r\n";}|nc -n 127.0.0.1 11211; }



###### notify on Battery power
# works on laptops, desktop having communication b/w UPS & CPU
function NotifyOnBATTERY() { while :; do on_ac_power||notify-send "Running on BATTERY"; sleep 1m; done ; }





function show_uptime() {
    # copyright 2007 - 2010 Christopher Bratusek
    case $1 in
        *help )
            echo -e "\n${ewhite}Usage:\n"
            echo -e "${eorange}show_uptime${ewhite} |${egreen} ! no options !\n"
            tput sgr0
        ;;
        * )
            uptime=$(</proc/uptime)
            timeused=${uptime%%.*}
            if (( timeused > 86400 )); then
            ((
                daysused=timeused/86400,
                hoursused=timeused/3600-daysused*24,
                minutesused=timeused/60-hoursused*60-daysused*60*24,
                secondsused=timeused-minutesused*60-hoursused*3600-daysused*3600*24
            ))
                if (( hoursused < 10 )); then
                    hoursused=0${hoursused}
                fi
                if (( minutesused < 10 )); then
                    minutesused=0${minutesused}
                fi
                if (( secondsused < 10 )); then
                    secondsused=0${secondsused}
                fi
                output="${daysused}d ${hoursused}h:${minutesused}m:${secondsused}s"
            elif (( timeused < 10 )); then
                output="0d 00h:00m:0$(timeused)s"
            elif (( timeused < 60 )); then
                output="0d 00h:00m:${timeused}s"
            elif (( timeused < 3600 )); then
            ((
                minutesused=timeused/60,
                secondsused=timeused-minutesused*60
            ))
                if (( minutesused < 10 )); then
                    minutesused=0${minutesused}
                fi
                if (( secondsused < 10 )); then
                    secondsused=0${secondsused}
                fi
                output="0d 00h:${minutesused}m:${secondsused}s"
            elif (( timeused < 86400 )); then
            ((
                hoursused=timeused/3600,
                minutesused=timeused/60-hoursused*60,
                secondsused=timeused-minutesused*60-hoursused*3600
            ))
                if (( hoursused < 10 )); then
                    hoursused=0${hoursused}
                fi
                if (( minutesused < 10 )); then
                    minutesused=0${minutesused}
                fi
                if (( secondsused < 10 )); then
                    secondsused=0${secondsused}
                fi
                output="0d ${hoursused}h:${minutesused}m:${secondsused}s"
            fi
            echo "$output"
        ;;
    esac
}



###### STAT Function showing ALL info, stat options, and descriptions
function statt() { C=c;stat --h|sed '/Th/,/NO/!d;/%/!d'|while read l;do p=${l/% */};[ $p == %Z ]&&C=fc&&echo ^FS:^;echo "`stat -$C $p \"$1\"` ^$p^${l#%* }";done|column -ts^; }



function system_infos()
# copyright 2007 - 2010 Christopher Bratusek
{
    case $1 in
        *cpu)
            echo -e "${ewhite}CPU:\n"
            echo -e "${eorange}Model:${eiceblue} $(grep "model name" /proc/cpuinfo | sed -e 's/.*: //g')"
            echo -e "${eorange}MHz  :${eiceblue} $(grep "cpu MHz" /proc/cpuinfo | sed -e 's/.*: //g')\n"
        ;;
        *kernel)
            echo -e "${ewhite}Kernel:\n"
            echo -e "${eorange}Release:${eiceblue} $(uname -r)"
            echo -e "${eorange}Version:${eiceblue} $(uname -v)"
            echo -e "${eorange}Machine:${eiceblue} $(uname -m)\n"
        ;;
        *mem | *ram)
            echo -e "${ewhite}RAM:\n"
            echo -e "${eorange}Total:${eiceblue} $(((`showmem --free`) + (`showmem --used`))) MB"
            echo -e "${eorange}Free :${eiceblue} $(showmem --free) MB"
            echo -e "${eorange}Used :${eiceblue} $(showmem --used) MB\n"
        ;;
        *partitions)
            echo -e "${ewhite}Partitions:${eorange}\n"
            echo -e "major minor blocks device-node ${eiceblue}\
            \n$(cat /proc/partitions | sed -e '1,2d')" | column -t
            echo ""
        ;;
        *pci)
            check_opt lspci systeminfos::pci
            if [[ $? != "1" ]]; then
                echo -e "${ewhite}PCI Devices:\n${eiceblue}"
                lspci -vkmm
                echo ""
            fi
        ;;
        *usb)
            check_opt lsusb systeminfos::usb
            if [[ $? != "1" ]]; then
                echo -e "${ewhite}USB Devices:\n${eiceblue}"
                lsusb -v
                echo ""
            fi
        ;;
        *mounts)
            echo -e "${ewhite}Mounts:\n${eorange}\
            \ndevice-node on mount-point type filesystem options\n" ${eiceblue} "\n\n$(mount)" | column -t
            echo ""
        ;;
        *bios)
            check_opt dmidecode systeminfos::bios
            if [[ $? != "1" && $EUID == 0 ]]; then
                echo -e "${ewhite}SMBIOS/DMI Infos:${eiceblue}\n"
                dmidecode -q
            fi
        ;;
        *all)
            system_infos_cpu
            system_infos_kernel
            system_infos_memory
            system_infos_partitions
            # system_infos_pci
            # system_infos_usb
            system_infos_mounts
            # system_infos_bios
        ;;
        *)
            echo -e "\n${ewhite}Usage:\n"
            echo -e "${eorange}system_infos ${ewhite}|${egreen} --cpu\t\t${eiceblue}[Display CPU Model and Freq]\
            \n${eorange}system_infos ${ewhite}|${egreen} --kernel\t${eiceblue}  [Display Kernel Version, Release and Machine]\
            \n${eorange}system_infos ${ewhite}|${egreen} --memory\t${eiceblue}  [Display Total, Free and Used RAM]\
            \n${eorange}system_infos ${ewhite}|${egreen} --partitions\t${eiceblue}[Display Major, Minor, Blocks and Node for all Paritions]\
            \n${eorange}system_infos ${ewhite}|${egreen} --pci\t\t${eiceblue}[Display Infos about all PCI Devices (and their kernel-module)]\
            \n${eorange}system_infos ${ewhite}|${egreen} --usb\t\t${eiceblue}[Display Infos about all USB Devices (and their kernel-module)]\
            \n${eorange}system_infos ${ewhite}|${egreen} --bios\t${eiceblue}    [Display SMBIOS DMI Infos]\
            \n${eorange}system_infos ${ewhite}|${egreen} --mounts\t${eiceblue}  [Display all mounted devices]\n"
            tput sgr0
        ;;
    esac
}



###### shows various info on running activities
# copyright 2007 - 2010 Christopher Bratusek
function treeps() {
    ps f -u $USER -o command,pid,%cpu,%mem,time,etime,tty | \
        awk 'NR <= 1 {print;next} !/awk/ && $0~var' var=${1:-".*"}
}



###### uptime in minutes
function uptime_min()
{
awk  '{print $0/60;}' /proc/uptime
}



###### info about current open windows
# copyright 2007 - 2010 Christopher Bratusek
function wininfo() {
    xprop | grep -w "WM_NAME\|WM_CLASS\|WM_WINDOW_ROLE\|_NET_WM_STATE"
}



##################################################
# Resizing an image              #
##################################################

# USAGE: image_resize "percentage of image resize" "input image" "output image"
function image_resize()
{
convert -sample "$1"%x"$1"% "$2" "$3"
}



##################################################
# Search IMDB.COM                #
##################################################

function imdb()
{
firefox "http://www.imdb.com/find?s=all&q="${@}"&x=0&y=0" &
}






##################################################
# Displays metadata for specified media file     #
##################################################

######   $1 = media file name
function info() {
    EXT=`echo "${1##*.}" | sed 's/\(.*\)/\L\1/'`
    if [ "$EXT" == "mp3" ]; then
        id3v2 -l "$1"
        echo
        mp3gain -s c "$1"
    elif [ "$EXT" == "flac" ]; then
        metaflac --list --block-type=STREAMINFO,VORBIS_COMMENT "$1"
    else
        echo "ERROR: Not a supported file type."
    fi
}




##################################################
# Kill a process by name             #
##################################################

###### example: killps firefox-bin
function killps()
{
    local pid pname sig="-TERM" # default signal
    if [ "$#" -lt 1 ] || [ "$#" -gt 2 ]; then
        echo "Usage: killps [-SIGNAL] pattern"
        return;
    fi
    if [ $# = 2 ]; then sig=$1 ; fi
    for pid in $(myps | nawk '!/nawk/ && $0~pat { print $2 }' pat=${!#}) ; do
        pname=$(myps | nawk '$2~var { print $6 }' var=$pid )
        if ask "Kill process $pid <$pname> with signal $sig ? "
            then kill $sig $pid
        fi
    done
}



###### example: pskill firefox-bin
# copyright 2007 - 2010 Christopher Bratusek
function psgrep() {
    if [[ $1 == "-u" ]]; then
        ps aux | grep -v grep | grep $2 | awk '{ print $2 " : " $11}' | tee .temp
        CMDS=$(cat .temp)
    elif [[ $1 != "" ]]; then
        ps aux | grep -v grep | grep "$1" | awk '{ print $11 " : " $2 " : " $1 }' | tee .temp
        CMDS=$(cat .temp)
    fi
    if [[ $CMDS == "" ]]; then
        echo "no matching process"
    fi
    rm -f .temp
}



function pskill() {
    if [[ $1 ]]; then
        psgrep $1
        shift
        if [[ $CMDS != "" ]]; then
            echo -e "\nenter process number to kill:\n"
            read ID
            if [[ ! $ID == 0 || ! $ID == "" ]]; then
                kill $@ $ID
            fi
        fi
    fi
}





##################################################
# Led set and reset              #
##################################################

function kitt() {
    # copyright 2007 - 2010 Christopher Bratusek
    setleds -L -num;
    setleds -L -caps;
    setleds -L -scroll;
    while :; do
        setleds -L +num;
        sleep 0.2;
        setleds -L -num;
        setleds -L +caps;
        sleep 0.2;
        setleds -L -caps;
        setleds -L +scroll;
        sleep 0.2;
        setleds -L -scroll;
        setleds -L +caps;
        sleep 0.2;
        setleds -L -caps;
    done
    resetleds
}



function resetleds()
# copyright 2007 - 2010 Christopher Bratusek
{
    setleds -L < /dev/tty1
}





##################################################
# Advanced ls functions              #
##################################################

function la() {
    # copyright 2007 - 2010 Christopher Bratusek
    ls -A --group-directories-first "$@"
}



function lg() {
    # copyright 2007 - 2010 Christopher Bratusek
    if [[ "$@" == "" ]]; then
        $@="*"
    fi
    ls -l --group-directories-first "$@" | gawk '{print $9, "belongs to Group ->", $4}' | column -t
}



function ll() {
    # copyright 2007 - 2010 Christopher Bratusek
    ls -l --group-directories-first "$@"
}



###### Counts files, subdirectories and directory size and displays details
# about files depending on the available space
function lls() {
    # count files
    echo -n "<`find . -maxdepth 1 -mindepth 1 -type f | wc -l | tr -d '[:space:]'` files>"
    # count sub-directories
    echo -n " <`find . -maxdepth 1 -mindepth 1 -type d | wc -l | tr -d '[:space:]'` dirs/>"
    # count links
    echo -n " <`find . -maxdepth 1 -mindepth 1 -type l | wc -l | tr -d '[:space:]'` links@>"
    # total disk space used by this directory and all subdirectories
    echo " <~`du -sh . 2> /dev/null | cut -f1`>"
    ROWS=`stty size | cut -d' ' -f1`
    FILES=`find . -maxdepth 1 -mindepth 1 |
    wc -l | tr -d '[:space:]'`
    # if the terminal has enough lines, do a long listing
    if [ `expr "${ROWS}" - 6` -lt "${FILES}" ]; then
        ls
    else
        ls -hlAF --full-time
    fi
}



function lo() {
    # copyright 2007 - 2010 Christopher Bratusek
    if [[ "$@" == "" ]]; then
        $@="*"
    fi
    ls -l --group-directories-first "$@" | gawk '{print $9, "belongs to User ->", $3}' | sed -e '1d' | column -t
}



function l1() {
    # copyright 2007 - 2010 Christopher Bratusek
    ls -1 --group-directories-first "$@"
}




function lm() {
    # copyright 2007 - 2010 Christopher Bratusek
    if [[ ! "$@" == "" ]]; then
        for file in "$@"; do
            stat -c "%A %a %n" "$file" | gawk '{print "Permissions of:", $3, "->", $1, "("$2")"}'
        done | column -t
    fi
}



###### inspired by http://tldp.org/HOWTO/Bash-Prompt-HOWTO/x279.html
# but I made it a single awk instead of an awk, forloop and a bc
# asumes we have awk available.  but really, who doesnt have awk?
# let's get the size of the files in this dir
function lsbytes() {
    echo -n $(ls -l | awk '/^-/{total += $5} END{printf "%.2f", total/1048576}')
}



function lscd() {
    # copyright 2007 - 2010 Christopher Bratusek
    builtin cd "${@}" &>/dev/null
    . $BSNG_RC_DIR/dirinfo/display
    dirinfo_display
    echo -e "${epink}content:"
    ls $LSCD_OPTS
    echo "$PWD" > $HOME/.lastpwd
}



###### display long list of files with the given extension
# example: lsext txt
function lsext()
{
find . -type f -iname '*.'${1}'' -exec ls -l {} \; ;
}



###### another way to call for a list of files/folders
function lsr() { /bin/ls -l "$@"/..namedfork/rsrc ; }



###### sorted, recursive long file listing
function lsr_() { find "${@:-.}" -print0 |sort -z |xargs -0 ls $LS_OPTIONS -dla; }



##################################################
# Show the single most recently modified file in #
# a directory                    #
##################################################

function lastfile() { find ${1:-.} -maxdepth 1 -type f -printf "%T+ %p\n" | sort -n | tail -n1 | sed 's/[^[:space:]]\+ //'; }



##################################################
# Uppercase, lowercase, & cleanup strings & names#
##################################################

###### lowercase all files in the current directory
function lcfiles() {
    print -n 'Really lowercase all files? (y/n) '
    if read -q ; then
        for i in * ; do
            mv $i $i:l
    done
    fi
}



###### Convert the first letter into lowercase letters
function lcfirst() {
      if [ -n "$1" ]; then
          perl -e 'print lcfirst('$1')'
      else
          cat - | perl -ne 'print lcfirst($_)'
      fi
}



###### usage: lower [STRING]...
function lower() { echo ${@,,}; }



###### usage: echo hELLO wORLD | lower
# convert stdin to lower case
function lower_() { tr [A-Z] [a-z]; }



###### move filenames to lowercase
function lowercase()
{
    for file ; do
        filename=${file##*/}
        case "$filename" in
        */*) dirname==${file%/*} ;;
        *) dirname=.;;
        esac
        nf=$(echo $filename | tr A-Z a-z)
        newname="${dirname}/${nf}"
        if [ "$nf" != "$filename" ]; then
            mv "$file" "$newname"
            echo "lowercase: $file --> $newname"
        else
            echo "lowercase: $file not changed."
        fi
    done
}



###### Remove whitespace at the beginning of a string
#  @param string $1 string (optional, can also handle STDIN)
#  @return string
#  @example:    echo " That is a sentinece " | trim
function ltrim() {
      if [ -n "$1" ]; then
              echo $1 | sed 's/^[[:space:]]*//g'
      else
              cat - | sed 's/^[[:space:]]*//g'
      fi
}



###### Space removal and lowercases folders in current dir.
function rmspaces() {
    ls | while read -r FILE
        do
        mv -v "$FILE" `echo $FILE | tr ' ' '_' | tr -d '[{}(),\!]' | tr -d "\'" | tr '[A-Z]' '[a-z]' | sed 's/_-_/_/g'`
        done
}



###### Remove whitespace at the end of a string
#  @param string $1 string (optional, can also handle STDIN)
#  @return string
#  @example:    echo "That is a sentinece " | rtrim
function rtrim() {
      if [ -n "$1" ]; then
              echo $1 | sed 's/[[:space:]]*$//g'
      else
              cat - | sed 's/[[:space:]]*$//g'
      fi
}



###### Cut a string after X chars and append three points
# string strim( string string [, int length ] )
function strim() {
      local string="$1"
      local length=${2:-30}
      [ "${#string}" -gt ${length} ] && string="${string:0:${length}}..."
      echo $string
}



###### Convert all alphabetic characters to lowercase
#  @param string $1|STDIN string
#  @return string
function strtolower() {
      if [ -n "$1" ]; then
        echo $1 | tr '[:upper:]' '[:lower:]'
      else
        cat - | tr '[:upper:]' '[:lower:]'
      fi
}



###### Convert all alphabetic characters converted to uppercase
#  @param string $1|STDIN string
#  @return string
function strtoupper() {
      if [ -n "$1" ]; then
        echo $1 | tr '[:lower:]' '[:upper:]'
      else
        cat - | tr '[:lower:]' '[:upper:]'
      fi
}



###### Remove whitespace at the beginning and end of a string
#  @param string $1 string (optional, can also handle STDIN)
#  @return string
#  @example:    echo " That is a sentinece " | trim
function trim() {
      if [ -n "$1" ]; then
              echo $1 | sed 's/^[[:space:]]*//g' | sed 's/[[:space:]]*$//g'
      else
              cat - | sed 's/^[[:space:]]*//g' | sed 's/[[:space:]]*$//g'
      fi
}



###### Convert the first letter into uppercase letters
function ucfirst() {
      if [ -n "$1" ]; then
          perl -e 'print ucfirst('$1')'
      else
          cat - | perl -ne 'print ucfirst($_)'
      fi
}




###### Converts first letter of each word within a string into an uppercase, all other to lowercase
#     string ucwords( string string )
function ucwords() {
      local string="$*"
      for word in $string; do
          # Get the first character with cut and convert them into uppercase.
          local first="$( echo $word | cut -c1 | tr '[:lower:]' '[:upper:]' )"
          # Convert the rest of the word into lowercase and append them to the first character.
          word="$first$( echo $word | cut -c2-${#word} | tr '[:upper:]' '[:lower:]' )"
          # Put together the sentence.
          local phrase="$phrase $word"
      done
      echo "$phrase"
}



###### usage: upper [STRING]...
function upper() { echo ${@^^}; }



###### usage: echo hELLO wORLD | upper
# convert stdin to upper case
function upper_() { tr [a-z] [A-Z]; }



##################################################
# Corporate ldapsearch for users         #
##################################################

function ldapfind() {
        ldapsearch -x -h ldap.foo.bar.com -b dc=bar,dc=com uid=$1
}



##################################################
# Organize a text file               #
##################################################

###### sort lines in a text file
function linesort()
{
sort -u "$1" > "$1".new
}



###### remove duplicate lines in a file (without resorting)
function removeduplines()
{
awk '!x[$0]++' "$1" > "$1".new
}



##################################################
# Livehttpheaders (firefox addon) replacement    #
##################################################

###### usage: liveh [-i interface] [output-file] && firefox &
function liveh() { tcpdump -lnnAs512 ${1-} tcp |sed ' s/.*GET /GET /;s/.*Host: /Host: /;s/.*POST /POST /;/[GPH][EOo][TSs]/!d;w '"${2-liveh.txt}"' ' >/dev/null ; }




##################################################
# Use a logger                   #
##################################################

function log() {
    echo "$1" 1>&2
    logger -ist "$(basename -- "$0")" "$1"
}



##################################################
# List your MACs address             #
##################################################

function lsmac() { ifconfig -a | awk '/HWaddr/ {print $5}' ; }



##################################################
# MPD music stuff                #
##################################################

###### Add music files in MPD
function madd()
{
    # while [ $# -gt 0 ]; do
        # case "$1" in
            # a)
            # args[i++]=artist;;
            # b)
            # args[i++]=album;;
            # t)
            # args[i++]=title;;
            # *)
            # args[i++]=$1;;
        # esac; shift;
    # done
    # mpc search "${args[@]}" |
    mpc search "$@" |
    mpc add
}



###### Clear, add and play: MPD
function mcap()
{
    mpc clear
    # while [ $# -gt 0 ]; do
        # case "$1" in
            # a)
            # args[i++]=artist;;
            # b)
            # args[i++]=album;;
            # t)
            # args[i++]=title;;
            # *)
            # args[i++]=$1;;
        # esac; shift; done
    # mpc search "${args[@]}" |
    mpc search "$@" |
    mpc add
    mpc play
}



##################################################
# Email yourself a quick message         #
##################################################

function mailme()
{
    echo "$@" | mail -s "$1" $SERVERMAIL
}



###### Usage: mailme message : mailme "process X completed"
function mailme_() { mailx -s "$@" $USER <<< "$@"; }



##################################################
# .. And function                #
##################################################

function man_()
{
    for i ; do
        xtitle The $(basename $1|tr -d .[:digit:]) manual
        command man -F -a "$i"
    done
}



##################################################
# Extended man command               #
##################################################

###### requires: sudo apt-get install w3m
function man_ext()
{
/usr/bin/man $* || w3m -dump http://google.com/search?q="$*"\&btnI | less
}



##################################################
# Manpage to ... document            #
##################################################

###### example: man2pdf wipe    =   wipe.pdf
# copyright 2007 - 2010 Christopher Bratusek
function man2pdf()
{
    case $1 in
        *help | "" )
            echo -e "\nUsage:"
            echo -e "\nman2pdf | <manualpage> [generate a pdf from <manualpage>]\n"
            tput sgr0
        ;;
        * )
            check_opt ps2pdf man2pdf
            if [[ $? != "1"  && $1 ]]; then
                man -t $1 | ps2pdf - >$1.pdf
            else    echo "No manpage given."
            fi
        ;;
    esac
}



###### example: man2text wipe   =   wipe.txt
function man2text()
{
man "$1" | col -b > ~/man_"$1".txt
}



##################################################
# What is the use of this switch?        #
##################################################

function manswitch() { man $1 | less -p "^ +$2"; }



##################################################
# Map a command over a list of files - map-files #
# /lib *.so ls -la               #
##################################################

function map-files() { find $1 -name $2 -exec ${@:3} {} \ ; }



##################################################
# Meta-Backup - backup your software selection   #
# and repositories in a deb meta package     #
##################################################

function meta-backup()
{
## Written by Arjan van Lent aka socialdefect ## VERSION: 2.1 ## Modified by Inameiname
DIALOG1="Did you enable extra repositories or PPAs on this system?. If you have no idea what this is just enter no"
DIALOG2="Your backup has been created succesfully"
DIALOG3="Something went wrong. Type bash -x meta-backup in a terminal to debug"
DIALOG4="Would you like to use the backup for a distribution upgrade?"
DIALOG5="Enter the codename of the distribution you'd like to upgrade to. eg. sid or maverick"
DIALOG6="Where woud you like to save your backup files? Enter full path. eg /home/username/backups"
mkdir -p /tmp/meta-backup/my-meta-backup/DEBIAN                     ## creating build directories
  dialog --title "Meta-backup" --yesno "$DIALOG1" 8 40                  ## repository dialog ## question add repo's
  dialog --title "Meta-backup" --infobox "..." 8 40
if [ $? = 0 ] ; then
  mkdir -p /tmp/meta-backup/my-repo-backup/etc/apt/sources.list.d
  mkdir /tmp/meta-backup/my-repo-backup/DEBIAN
  cp -R /etc/apt/sources.list.d/* /tmp/meta-backup/my-repo-backup/etc/apt/sources.list.d/
  cp -R /etc/apt/sources.list /tmp/meta-backup/my-repo-backup/etc/apt/
fi
                                            ## create the control file for the repo-backup
echo 'Section: misc
Priority: optional
Package: my-repo-backup
Version: 2.1
Maintainer: meta-backup
Depends:
Architecture: all
Description: Repository/PPA backup created by meta-backup.
 Repository/PPA backup created by meta-backup. This package can be used to install all repositories and PPAs that are installed on the computer where the backup is made.' >> /tmp/meta-backup/my-repo-backup/DEBIAN/control
                                            ## create the preinst file for the repo-backup
echo '#!/bin/sh
set -e
# Backup repo config
mv /etc/apt/sources.list /etc/apt/sources.list.old
mv /etc/apt/sources.list.d /etc/apt/sources.list.d.old' >> /tmp/meta-backup/my-repo-backup/DEBIAN/preinst
chmod +x /tmp/meta-backup/my-repo-backup/DEBIAN/preinst
                                            ## create the postinst file for the repo-backup
echo '#!/bin/sh
set -e
# Pubkeys (to generate this large key, which is all of them in one: sudo apt-key exportall > /tmp/repokeys.key)
if [ -f /tmp/repokeys.key ];then
    rm /tmp/repokeys.key
fi
sudo cat > "/tmp/repokeys.key" <<"End-of-message"' >> /tmp/meta-backup/my-repo-backup/DEBIAN/postinst
  ## get the repository keys
apt-key exportall >> /tmp/meta-backup/my-repo-backup/DEBIAN/postinst
echo 'End-of-message
if which sudo apt-key >> /dev/null; then
    if sudo apt-key add "/tmp/repokeys.key"; then
        echo "OK - repokeys key was installed"
    else
        echo "ERROR: there was a problem installing the repokeys-key"
    fi
fi
sudo rm -fv "/tmp/repokeys.key"' >> /tmp/meta-backup/my-repo-backup/DEBIAN/postinst
chmod +x /tmp/meta-backup/my-repo-backup/DEBIAN/postinst
                                            ## create the postrm file for the repo-backup
echo '#!/bin/sh
set -e
# Restore repo config
mv /etc/apt/sources.list.old /etc/apt/sources.list
mv /etc/apt/sources.list.d.old /etc/apt/sources.list.d' >> /tmp/meta-backup/my-repo-backup/DEBIAN/postrm
chmod +x /tmp/meta-backup/my-repo-backup/DEBIAN/postrm
dialog --title "Meta-backup" --yesno "$DIALOG4" 8 40                    ## Distupgrade feature
  dialog --title "Meta-backup" --infobox "..." 8 40
if [ $? = 0 ] ; then
    dialog --title "Meta-backup" --inputbox "$DIALOG5" 8 40 2> /tmp/meta-backup/upgrade
    UPGRADE=`cat /tmp/meta-backup/upgrade`
    dialog --title "Meta-backup" --infobox "..." 8 40
fi
if [ $UPGRADE = 0 ] ; then
  MYDIST=`lsb_release -cs`
  sed 's/$MYDIST/$UPGRADE/' /tmp/meta-backup/myrepo-backup/etc/apt/sources.list
  sed 's/$MYDIST/$UPGRADE/' /tmp/meta-backup/myrepo-backup/etc/apt/sources.list.d/*
fi                                          ## end dist upgrade feature
  DEPS=`aptitude search -F %p ~i --disable-columns | sed 's/$/,/' | tr '\n\r' ' ' | sed 's/, $//'`  ## get list of inst. packages to fill DEPS variable
                                            ## create the control file for the meta-backup
echo "Section: misc
Priority: optional
Package: my-meta-backup
Version: 2.1
Maintainer: meta-backup
Depends: $DEPS
Architecture: all
Description: Personal system backup created by meta-backup
 Personal system backup created by meta-backup. This package can be used to install all applications that are installed on the computer where the backup is made. Can be used on all systems using the same base system version as used on the backup machine." >> /tmp/meta-backup/my-meta-backup/DEBIAN/control
cd /tmp/meta-backup && dpkg --build my-meta-backup                  ## build and save the package(s)
if [ $? = 0 ] ; then
    cd /tmp/meta-backup && dpkg --build my-repo-backup
fi
ls /tmp/meta-backup/my-meta-backup.deb                          ## finish backup
  if [ $? = 0 ] ; then
    ERROR=no
    else ERROR=yes
  fi
ls /tmp/meta-backup/my-repo-backup.deb
  if [ $? = 0 ] ; then
    ERROR=no
  else ERROR=yes
  fi
dialog --title "Meta-backup" --inputbox "$DIALOG6" 8 40 2> /tmp/meta-backup/save    ## move the debs to selected location
    SAVE=`cat /tmp/meta-backup/save`
    dialog --title "Meta-backup" --infobox "..." 8 40
    ls $SAVE
  if [ $? = 0 ] ; then
    mv /tmp/meta-backup/*.deb $SAVE
    chmod 777 $SAVE/my-*-backup.deb
  else
    mkdir -p $SAVE
    mv /tmp/meta-backup/*.deb $SAVE
    chmod -R 777 $SAVE
  fi
if [ $ERROR = no ] ; then                               ## Display exit message
  dialog --title "Meta-backup" --infobox "$DIALOG2" 8 40
 else
  dialog --title "Meta-backup" --infobox "$DIALOG3" 8 40
fi
rm -rf /tmp/meta-backup                                 ## cleaning up
}



##################################################
# Makes directory then moves into it         #
##################################################

function mkcdr() {
    mkdir -p -v $1
    cd $1
}



function mkdircd()  { mkdir -p "$@" && eval cd "\"\$$#\""; }



##################################################
# Creates an archive from directory      #
##################################################

function mktar() { tar cvf  "${1%%/}.tar"     "${1%%/}/"; }



function mktbz() { tar cvjf "${1%%/}.tar.bz2" "${1%%/}/"; }



function mktgz() { tar cvzf "${1%%/}.tar.gz"  "${1%%/}/"; }



##################################################
# Reminder / to do list              #
##################################################

function mnote()
{
    echo -e "- $* \n" >> ~/todo
    echo -e "- $* \n" >> ~/todo.perm
    ~/motd.pl
}





##################################################
# Computes most frequent used words of text file #
##################################################

###### usage:   most_frequent "file.txt"
function most_frequent()
{
cat "$1" | tr -cs "[:alnum:]" "\n"| tr "[:lower:]" "[:upper:]" | awk '{h[$1]++}END{for (i in h){print h[i]" "i}}'|sort -nr | cat -n | head -n 30
}








##################################################
# Messagebox maker               #
##################################################

function msg()
# Author: Josh Bailey
# Email: jbsnake <at> <no spam> usalug.org
# call this like:
# msg "Title of Message Box"
# or
# msg "Title of Message Box" $height $width
{
   # function for making a messagebox
   # if it has less than two arguments
   if [[ $# < 2 ]]
   then
      # use auto-size for the messagebox
      dialog --msgbox "$1" 0 0
   else
      # use specified height and width
      dialog --msgbox "$1" $2 $3
   fi
   clear
}



##################################################
# Youtube stuff                  #
##################################################

###### stream YouTube videos directly to your media player
function mtube() {
  video_id=$(curl -s $1 | sed -n "/watch_fullscreen/s;.*\(video_id.\+\)&title.*;\1;p");
  mplayer -fs $(echo "http://youtube.com/get_video.php?$video_id");
}



alias mtube_='mplayer -fs $(echo "http://youtube.com/get_video.php?$(curl -s "$1" | sed -n "/watch_fullscreen/s;.*\(video_id.\+\)&title.*;\1;p")")'



###### mps-youtube
# requires "python-pip" and mps-youtube
# sudo apt-get install python-pip
# sudo pip install mps-youtube
# sudo pip install mps-youtube --upgrade
alias youtube='mpsyt'



###### Youtube-dl
# requires "youtube-dl"
# sudo apt-get install youtube-dl
alias yt='youtube-dl -t'



###### YouTube convert and download all user's videos to MP3s on the fly
function yt2mp3() { for j in `seq 1 301`;do i=`curl -s gdata.youtube.com/feeds/api/users/$1/uploads\?start-index=$j\&max-results=1|grep -o "watch[^&]*"`;ffmpeg -i `wget youtube.com/$i -qO-|grep -o 'url_map"[^,]*'|sed -n '1{s_.*|__;s_\\\__g;p}'` -vn -ab 128k "`youtube-dl -e ${i#*=}`.mp3";done;}



function yt2mp3-chanrip() { for count in 1 51 101 151 201 251 301; do for i in $(curl -s http://gdata.youtube.com/feeds/api/users/"$1"/uploads\?start-index="$count"\&max-results=50 | grep -Eo "watch\?v=[^[:space:]\"\'\\]{11}" | uniq); do ffmpeg -i $(wget http://youtube.com/"$i" -qO- | sed -n "/fmt_url_map/{s/[\'\"\|]/\n/g;p}" | sed -n '/^fmt_url_map/,/videoplayback/p' | sed -e :a -e '$q;N;5,$D;ba' | tr -d '\n' | sed -e 's/\(.*\),\(.\)\{1,3\}/\1/') -vn -ab 128k "$(youtube-dl -e http://youtube.com/"$i").mp3"; done; done; unset count i; }



###### download entire YouTube channel - all of a user's videos                  #
# function yt-chanrip() { for i in $(curl -s http://gdata.youtube.com/feeds/api/users/"$1"/uploads | grep -Eo "watch\?v=[^[:space:]\"\'\\]{11}" | uniq); do youtube-dl --title --no-overwrites http://youtube.com/"$i"; done }



###### download YouTube music playlist and convert it to mp3 files
function yt-pl2mp3() { umph -m 50 $1 | cclive -f mp4_720p; IFS=$(echo -en "\n\b"); for track in $(ls | grep mp4 | awk '{print $0}' | sed -e 's/\.mp4//'); do (ffmpeg -i $track.mp4 -vn -ar 44100 -ac 2 -ab 320 -f mp3 $track.mp3); done; rm -f *.mp4 ; }





##################################################
# Query Wikipedia via console over DNS       #
##################################################

function mwiki() { blah=`echo $@ | sed -e 's/ /_/g'`; dig +short txt $blah.wp.dg.cx; }



# function mwiki() { dig +short txt `echo $*|sed 's| *|_|g'`.wp.dg.cx; }



function mwiki_() { local IFS=_; dig +short txt "${*^}".wp.dg.cx; }



##################################################
# User friendly ps               #
##################################################

function my_ps() { ps $@ -u $USER -o pid,%cpu,%mem,bsdtime,command ; }



function pp() { my_ps f | awk '!/awk/ && $0~var' var=${1:-".*"} ; }



function psaux() {
    [ $# == 1 ] && ps aux | grep $1
}





##################################################
# Stupid simple note taker           #
##################################################

function note()
{
        # if file doesn't exist, create it
        [ -f $HOME/.notes ] || touch $HOME/.notes
        # no arguments, print file
        if [ $# = 0 ]
        then
                cat $HOME/.notes
        # clear file
        elif [ $1 = -c ]
        then
                > $HOME/.notes
        # add all arguments to file
        else
                echo "$@" >> $HOME/.notes
        fi
}




##################################################
# Remove apps with style: nuke it from orbit     #
##################################################

###### You can't stand programs x, y, and z. Remove all trace of their existence by adding this function to your config. It will remove the cruft, the settings, #and such and such. This function doesn't even give a damn about you trying to remove programs that don't exist: it'll just for loop to the next one on #your hit list.
# function nuke() { if [ $(whoami) != "root" ] ; then for x in $@; do sudo apt-get autoremove --purge $x; done; else for x in $@; do apt-get autoremove --purge $x; done; fi }




##################################################
# Echo the lines of a file preceded by line  #
# number                     #
##################################################

function numberLines() { perl -pe 's/^/$. /' "$@" ; }



##################################################
# How many pages will my text files print on?    #
##################################################

function numpages() { echo $(($(wc -l $* | sed -n 's/ total$//p')/60)); }



##################################################
# Open a GUI app from CLI            #
##################################################

function open() {
  $1 >/dev/null 2>&1 &
}




##################################################
# Convert a single-page PDF to a hi-res PNG, at  #
# 300dpi                     #
##################################################

###### If you skip this part: -density 300x300, you'll get a very lo-res image
function pdf2png()
{
convert -density 300x300 $1 $2
}



##################################################
# ThePirateBay.org torrent search        #
##################################################

function piratebay()
{
lynx -dump http://thepiratebay.org/search/$@|awk '/TPB.torrent$/ {print $2}'
}



##################################################
# Optimize PNG files                 #
##################################################

function pngoptim()
{
       NAME_="pngoptim"
       HTML_="optimize png files"
    PURPOSE_="reduce the size of a PNG file if possible"
   SYNOPSIS_="$NAME_ [-hl] <file> [file...]"
   REQUIRES_="standard GNU commands, pngcrush"
    VERSION_="1.0"
       DATE_="2004-06-29; last update: 2004-12-30"
     AUTHOR_="Dawid Michalczyk <dm@eonworks.com>"
        URL_="www.comp.eonworks.com"
   CATEGORY_="gfx"
   PLATFORM_="Linux"
      SHELL_="bash"
 DISTRIBUTE_="yes"
# This program is distributed under the terms of the GNU General Public License
usage() {
echo >&2 "$NAME_ $VERSION_ - $PURPOSE_
Usage: $SYNOPSIS_
Requires: $REQUIRES_
Options:
     -h, usage and options (this help)
     -l, see this script"
exit 1
}
# tmp file set up
tmp_1=/tmp/tmp.${RANDOM}$$
# signal trapping and tmp file removal
trap 'rm -f $tmp_1 >/dev/null 2>&1' 0
trap "exit 1" 1 2 3 15
# var init
old_total=0
new_total=0
# arg handling and main execution
case "$1" in
    -h) usage ;;
    -l) more $0; exit 1 ;;
     *.*) # main execution
        # check if required command is in $PATH variable
        which pngcrush &> /dev/null
        [[ $? != 0 ]] && { echo >&2 required \"pngcrush\" command is not in your PATH; exit 1; }
        for a in "$@";do
            if [ -f $a ] && [[ ${a##*.} == [pP][nN][gG] ]]; then
                old_size=$(ls -l $a | { read b c d e f g; echo $f ;} )
                echo -n "${NAME_}: $a $old_size -> "
                pngcrush -q $a $tmp_1
                rm -f -- $a
                mv -- $tmp_1 $a
                new_size=$(ls -l $a | { read b c d e f g; echo $f ;} )
                echo $new_size bytes
                (( old_total += old_size ))
                (( new_total += new_size ))
            else
                echo ${NAME_}: file $a either does not exist or is not a png file
            fi
        done ;;
    *) echo ${NAME_}: skipping $1 ; continue ;;
esac
percentage=$(echo "scale = 2; ($new_total*100)/$old_total" | bc)
reduction=$(echo $(( old_total - new_total )) \
| sed '{ s/$/@/; : loop; s/\(...\)@/@.\1/; t loop; s/@//; s/^\.//; }')
echo "${NAME_}: total size reduction: $reduction bytes (total size reduced to ${percentage}%)"
}






##################################################
# Paste command output to www.pastehtml.com in   #
# txt format                     #
##################################################

function paste() { curl -s -S --data-urlencode "txt=$($*)" "http://pastehtml.com/upload/create?input_type=txt&result=address";echo; }



##################################################
# Removes duplicate paths            #
##################################################

###### NOTE: symlinks aren't dereferenced (e.g., using `readlink`) as they may
# exist for compatibility reasons
function pathremove() {
    local IFS=':'
    local newpath
    local i

    for i in ${!2}; do
        if [ "$i" != "$1" ]; then
            newpath=${newpath:+$newpath:}$i
        fi
    done
    export $2="$newpath"
}



##################################################
# Print character classes            #
##################################################

function pcharc() { perl -e 'for (0..255) {$_ = chr($_); print if /['$1']/}' | cat -v; echo; }



##################################################
# Quick plot of numbers on stdin (can also pass  #
# plot paramaters)               #
##################################################

# requires gnuplot: sudo apt-get install gnuplot
# example: seq 1000 | sed 's/.*/s(&)/' | bc -l | plot linecolor 2
function plot() { { echo 'plot "-"' "$@"; cat; } | gnuplot -persist; }



##################################################
# Scans a port, returns what's on it.        #
##################################################

function port() {
lsof -i :"$1"
}



##################################################
# Portscan in one line               #
##################################################

function portscan()
{
$HOST=127.0.0.1;for((port=1;port<=65535;++port));do echo -en "$port ";if echo -en "open $HOST $port\nlogout\quit" | telnet 2>/dev/null | grep 'Connected to' > /dev/null;then echo -en "\n\nport $port/tcp is open\n\n";fi;done
}



##################################################
# Use Perl like grep                 #
##################################################

function prep() { perl -nle 'print if '"$1"';' $2 ; }



##################################################
# Find the printer driver (ppd) type being used  #
##################################################

function printdriver() {
        lpoptions -d $1 | grep -oe "printer-make-and-model='.*'" | cut -f2 -d "=" | sed -r s/\'//g
}



##################################################
# Print a row of characters across the terminal  #
##################################################

###### Default character is "=", default color is white
function println()
{
echo -n -e "\e[038;05;${2:-255}m";printf "%$(tput cols)s"|sed "s/ /${1:-=}/g"
}




##################################################
# Pull a single file out of a .tar.gz        #
##################################################

function pullout() {
  if [ $# -ne 2 ]; then
    echo "need proper arguments:"
    echo "pullout [file] [archive.tar.gz]"
    return 1
  fi
  case $2 in
    *.tar.gz|*.tgz)
    gunzip < $2 | tar -xf - $1
    ;;
    *)
    echo $2 is not a valid archive
    return 1
    ;;
  esac
  return 0
}



##################################################
# Create QR codes from a URL             #
##################################################

function qrurl() { curl -sS "http://chart.apis.google.com/chart?chs=200x200&cht=qr&chld=H|0&chl=$1" -o - | display -filter point -resize 600x600 png:-; }



##################################################
# Email yourself a short note            #
##################################################

function quickemail() { echo "$*" | mail -s "$*" email@email.com; }



##################################################
# Suppress output of loud commands you don't want#
# to hear from                   #
##################################################

function quietly() { "$@" |&:; }



function Quietly() { "$@" > /dev/null 2>&1; }



function quietly_() { $* 2> /dev/null > /dev/null; }



##################################################
# Scroll file one line at a time (w/only UNIX    #
# base tools)                    #
##################################################

###### usage:   rd < file ; or ... | rd
function rd_() { IFS='<ctrl-m>';$@;for i in `sed 's.\\\.\\\134.g;s.%.\\\045.g'`;do printf "$i$IFS";sleep 1;done ; }



##################################################
# TTS                        #
##################################################

function readfile() { curl -sGA Mozilla -d "language=en&format=audio/mp3&options=MaxQuality&appid=To6RoRW0R9Pt9emvqxsqEImBiS_ElZ19Dxpu9j6WURkg*&text=`python3 -c 'from urllib.parse import quote_plus; from sys import stdin; print(quote_plus(stdin.read()))' <${1:?file name is empty}`" 'http://api.microsofttranslator.com/V2/Http.svc/Speak' | mpg321 -q -; }





##################################################
# Reminder for whatever whenever         #
##################################################

function remindme()
{
sleep $1 && zenity --info --text "$2" &
}



##################################################
# Repeats a command every x seconds      #
##################################################

###### Usage: repeat PERIOD COMMAND
function repeat() {
    local period
    period=$1; shift;
    while (true); do
        eval "$@";
    sleep $period;
    done
}





##################################################
# Rip a file with handbrake and good options     #
##################################################

# function rip() {
# handbrake -i /dev/dvd -o ${HOME}/${1}.mp4 -L -U -F -f mp4 -e x264 -b 4000 -B 192
# }



##################################################
# Log rm commands                #
##################################################

function rm() {         workingdir=$( pwdx $$ | awk '{print $2}' )         /bin/rm $*         echo "rm $* issued at $(date) by the user $(who am i| awk '{print $1} ') in the directory ${workingdir}"  >> /tmp/rm.out ; }



##################################################
# Using associative array to remove all files and#
# directories under PWD except           #
##################################################

function rmall_but() { declare -A keep;for arg;do keep[$arg]=1;done;for file in *;do [[ ${keep[$file]} ]] || rm -rf "$file";done; }



##################################################
# Remove an inode via inode number       #
##################################################

function rminode() {
        find . -inum $1 -exec rm -i {} \;
}



##################################################
# Roll - archive wrapper             #
##################################################

###### usage: roll <foo.tar.gz> ./foo ./bar
function roll()
{
  FILE=$1
  case $FILE in
    *.tar.bz2) shift && tar cjf $FILE $* ;;
    *.tar.gz) shift && tar czf $FILE $* ;;
    *.tgz) shift && tar czf $FILE $* ;;
    *.zip) shift && zip $FILE $* ;;
    *.rar) shift && rar $FILE $* ;;
  esac
}



##################################################
# Removing all extended attributes from a    #
# directory tree                 #
##################################################

function rr()
{
    for i in $(ls -Rl@ | grep '^    ' | awk '{print $1}' | sort -u); \
       do echo Removing $i ... >&2;  \
       find . | xargs xattr -d $i 2>/dev/null ; done
}



##################################################
# RTFM function                  #
##################################################

function rtfm() { help $@ || man $@ || $BROWSER "http://www.google.com/search?q=$@"; }



##################################################
# Make a backup before editing a file        #
##################################################

function safeedit() {
cp $1 ${1}.backup && vim $1
}



##################################################
# Sanitize - set file/directory owner and    #
# permissions to normal values (644/755)     #
##################################################

###### usage: sanitize <file>
function sanitize()
{
  chmod -R u=rwX,go=rX "$@"
  chown -R ${USER}:users "$@"
}



##################################################
# Save a specified directory             #
##################################################

function save() { /usr/bin/sed "/$@/d" ~/.dirs > ~/.dirs1; \mv ~/.dirs1 ~/.dirs; echo "$@"=\"`pwd`\" >> ~/.dirs; source ~/.dirs ; }



##################################################
# Save a file to ~/Temp              #
##################################################

function saveit() {
cp $1 ${HOME}/Temp/${1}.saved
}



##################################################
# Screencasting with mplayer webcam window   #
##################################################

function screencastw()
{
mplayer -cache 128 -tv driver=v4l2:width=176:height=177 -vo xv tv:// -noborder -geometry "95%:93%" -ontop | ffmpeg -y -f alsa -ac 2 -i pulse -f x11grab -r 30 -s `xdpyinfo | grep 'dimensions:'|awk '{print $2}'` -i :0.0 -acodec pcm_s16le output.wav -an -vcodec libx264 -vpre lossless_ultrafast -threads 0 output.mp4
}




##################################################
# Search and replace words/phrases from text file#
##################################################

###### usage:   searchnreplace "whatever oldtext" "whatever newtext" "file(s) to act on"
function searchnreplace()
{
# Store old text and new text in variables
old=$1;
new=$2;
# Shift positional parameters to places to left (get rid of old and
# new from command line)
shift;
shift;
# Store list of files as a variable
files=$@;
a='';
for a in $files
 do
  temp=$(echo "/tmp/$LOGNAME-$a");
# echo "$temp";
  echo -n ".";
  sed -e "s/$old/$new/g" $a > $temp;
  mv $temp $a;
 done
echo;
echo -e "Searched $# files for '$old' and replaced with '$new'";
}



##################################################
# Auto send an attachment from CLI       #
##################################################

function send() {
echo "File auto-sent from linux." | mutt -s "See Attached File" -a $1 $2
}




##################################################
# Create a new script, automatically populating  #
# the shebang line, editing the script, and      #
# making it executable.              #
##################################################

function shebang() { if i=$(which $1); then printf '#!%s\n\n' $i >  $2 && vim + $2 && chmod 755 $2; else echo "'which' could not find $1, is it in your \$PATH?"; fi; }




##################################################
# Shot - takes a screenshot of your current  #
# window                     #
##################################################

function shot()
{
import -frame -strip -quality 75 "$HOME/$(date +%s).png"
}



##################################################
# Create an easy to pronounce shortened URL from #
# CLI                        #
##################################################

function shout() { curl -s "http://shoutkey.com/new?url=$1" | sed -n 's/\<h1\>/\&/p' | sed 's/<[^>]*>//g;/</N;//b' ;}




##################################################
# Colored word-by-word diff of two files     #
##################################################

###### ex.: showdiff oldversion.txt newversion.txt
function showdiff()
{
wdiff -n -w $'\033[30;41m' -x $'\033[0m' -y $'\033[30;42m' -z $'\033[0m' $1 $2
}



##################################################
# Show the contents of a file, including     #
# additional useful info             #
##################################################

function showfile()
{
width=72
for input
do
  lines="$(wc -l < $input | sed 's/ //g')"
  chars="$(wc -c < $input | sed 's/ //g')"
  owner="$(ls -ld $input | awk '{print $3}')"
  echo "-----------------------------------------------------------------"
  echo "File $input ($lines lines, $chars characters, owned by $owner):"
  echo "-----------------------------------------------------------------"
  while read line
    do
      if [ ${#line} -gt $width ] ; then
        echo "$line" | fmt | sed -e '1s/^/  /' -e '2,$s/^/+ /'
      else
        echo "  $line"
      fi
    done < $input
  echo "-----------------------------------------------------------------"
done | more
}



##################################################
# ShowTimes: show the modification, metadata-    #
# change, and access times of a file         #
##################################################

function showTimes() { stat -f "%N:   %m %c %a" "$@" ; }



##################################################
# Used by file                   #
##################################################

function sh_coloroff()
{
echo -en "$reset_color"
}



function sh_colormsg()
{
[ -n "$1" ] && echo -en "${fg_bold}${@}${reset_color}"
}



function sh_error()
{
echo -e "${fg_bold}[ e ]${reset_color} $@"
}



function sh_info()
{
echo -e "${fg_bold}[ i ]${reset_color} $@"
}



function sh_success()
{
echo -e "${fg_bold}[ k ]${reset_color} $@"
}



function sh_mesg()
{
echo -e "${fg_bold}[ m ]${reset_color} $@"
}



###### use with   svn diff -r `sh_svnprev`
function sh_svnprev()
{ echo $(( `svnversion . | sed 's/[^0-9].*//'` - 1))
}



###### $1 - path
function sh_fcore()
{
  p="."
  [ -n "$1" ] && p="$1"
  find $p -name "core\.*[[:digit:]]*" -type f 2>& /dev/null
  return 0
}



##################################################
# Ssh functions                  #
##################################################

function slak()
{
    if [ $# -lt 2 ]; then
        echo "add public key to securelink server"
        echo "usage: skak [accountname] [sl port]"
    else
        cat /Volumes/Library/ssh/id_rsa-$1.pub | ssh -q lila@localhost -p $2 "if [ ! -d ~/.ssh/ ] ; then mkdir ~/.ssh ; fi ; chmod 700 ~/.ssh/ ; cat - >> ~/.ssh/authorized_keys ; chmod 600 ~/.ssh/authorized_keys"
    fi
}



function slssh()
{
    if [ $# -lt 1 ]; then
        echo "connect to securelink ssh session"
        echo "usage slssh [port#]"
        echo "ssh -p \$1 localhost"
    else
        ssh -p $1 localhost
    fi
}



function slpg()
{
    if [ $# -lt 1 ]; then
        echo "create securelink ssh tunnel for postgres"
        echo "usage: slpg [port#]"
        echo "ssh -N localhost -L 2345/localhost/5432 -p \$1"
    else
        ssh -N localhost -L 2345/localhost/5432 -p $1
    fi
}



function sshmysql()
{
# bind MySQL hostport to forward remote MySQL connection to localhost
ssh -L 13306:127.0.0.1:3306 -N $* &
}



function sshpg()
{
    if [ $# -lt 1 ]; then
        echo "create ssh tunnel for postgres"
        echo "usage: sshpg username@server"
        echo "ssh -N \$1 -L 2345/localhost/5432"
    else
        ssh -N $1 -L 2345/localhost/5432
    fi
}



function sshpg2()
{
    if [ $# -lt 1 ]; then
        echo "create ssh tunnel for postgres"
        echo "usage: sshpg username@server"
        echo "ssh -N \$1 -L \$2/localhost/5432"
    else
        ssh -N $1 -L $2/localhost/5432
    fi
}



##################################################
# Function that outputs dots every second until  #
# command completes              #
##################################################

function sleeper() { while `ps -p $1 &>/dev/null`; do echo -n "${2:-.}"; sleep ${3:-1}; done; }; export -f sleeper



##################################################
# Slow down CPU and IO for process and its   #
# offsprings                     #
##################################################

###### requires gawk: sudo apt-get install gawk
function slow2() { ionice -c3 renice -n 20 $(pstree `pidof $1` -p -a -u -A|gawk 'BEGIN{FS=","}{print $2}'|cut -f1 -d " ") ; }



##################################################
# Sort a list of comma-separated list of numbers #
##################################################

function sort_csn() { echo "${1}" | sed -e "s/,/\n/g"| sort -nu | awk '{printf("%s,",$0)} END {printf("\n")}' | sed -e "s/,$//"; }



##################################################
# Get function's source              #
##################################################

function source_print() { set | sed -n "/^$1/,/^}$/p"; }



##################################################
# Spellchecking                  #
##################################################

###### I-Spell @ work: ENGLISH
# requires ispell: sudo apt-get install ispell
function spell()
{
    local CHATTO
    if [ $# -ne 1 ]; then
        echo -e "\033[1;32mUSAGE: \033[33mis word_to_check\033[0m"
    else
        CHATTO=$( echo $* | awk '{print $1}' )
        shift
        echo -e "----------------------------------------------------->\n"
        echo $CHATTO | ispell -a -m -B |grep -v "@"
        echo -e "----------------------------------------------------->"
    fi
}



###### Google spell checker
function spellcheck() { typeset y=$@;curl -sd "<spellrequest><text>$y</text></spellrequest>" https://www.google.com/tbproxy/spell|sed -n '/s="[0-9]"/{s/<[^>]*>/ /g;s/\t/ /g;s/ *\(.*\)/Suggestions: \1\n/g;p}'|tee >(grep -Eq '.*'||echo -e "OK");}



###### spell checks either a Web page URL or a file
# requires ispell: sudo apt-get install ispell
function webspell()
{
okaywords="$HOME/.okaywords"
tempout="/tmp/webspell.$$"
trap "/bin/rm -f $tempout" 0
if [ $# -eq 0 ] ; then
  echo "Usage: webspell file|URL" >&2;
fi
for filename
do
  if [ ! -f "$filename" -a "$(echo $filename|cut -c1-7)" != "http://" ] ; then
     continue;      # picked up directory in '*' listing
  fi
  lynx -dump $filename | tr ' ' '\n' | sort -u | \
    grep -vE "(^[^a-z]|')" | \
    # adjust the following line to produce just a list of misspelled words
    ispell -a | awk '/^\&/ { print $2 }' | \
    sort -u > $tempout
  if [ -r $okaywords ] ; then
    # if you have an okaywords file, screen okay words out
    grep -vif $okaywords < $tempout > ${tempout}.2
    mv ${tempout}.2 $tempout
  fi
  if [ -s $tempout ] ; then
    echo "Probable spelling errors: ${filename}"
    echo '-------' ; cat $tempout ; echo '========='
    cat $tempout | paste - - - -  | sed 's/^/  /'
  fi
done
}



##################################################
# Cut a part of a video              #
##################################################

# ("$1" for original file, "$2" for new file, "$3" is start time, & "$4" is length of video desired)
function splitvideo()
{
ffmpeg -vcodec copy -acodec copy -i "$1" -ss "$3" -t "$4" "$2"
}



##################################################
# Posts a file to sprunge.us and copies the      #
# related url to the clipboard           #
##################################################

function sprunge() { curl -s -F "sprunge=@$1" http://sprunge.us | xclip -selection clipboard && xclip -selection clipboard -o; }




##################################################
# Stopwatch and Countdown Timer          #
##################################################

function stopwatch() {
# copyright 2007 - 2010 Christopher Bratusek
BEGIN=$(date +%s)
while true; do
    NOW=$(date +%s)
    DIFF=$(($NOW - $BEGIN))
    MINS=$(($DIFF / 60))
    SECS=$(($DIFF % 60))
    echo -ne "Time elapsed: $MINS:`printf %02d $SECS`\r"
    sleep .1
done
}





###### countdown clock
function countdown() { case "$1" in -s) shift;; *) set $(($1 * 60));; esac; local S=" "; for i in $(seq "$1" -1 1); do echo -ne "$S\r $i\r"; sleep 1; done; echo -e "$S\rBOOM!"; }



###### countdown clock
alias countdown2='MIN=1 && for i in $(seq $(($MIN*60)) -1 1); do echo -n "$i, "; sleep 1; done; echo -e "\n\nBOOOM! Time to start."'




##################################################
# Count total number of subdirectories in current#
# directory starting with specific name.     #
##################################################

function subdir_find()
{
find . -type d -name "*TestDir*" | wc -l
}




##################################################
# Swap 2 filenames around            #
##################################################

###### from Uzi's bashrc
function swap()
{
    local TMPFILE=tmp.$$
    [ $# -ne 2 ] && echo "swap: 2 arguments needed" && return 1
    [ ! -e $1 ] && echo "swap: $1 does not exist" && return 1
    [ ! -e $2 ] && echo "swap: $2 does not exist" && return 1
    mv "$1" $TMPFILE
    mv "$2" "$1"
    mv $TMPFILE "$2"
}



function swap2() { if [ -f "$1" -a -f "$2" ]; then mv "$1" "$1.$$" && mv "$2" "$1" && mv "$1.$$" "$2" && echo "Success"; else echo "Fail"; fi; }



##################################################
# Switch two files (comes in handy)      #
##################################################

function switchfile() {
mv $1 ${1}.tmp && $2 $1 && mv ${1}.tmp $2
}



##################################################
# Creates a dated tarball            #
##################################################

function tarball()
{
    name=$1
    shift
    tar zcvf $name-`date +%Y%m%d`.tar.gz "$@"
}



##################################################
# Monitor progress of data through a pipeline    #
##################################################

function tarcp() {
    if (( $# >= 2 )); then
        echo "copy ${@[1, -2]} => ${@[-1]}"
        # http://www.ivarch.com/programs/pv.shtml
        if which pv ; then
            tar -c -f - ${@[1, -2]} | pv -t -b -r | tar -x -f - -C ${@[-1]}
        else
            tar -c -v -f - ${@[1, -2]} | tar -x -f - -C ${@[-1]}
        fi
    else
        "error, not enough parameters."
        return 1
    fi
}




##################################################
# Keeping your $HOME directory organized     #
##################################################

## having one temp dir for dls etc can quickly become mess, so try this tip to organise by date
# export TD="$HOME/temp/`date +'%Y-%m-%d'`"
# function td() {
#    td=$TD
#    if [ ! -z "$1" ]; then
#        td="$HOME/temp/`date -d "$1 days" +'%Y-%m-%d'`";
#    fi
#    mkdir -p $td; cd $td
#    unset td
# }





##################################################
# Set terminal title                 #
##################################################

function terminal_title {
    echo -en "\033]2;$@\007"
}



##################################################
# Terrorist threat level text            #
##################################################

function terrorist-level()
{
echo "Terrorist threat level: $(curl -s 'http://www.dhs.gov/dhspublic/getAdvisoryCondition' | awk -F\" 'NR==2{ print $2 }')"
}



##################################################
# Display theme info                 #
##################################################

function themeinfo() {
  if [ `pgrep emerald` ]; then
    echo "  Emerald:    `cat $HOME/.emerald/theme/theme.ini | grep description | awk -F= '{print $2}'`"
  else
    echo "  Metacity:   `gconftool-2 -g /apps/metacity/general/theme`"
  fi
  echo "  GTK:        `gconftool-2 -g /desktop/gnome/interface/gtk_theme`"
  echo "  Icons:      `gconftool-2 -g /desktop/gnome/interface/icon_theme`"
  echo "  Cursor:     `gconftool-2 -g /desktop/gnome/peripherals/mouse/cursor_theme`"
  echo "  Font:       `gconftool-2 -g /desktop/gnome/interface/font_name`"
  echo "  Wallpaper:  `gconftool-2 -g /desktop/gnome/background/picture_filename | xargs basename | cut -d. -f 1`"
  echo
}



##################################################
# Thesaurus                  #
##################################################

###### requires dict: sudo apt-get install dict
function ths() {
    dict -d moby-thes $@
}



##################################################
# A function to find the fastest free DNS server #
##################################################

###### requires: sudo apt-get install moreutils
function timeDNS() { { for x in "${local_DNS}" "208.67.222.222" "208.67.220.220" "198.153.192.1" "198.153.194.1" "156.154.70.1" "156.154.71.1" "8.8.8.8" "8.8.4.4"; do ({ echo -n "$x "; dig @"$x" "$*"|grep Query ; }|sponge &) done ; } | sort -n -k5 ; }



##################################################
# Timer function                 #
##################################################

###### Elapsed time.  Usage:
#   t=$(timer)
#   ... # do something
#   printf 'Elapsed time: %s\n' $(timer $t)
#      ===> Elapsed time: 0:01:12
# If called with no arguments a new timer is returned.
# If called with arguments the first is used as a timer
# value and the elapsed time is returned in the form HH:MM:SS.
function timer()
{
    if [[ $# -eq 0 ]]; then
        echo $(date '+%s')
    else
        local  stime=$1
        etime=$(date '+%s')
        if [[ -z "$stime" ]]; then stime=$etime; fi
        dt=$((etime - stime))
        ds=$((dt % 60))
        dm=$(((dt / 60) % 60))
        dh=$((dt / 3600))
        printf '%d:%02d:%02d' $dh $dm $ds
    fi
}






##################################################
# Top-ten commands               #
##################################################

function top10() {
    # copyright 2007 - 2010 Christopher Bratusek
    history | awk '{a[$2]++ } END{for(i in a){print a[i] " " i}}' | sort -rn | head
}



##################################################
# Switch tor on and off (requires privoxy)   #
##################################################

function torswitch() {
    # copyright 2007 - 2010 Christopher Bratusek
    if [[ $EUID == 0 ]]; then
        case $1 in
            *on )
                if [[ $(grep forward-socks4a /etc/privoxy/config) == "" ]]; then
                    echo "forward-socks4a / 127.0.0.1:9050 ." >> /etc/privoxy/config
                else
                    sed -e 's/\# forward-socks4a/forward-socks4a/g' -i /etc/privoxy/config
                    /etc/init.d/tor restart
                    /etc/init.d/privoxy restart
                fi
            ;;
            *off )
                sed -e 's/forward-socks4a/\# forward-socks4a/g' -i /etc/privoxy/config
                /etc/init.d/tor restart
                /etc/init.d/privoxy restart
            ;;
        esac
    fi
}





##################################################
# Touchpad stuff                 #
##################################################

###### to get information on touchpad
alias touchpad_id='xinput list | grep -i touchpad'



###### to disable touchpad
# using 'touchpad_id', set the number for your touchpad (default is 12)
function touchpad_off()
{
touchpad=12
xinput set-prop $touchpad "Device Enabled" 0
}



###### to enable touchpad
# using 'touchpad_id', set the number for your touchpad (default is 12)
function touchpad_on()
{
touchpad=12
xinput set-prop $touchpad "Device Enabled" 1
}



##################################################
# Transmission with blocklists           #
##################################################

function transmissionbl()
{
# Creator:  Inameiname
# Version:  1.2
# Last modified: 24 October 2011
#
# Automatically downloads and 'installs' my choice of I-Blocklist lists
# prior to running Transmission (currently, there are 82 separate lists
# to choose from)
#
# Homepage: http://www.iblocklist.com/lists.php
notify-send -t 20000 -i /usr/share/icons/gnome/32x32/status/info.png "Please wait while blocklists for Transmission BitTorrent Client are downloading..."
BLOCKLISTDIR="$HOME/.config/transmission/blocklists"
BASEURL="http://list.iblocklist.com/?list="
ENDURL="&fileformat=p2p&archiveformat=gz"
FILES=( bt_level1 bt_level2 bt_level3 us bt_dshield jcjfaxgyyshvdbceroxf ijfqtofzixtwayqovmxn bt_templist dufcxgnbjsdwmwctgfuj )
if [ ! -d $BLOCKLISTDIR ];then
    mkdir -p $BLOCKLISTDIR
else
    /bin/rm -fv -R $BLOCKLISTDIR
    mkdir -p $BLOCKLISTDIR
fi
for i in "${FILES[@]}"
  do
    # wget -c $BASEURL"$i"$ENDURL -O $BLOCKLISTDIR/$i.gz
    curl -L --retry 10 $BASEURL"$i"$ENDURL -o $BLOCKLISTDIR/$i.gz   # seems to generate less download failures than wget
    gunzip -f $BLOCKLISTDIR/$i.gz
    mv $BLOCKLISTDIR/$i $BLOCKLISTDIR/$i.txt
done
if [ ! $(find "$BLOCKLISTDIR" -type f -name "*.gz") ];then
    notify-send -t 10000 -i /usr/share/icons/gnome/32x32/status/info.png "The blocklists have finished downloading. Transmission will open momentarily..."
    transmission-gtk
    /bin/rm -fv -R $BLOCKLISTDIR/*.txt
    exit
else
    notify-send -t 10000 -i /usr/share/icons/gnome/32x32/status/info.png "The blocklists have failed to completely download. Please try again." & /bin/rm -fv -R $BLOCKLISTDIR
    exit
fi
}



##################################################
# Moves specified files to ~/.Trash      #
##################################################

###### will not overwrite files that have the same name
function trashit()
{   local trash_dir=$HOME/.Trash
    for file in "$@" ; do
        if [[ -d $file ]] ; then
            local already_trashed=$trash_dir/`basename $file`
            if [[ -n `/bin/ls -d $already_trashed*` ]] ; then
                local count=`/bin/ls -d $already_trashed* | /usr/bin/wc -l`
                count=$((++count))
                /bin/mv --verbose "$file" "$trash_dir/$file$count"
                continue
            fi
        fi
        /bin/mv --verbose --backup=numbered "$file" $HOME/.Trash
    done
}



##################################################
# Tree stuff                     #
##################################################

###### shows directory tree (requires 'tree': sudo apt-get install tree)
function treecd() {
    builtin cd "${@}" &>/dev/null
    . $BSNG_RC_DIR/dirinfo/display
    dirinfo_display
    echo -e "${epink}content:"
    tree -L 1 $TREE_OPTS
    echo "$PWD" > $HOME/.lastpwd
}



###### displays a tree of the arborescence
function treefind() {
    find "$@" | sed 's/[^/]*\//|   /g;s/| *\([^| ]\)/+--- \1/'
}



##################################################
# Search for a show at TV.COM            #
##################################################

function tvcom() {
firefox "http://www.tv.com/search.php?type=11&stype=all&tag=search%3Bfrontdoor&qs="${@}"&stype=program" &
}



##################################################
# Convert text file to pdf           #
##################################################

# Requires: sudo apt-get install txt2html python-pisa
function txt2pdf() { xhtml2pdf -b "${1%.*}" < <(txt2html "$1"); }



##################################################
# Adds "-c" canonical option to bash "type"      #
# builtin command to follow symbolic links   #
##################################################

function type() { if [ "$1" = "-c" ]; then shift; for f in "$@"; do ff=$(builtin type -p "$f"); readlink -f "$ff"; done; else builtin type $typeopts "$@"; fi; }



##################################################
# Changes spaces to underscores in names     #
##################################################

function underscore()
{
    for f in * ; do
        [ "${f}" != "${f// /_}" ]
        mv -- "${f}" "${f// /_}"
    done
}





##################################################
# Up to top directory                #
##################################################

function up() {
# copyright 2007 - 2010 Christopher Bratusek
[ "${1/[^0-9]/}" == "$1" ] && {
        local ups=""
        for ((i=1; i<=$1; i++))
        do
                ups=$ups"../"
        done
        cd $ups
        }
}



##################################################
# Move all files in current directory        #
# (recursively) up a level           #
##################################################

function upalevel()
{
find . -type f | perl -pe '(s!(\./.*/)(.*)!mv "\1\2" "\1../\2"!);' | sh
}



##################################################
# Short URLs with ur1.ca             #
##################################################

function ur1() { curl -s --url http://ur1.ca/ -d longurl="$1" | sed -n -e '/Your ur1/!d;s/.*<a href="\(.*\)">.*$/\1/;p' ; }



##################################################
# Easily decode unix-time (function)         #
##################################################

function utime() { perl -e "print localtime($1).\"\n\"";}



##################################################
# Echo a command, then execute it        #
##################################################

function v_() { echo "$@"; "$@"; }



##################################################
# Copy a file prefixed with a version number to a#
# subdirectory                   #
##################################################

function vers() { ( IFS=$'\n'; suf="_versions"; mkdir -p "$1$suf"; nr=`ls "$1$suf" | wc -l`; nr=`printf "%02d" $(($nr + 1))`; cp "$1" "$1$suf/v${nr}_$1" ) ; }



##################################################
# Edit a executable script           #
##################################################

function vie() { vi $(which $1); }



##################################################
# Run a command, redirecting output to a file,   #
# then edit the file with vim            #
##################################################

function vimcmd() { $1 > $2 && vim $2; }



##################################################
# Text message on wallpaper          #
##################################################

function wallpaperWarn() { BG="/desktop/gnome/background/picture_filename"; convert "`gconftool-2 -g $BG`" -pointsize 70 -draw "gravity center fill red  text 0,-360 'Warn' fill white  text 0,360 'Warn'" /tmp/w.jpg; gconftool-2 --set $BG -t string "/tmp/w.jpg" ; }



##################################################
# Crawl a webpage for links          #
##################################################

function webcrawl()
{
lynx -dump $1 | grep -A999 "^References$" | tail -n +3 | awk '{print $2 }'
}



##################################################
# Download all files of a certain type with wget #
##################################################

###### usage: wgetall mp3 http://example.com/download/
function wgetall() { wget -r -l2 -nd -Nc -A.$@ $@ ; }



##################################################
# Telling you from where your commit come from   #
##################################################

function where()
{
COUNT=0; while [ `where_arg $1~$COUNT | wc -w` == 0 ]; do let COUNT=COUNT+1; done; echo "$1 is ahead of "; where_arg $1~$COUNT; echo "by $COUNT commits";};function where_arg() { git log $@ --decorate -1 | head -n1 | cut -d ' ' -f3- ;
}



##################################################
# Which PATH variable should use for this script?#
##################################################

function whichpath() { local -A path; local c p; for c; do p=$(type -P "$c"); p=${p%/*}; path[${p:-/}]=1; done; local IFS=:; printf '%s\n' "${!path[*]}"; }



##################################################
# Check hosts that are online            #
##################################################

###### for those who DO NOT USE their /etc/hosts file for name resolution
# Function whoisonline adapted by:  dewar1
# This can look through resolv.conf file for address of nameservers
# (note: THIS WILL ONLY WORK IF YOU USE LOCAL NAMESERVERS! Nameservers
# from your ISP will render this function useless). It then cuts result to
# show just first 3 octets of IP address and runs nmap just as original function.
if which nmap 2>&1 > /dev/null; then
  function whodat()
  {
    if [ -n "$1" ]; then
      net="$1"
    else
      net=$(cat /etc/resolv.conf | grep 'nameserver' | cut -c12-26 | awk -F '.' '{print $1"."$2"."$3".0/24"}')
    fi
    echo "testing $net for online hosts"
    nmap -sP $net | awk '/Host/ && /up/ { print $0; }'
    echo "done"
}
fi



###### for those who USE their /etc/hosts file for name resolution
#if which nmap 2>&1 > /dev/null; then
#  function whoisonline()
#  {
#    if [ -n "$1" ]; then
#      net="$1"
#    else
#      net=$(grep `hostname` /etc/hosts | awk -F '.' '{ print $1"."$2"."$3".0/24"}')
#    fi
#    sh_info "testing $net for online boxes"
#    sudo nmap -sP $net | awk '/Host/ && /up/ { print $0; }'
#    sh_success "done"
#  }
#fi



##################################################
# Wipe command (uses 'shred', not 'wipe',    #
# which I think is better (sudo apt-get      #
# install wipe))                 #
##################################################

function wipe_() {
    # copyright 2007 - 2010 Christopher Bratusek
    cryptsetup -d /dev/urandom -c aes-xts-plain create delete $1
    shred -vzn 0 /dev/mapper/delete
    sync && sleep 4
    cryptsetup remove delete
}



##################################################
# Wordcount                  #
##################################################

###### counts frequency of words in a file
function wordfreq()
{
cat "$1"|tr -d '[:punct:]'|tr '[:upper:]' '[:lower:]'|tr -s ' ' '\n'|sort|uniq -c|sort -rn
}



##################################################
# ISO-writer                     #
##################################################

function writeiso() {
    # copyright 2007 - 2010 Christopher Bratusek
    if [[ $CD_WRITER ]]; then
        cdrecord dev=$CD_WRITER "$1"
    else    cdrecord deV=/dev/dvdrw "$1"
    fi
}




##################################################
# Adds some text in the terminal frame       #
##################################################

function xtitle()
{
    case "$TERM" in
        *term | rxvt)
            echo -n -e "\033]0;$*\007" ;;
        *)
            ;;
    esac
}



##################################################
# To create a ZIP archive of a file or folder    #
##################################################

function zipf() { zip -r "$1".zip "$1" ; }



##################################################
##################################################
##################################################







######################################################################################################################################################
###### ALIASES ###### ALIASES ###### ALIASES ###### ALIASES ###### ALIASES ###### ALIASES ###### ALIASES ###### ALIASES ###### ALIASES ###### ALIASES ######
######################################################################################################################################################








##################################################
# App-specific                   #
##################################################

alias scrot='scrot -c -d 7'
alias ss='gnome-screensaver-command -a'
alias unity-reset-icons='unity --reset-icons'                       # to reset Unity launcher icons
alias unity-reset='unity --reset'                           # to reset Unity
alias unity-session='gsettings set org.gnome.desktop.session session-name "unity"'  # GNOME3 desktop session
alias unity-set='sudo /usr/lib/lightdm/lightdm-set-defaults -s unity'           # auto login under set GNOME3 desktop


##################################################
# Computer cleanup               #
##################################################

alias cachecleanup='sudo rm -fr /root/.cache/* && sudo rm -fr ~/.cache/*'               # cleanup cache
alias cleanup="sudo apt-get -y autoclean && sudo apt-get -y autoremove && sudo apt-get -y clean && sudo apt-get -y remove && sudo aptitude -y purge `dpkg --get-selections | grep deinstall | awk '{print $1}'` && sudo deborphan | xargs sudo apt-get -y remove --purge && sudo bleachbit --clean --preset && find ~ -type f -name ".DS_Store" -exec rm {} \; && find ~ -type f -name "Thumbs.db" -exec rm {} \; && find ~ -type f -regex ".*~" -exec rm {} \; && sudo rm -rvf ~/.adobe ~/.adobe/Acrobat/*/Cache/ ~/.adobe/Acrobat/*/Preferences/reader_prefs ~/.adobe/Flash_Player/AssetCache/ ~/.amsn/*/*/cache/ ~/.amsn/*/logs/ ~/.amsn/*/voiceclips/ ~/.amsn/*/webcam/ ~/.aMule/logfile ~/.aMule/logfile.bak ~/.aMule/Temp/ ~/.azureus/active/*.bak ~/.azureus/ipfilter.cache ~/.azureus/*.log ~/.azureus/logs/ ~/.azureus/tmp/ ~/.bash_history ~/.beagle/Indexes/ ~/.beagle/Log/ ~/.beagle/TextCache/ ~/.cache/ ~/.cache/* ~/.cache/audacious/thumbs/ ~/.cache/chromium/ ~/.cache/gedit/gedit-metadata.xml ~/.cache/google-chrome/ ~/.cache/vlc/ ~/.compiz/session/ ~/.config/audacious/log ~/.config/audacious/playlist.xspf ~/.config/chromium/Default/Bookmarks.bak ~/.config/chromium/Default/Cookies ~/.config/chromium/Default/Current\ Session ~/.config/chromium/Default/Current\ Tabs ~/.config/chromium/Default/databases/Databases.db ~/.config/chromium/Default/databases/http*/ ~/.config/chromium/Default/Extension\ Cookies ~/.config/chromium/Default/Favicons/ ~/.config/chromium/Default/*History* ~/.config/chromium/Default/*History*/ ~/.config/chromium/Default/*-journal ~/.config/chromium/Default/Last\ Session ~/.config/chromium/Default/Last\ Tabs ~/.config/chromium/Default/Local\ Storage/*localstorage ~/.config/chromium/Default/Thumbnails* ~/.config/chromium/Default/Top\ Sites ~/.config/chromium/Default/Visited\ Links ~/.config/chromium/Default/Web\ Data/chrome.autofill ~/.config/chromium/Default/Web\ Data/chrome.keywords ~/.config/chromium/Local\ State/HostReferralList.json ~/.config/chromium/Local\ State/StartupDNSPrefetchList.json ~/.config/compiz/ ~/.config/emesene*/*/cache/ ~/.config/emesene*/*/log* ~/.config/emesene*/*/logs/ ~/.config/google-chrome/Default/Cookies ~/.config/google-chrome/Default/Current\ Session ~/.config/google-chrome/Default/Current\ Tabs ~/.config/google-chrome/Default/databases/Databases.db ~/.config/google-chrome/Default/databases/http*/ ~/.config/google-chrome/Default/Extension\ Cookies ~/.config/google-chrome/Default/Favicons/ ~/.config/google-chrome/Default/*History* ~/.config/google-chrome/Default/History/ ~/.config/google-chrome/Default/Last\ Session ~/.config/google-chrome/Default/Last\ Tabs ~/.config/google-chrome/Default/Local\ Storage/http*localstorage ~/.config/google-chrome/Default/Preferences/dns_prefetching.json ~/.config/google-chrome/Default/Thumbnails* ~/.config/google-chrome/Default/Top\ Sites ~/.config/google-chrome/Default/Visited\ Links ~/.config/google-chrome/Default/Web\ Data/chrome.autofill ~/.config/google-chrome/Default/Web\ Data/chrome.keywords ~/.config/google-chrome/Local\ State/HostReferralList.json ~/.config/google-chrome/Local\ State/StartupDNSPrefetchList.json ~/.config/gpodder/cache/ ~/.config/menus/*.menu.undo-* ~/.config/real/rpcookies.txt ~/.config/Screenlets/*.log ~/.config/transmission/blocklists/ ~/.config/transmission/resume/ ~/.easytag/easytag.log ~/.elinks/cookies ~/.elinks/*hist /etc/apt/sources.list.d/* ~/.evolution/cache/ ~/.exaile/cache/ ~/.exaile/covers/ ~/.exaile/exaile.log ~/.exaile/podcasts/ ~/.filezilla/recentservers.xml ~/.gconf/apps/gnome-settings/gnome-panel/%gconf.xml ~/.gconf/apps/gnome-settings/gnome-search-tool/%gconf.xml ~/.gftp/cache/ ~/.gftp/gftp.log ~/.gimp-*/tmp/ ~/.gl-117/logfile.txt ~/.gnome2/epiphany/ephy-favicon-cache.xml ~/.gnome2/epiphany/ephy-history.xml ~/.gnome2/epiphany/favicon_cache/ ~/.gnome2/epiphany/mozilla/epiphany/Cache/ ~/.gnome2/epiphany/mozilla/epiphany/cookies* ~/.gnome2/gedit-metadata.xml ~/.gnome2/rhythmbox/jamendo/ ~/.gnome2/rhythmbox/magnatune/ ~/.googleearth/Cache/dbCache.* ~/.googleearth/Temp/ ~/.goutputstream-* ~/.hippo_opensim_viewer/cache/ ~/.hippo_opensim_viewer/logs/ ~/.icedteaplugin/cache/ ~/.java/deployment/cache/ ~/.kde/cache-*/ ~/.kde*/share/apps/gwenview/recent*/*rc ~/.kde/share/apps/kcookiejar/cookies ~/.kde/share/apps/konqueror/autosave/ ~/.kde/share/apps/konqueror/closeditems_saved ~/.kde/share/apps/konqueror/konq_history ~/.kde*/share/apps/RecentDocuments/*.desktop ~/.kde/share/config/konq_history ~/.kde/tmp-*/ ~/.kde/tmp-localhost.localdomain/ ~/.libreoffice/*/*/*/cache/ ~/.libreoffice/*/*/registry/data/org/openoffice/Office/Common.xcu ~/.liferea_*/cache/ ~/.liferea_*/mozilla/liferea/Cache/ ~/.liferea_*/mozilla/liferea/cookies.sqlite ~/.links2/links.his ~/.local/share/gvfs-metadata/*.log ~/.local/share/gvfs-metadata/uuid* ~/.local/share/Trash/ ~/.local/share/Trash/* ~/.luckyBackup/logs/ ~/.luckyBackup/snaps/ ~/.macromedia ~/.macromedia/Flash_Player/ ~/.mc/filepos ~/.mc/history ~/.miro/icon-cache/ ~/.miro/miro-*log* ~/.miro/mozilla/Cache/ ~/.mozilla/default/Cache/ ~/.mozilla/extensions ~/.mozilla/firefox/Crash\ Reports/ ~/.mozilla/firefox/*.default/adblockplus/patterns-backup* ~/.mozilla/firefox/*.default/bookmarkbackups/ ~/.mozilla/firefox/*.default/Cache/ ~/.mozilla/firefox/*.default/cookies.* ~/.mozilla/firefox/*.default/downloads.sqlite ~/.mozilla/firefox/*.default/formhistory.sqlite ~/.mozilla/firefox/*.default/history.dat ~/.mozilla/firefox/*.default/minidumps/ ~/.mozilla/firefox/*.default/mozilla-media-cache/ ~/.mozilla/firefox/*.default/OfflineCache/ ~/.mozilla/firefox/*.default/reminderfox/*.bak* ~/.mozilla/firefox/*.default/sessionstore.* ~/.mozilla/firefox/*.default/startupCache/ ~/.mozilla/firefox/*.default/webappsstore.sqlite ~/.mozilla/seamonkey/*/Cache/ ~/.mozilla/seamonkey/*.default/cookies.sqlite ~/.mozilla/seamonkey/*.default/downloads.sqlite ~/.mozilla/seamonkey/*.default/urlbarhistory.sqlite ~/.mozilla/*/*.slt/chatzilla/logs/*log ~/.mozilla/*/*.slt/cookies.txt ~/.mozilla/*/*.slt/history.dat ~/.mozilla-thunderbird/*.default/signons.txt ~/.nautilus/metafiles/*/*.xml ~/.nautilus/saved-session-?????? ~/.nexuiz/data/dlcache/ ~/.ntrc_*/cookies.txt ~/.ntrc_*/history* ~/.openoffice.org/*/*/*/cache/ ~/.openoffice.org/*/*/registry/data/org/openoffice/Office/Common.xcu ~/.opera/*cache*/ ~/.opera/cookies4.dat ~/.opera/download.dat ~/.opera/global.dat ~/.opera/*history* ~/.opera/icons/ ~/.opera/pstorage/ ~/.opera/sessions/ ~/.opera/temporary_downloads/ ~/.opera/thumbnails/ ~/.opera/vlink4.dat ~/.opera/vps/????/md.dat ~/.purple/icons/ ~/.purple/logs/ ~/.recently-used.xbel ~/.recoll/xapiandb/ /root/.adobe /root/.cache/* /root/.local/share/Trash/* /root/.macromedia /root/.thumbnails/* /root/.Trash ~/.secondlife/cache/ ~/.secondlife/logs/ ~/.Skype/*/chatmsg[0-9]*.dbb ~/.Skype/*/chatsync/*/*.dat ~/.sw35/swiftweasel/*/Cache/ ~/.synaptic/log/ ~/.thumbnails/ ~/.thumbnails/* ~/.thunderbird/*.default/Cache/ ~/.thunderbird/*.default/cookies.sqlite ~/.thunderbird/*.default/signons.sqlite ~/.thunderbird/*.default/signons.txt ~/.thunderbird/default/*.slt/Cache/ ~/.thunderbird/default/*.slt/cookies.sqlite ~/.thunderbird/default/*.slt/signons3.txt ~/.thunderbird/default/*.slt/signons.sqlite ~/.thunderbird/default/*.slt/signons.txt ~/.thunderbird/Profiles/*.default/Cache/ ~/.thunderbird/Profiles/*.default/cookies.sqlite ~/.thunderbird/Profiles/*.default/signons.sqlite ~/.Trash ~/.tremulous/servercache.dat /var/backups/ /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/tmp/ ~/.viminfo ~/.wine/drive_c/winetrickstmp/ ~/.winetrickscache/ ~/.xbmc/addons/Navi-X/cache/images/* ~/.xbmc/addons/packages/* ~/xbmc*.log ~/.xbmc/userdata/Database/Textures* ~/.xbmc/userdata/Thumbnails/* ~/.xchat2/logs/*log ~/.xchat2/scrollback/ ~/.xchat2/xchatlogs/*log ~/.xine/catalog.cache ~/.xsession-errors ~/.xsession-errors.old"



##################################################
# Hardware Shortcuts                 #
##################################################

alias laptop_display='sudo cat /proc/acpi/video/VGA/LCD/brightness'     # set laptop display brightness (path may vary depending on laptop model
alias laptop_displays='echo <percentage> > /proc/acpi/video/VGA/LCD/brightness' # to discover the possible values for your display



##################################################
# Information                    #
##################################################

alias charcount='wc -c $1'                              # count number of characters in text file
alias codename='lsb_release -cs | sed "s/^./\u&/"'                  # Linux version detail - just codename (Natty, Oneiric, etc)
alias cpu_hogs='ps wwaxr -o pid,stat,%cpu,time,command | head -10'          # to find CPU hogs
alias cpus='grep -c ^processor /proc/cpuinfo'                       # number of CPU's in a system
alias cpus_='grep "processor" /proc/cpuinfo | wc -l'                    # number of CPU's in a system
alias cpu='sudo dmidecode | grep Core'                          # CPU info in a system
alias cputemp='while sleep 1; do acpi -t | osd_cat -p bottom; done &'           # to get the CPU temperature continuously on the desktop
alias ctemp='sensors -f && sensors'                         # to get the computer temperature in Fahrenheit and Celcius
alias df='df -h -x tmpfs -x usbfs'                          # displays global disk usage by partition, excluding supermounted devices
alias directorydiskusage='du -s -k -c * | sort -rn'
alias dir='ls --color=auto --format=vertical'
alias diskwho='sudo iotop'
alias distro='lsb_release -is'                              # Linux distro version (Ubuntu, Linux Mint, Debian, Fedora, etc)
alias distro_='cat /etc/lsb-release | grep DISTRIB_ID | cut -d '=' -f 2'        # Linux distro version (Ubuntu, Linux Mint, Debian, Fedora, etc)
alias distro_ver='lsb_release -rs'                          # Linux version detail - just codename version (11.04, 11.10, etc)
alias distro_vers='lsb_release -ds'                         # Linux distro and version details (Ubuntu 11.04)
alias du='du -h --max-depth=1'                              # displays disk usage by directory, in human readable format
alias dush='du -sm *|sort -n|tail'                          # easily find megabyte eating files or directories
alias hardware='sudo lshw -html > hardware.html'                    # overview of the hardware in the computer
# alias hgrep='history | grep --color=always'                       # search commands history
alias hiddenpnps='unhide (proc|sys|brute)'                      # forensic tool to find hidden processes and ports
alias hogc='ps -e -o %cpu,pid,ppid,user,cmd | sort -nr | head'              # display the processes that are using the most CPU time and memory
alias hogm='ps -e -o %mem,pid,ppid,user,cmd | sort -nr | head'              # display the processes that are using the most CPU time and memory
alias mem_hogs_ps='ps wwaxm -o pid,stat,vsize,rss,time,command | head -10'      # to find memory hogs
alias mem_hogs_top='top -l 1 -o rsize -n 10'                        # to find memory hogs
alias numFiles='echo $(ls -1 | wc -l)'                          # numFiles: number of (non-hidden) files in current directory
alias ontime='date -d @$(echo $(($(date +%s)-$(cat /proc/uptime|cut -d. -f1))))'    # knowing when a machine is turned on
alias phonesearch='grep '[0-9]\{3\}-[0-9]\{4\}' "$1"'                   # search phone #'s in file (requires XXX-XXX-XXXX format)
alias superfind='sudo find / ! \( -path /proc -prune -o -path /tmp -prune -o -path /dev -prune -o -path /mnt -prune \) -name'
alias top20='du -xk | sort -n | tail -20'                       # find the 20 biggest directories on the current filesystem
alias top-commands='history | awk "{print $2}" | awk "BEGIN {FS="|"} {print $1}" |sort|uniq -c | sort -rn | head -10'   # show most popular commands
alias topten='du -sk $(/bin/ls -A) | sort -rn | head -10'               # displays the top ten biggest folders/files in the current directory
alias top_processes="watch -n 1 'ps -aux | sort -nrk 4 | head'"             # monitoring which processes most use CPU
alias treefind_="find . | sed 's/[^/]*\//|   /g;s/| *\([^| ]\)/+--- \1/'"       # displays a tree of the arborescence
alias tree='tree -Cs'                                   # nice alternative to 'ls'
alias wordcount='wc -w $1'                              # count number of words in text file




##################################################
# Miscellaneous                  #
##################################################

# alias screencast='ffmpeg -f alsa -ac 2 -i hw:0,0 -f x11grab -r 30 -s 1280x800+0+0 -i :0.0 -acodec pcm_s16le -vcodec libx264 -vpre lossless_ultrafast -threads 0 -y output.mkv'
# alias screencast='ffmpeg -f x11grab -r 30 -s 1280x800 -i :0.0 $HOME/outputFile.mpg'   # record a screencast and convert it to an mpeg
alias screencast="ffmpeg -y -f alsa -ac 2 -i pulse -f x11grab -r 30 -s `xdpyinfo | grep 'dimensions:'|awk '{print $2}'` -i :0.0 -acodec pcm_s16le output.wav -an -vcodec libx264 -vpre lossless_ultrafast -threads 0 output.mp4"        # capture video of a linux desktop
alias trace='~/.scripts/trace'                              # visual traceroute



##################################################
# Miscellaneous Fun              #
##################################################

alias 99bottles='x="bottles of beer";y="on the wall";for b in {99..1};do echo "$b $x $y, $b $x. Take one down pass it around, $(($b-1)) $x $y"; sleep 3;done'
alias addictive='count="1" ; while true ; do read next ; if [[ "$next" = "$last" ]] ; then count=$(($count+1)) ; echo "$count" ; else count="1" ; echo $count ; fi ; last="$next" ; done'                               # simple addicting bash game
alias awesome='while $i;do `notify-send -t 200 "You are awesome :)"`;sleep 60; done;'       # get informed periodically by your box that you are awesome
alias busy='for i in `seq 0 100`;do timeout 6 dialog --gauge "Install..." 6 40 "$i";done'   # pretend to be busy in office to enjoy a cup of coffee
alias busy2='my_file=$(find /usr/include -type f | sort -R | head -n 1); my_len=$(wc -l $my_file | awk "{print $1}"); let "r = $RANDOM % $my_len" 2>/dev/null; vim +$r $my_file'
alias busy3='cat /dev/urandom | hexdump -C | highlight ca fe 3d 42 e1 b3 ae f8 | perl -MTime::HiRes -pnE "Time::HiRes::usleep(rand()*1000000)"'
# alias earth='mv ~/Pictures/Backgrounds/mercator.jpg ~/Pictures/Backgrounds/mercator.`timestamp`.jpg | wget -r -N http://static.die.net/earth/mercator/1600.jpg -O ~/Pictures/Backgrounds/mercator.jpg && gconftool-2 --type string --set /desktop/gnome/background/picture_filename ~/Pictures/Backgrounds/mercator.jpg'  # live earth wallpaper (downloads and saves each time) (GNOME2)
# alias earth='mv ~/Pictures/Backgrounds/mercator.jpg ~/Pictures/Backgrounds/mercator.`timestamp`.jpg | wget -r -N http://static.die.net/earth/mercator/1600.jpg -O ~/Pictures/Backgrounds/mercator.jpg && gsettings set org.gnome.desktop.background picture-uri "file://$HOME/Pictures/Backgrounds/mercator.jpg"' # live earth wallpaper (downloads and saves each time) (GNOME3)
# alias earth='rm -f ~/Pictures/Backgrounds/mercator.jpg && wget -r -N http://static.die.net/earth/mercator/1600.jpg -O ~/Pictures/Backgrounds/mercator.jpg && gconftool-2 --type string --set /desktop/gnome/background/picture_filename ~/Pictures/Backgrounds/mercator.jpg'  # live earth wallpaper (GNOME2)
alias einsteiny='A=1;B=100;X=0;C=0;N=$[$RANDOM%$B+1];until [ $X -eq $N ];do read -p "N between $A and $B. Guess? " X;C=$(($C+1));A=$(($X<$N?$X:$A));B=$(($X>$N?$X:$B));done;echo "Took you $C tries, Einstein";'                        # numbers guessing game
alias etchasketch='c=12322123;x=20;y=20;while read -sn1 p;do k=${c:(p-1)*2:2};let x+=$((k/10-2));let y+=$((k%10-2));echo -en \\033[$y\;"$x"HX;done' # use the 1 2 3 and 4 keys to move the cursor around the screen (It's an etch-a-sketch for your terminal!)
alias excuses='echo `telnet bofh.jeffballard.us 666 2>/dev/null` |grep --color -o "Your excuse is:.*$"'     # excuses
alias freechess='telnet fics.freechess.org 5000'                        # connects to a telnet server for free internet chess
alias funfacts='wget http://www.randomfunfacts.com -O - 2>/dev/null | grep \<strong\> | sed "s;^.*<i>\(.*\)</i>.*$;\1;";'
alias funknet='telnet the-funk.net 7000'                            # Access to Funk.net
alias futurama='curl -Is slashdot.org | sed -n '5p' | sed 's/^X-//''                # get Futurama quotations from slashdot.org servers
alias guitartune='for n in E2 A2 D3 G3 B3 E4;do play -n synth 4 pluck $n repeat 2;done'     # tune your guitar from the command line
alias iamcow='fortune | cowsay'
alias iamsurprise='fortune | cowsay -f $(random_cow)'
alias insults='wget http://www.randominsults.net -O - 2>/dev/null | grep \<strong\> | sed "s;^.*<i>\(.*\)</i>.*$;\1;";'
alias lotto='shuf -i 1-49 -n 6 | sort -n | xargs'                       # lotto generator
alias matrix='echo -e "\e[32m"; while :; do for i in {1..16}; do r="$(($RANDOM % 2))"; if [[ $(($RANDOM % 5)) == 1 ]]; then if [[ $(($RANDOM % 4)) == 1 ]]; then v+="\e[1m $r   "; else v+="\e[2m $r   "; fi; else v+="     "; fi; done; echo -e "$v"; v=""; done'
alias matrix2='echo -e "\e[31m"; while $t; do for i in `seq 1 30`;do r="$[($RANDOM % 2)]";h="$[($RANDOM % 4)]";if [ $h -eq 1 ]; then v="\e[1m $r";else v="\e[2m $r";fi;v2="$v2 $v";done;echo -e $v2;v2="";done;'
alias matrix3='COL=$(( $(tput cols) / 2 )); clear; tput setaf 2; while :; do tput cup $((RANDOM%COL)) $((RANDOM%COL)); printf "%$((RANDOM%COL))s" $((RANDOM%2)); done'
alias matrix4='echo -ne "\e[32m" ; while true ; do echo -ne "\e[$(($RANDOM % 2 + 1))m" ; tr -c "[:print:]" " " < /dev/urandom | dd count=1 bs=50 2> /dev/null ; done'
alias matrix5='tr -c "[:digit:]" " " < /dev/urandom | dd cbs=$COLUMNS conv=lcase,unblock | GREP_COLOR="1;32" grep --color "[^ ]"'
alias roulette='[ $[ $RANDOM % 6 ] == 0 ] && echo Die || echo Live'             # command line Russian roulette
alias screensaver='for ((;;)); do echo -ne "\033[$((1+RANDOM%LINES));$((1+RANDOM%COLUMNS))H\033[$((RANDOM%2));3$((RANDOM%8))m$((RANDOM%10))"; sleep 0.1 ; done'                                             # terminal screensaver
alias starwars='telnet towel.blinkenlights.nl'                          # the famous starwars ASCII version from telnet
alias termvideo_bw='mplayer -vo aa'                             # watch movies in ASCII (just direct to the video)
alias termvideo='mplayer -vo caca'                              # watch movies in ASCII (just direct to the video)


##################################################
# Network/Internet -oriented stuff       #
##################################################

alias appson="netstat -lantp | grep -i stab | awk -F/ '{print $2}' | sort | uniq"   # view only the process name using an internet connection
alias bandwidth='dd if=/dev/zero of=/dev/null bs=1M count=32768'            # processor / memory bandwidthd? in GB/s
alias hdinfo='hdparm -i[I] /dev/sda'                            # hard disk information - model/serial no.
alias hostip='wget http://checkip.dyndns.org/ -O - -o /dev/null | cut -d: -f 2 | cut -d\< -f 1'
alias hostname_lookup='lookupd -d'                          # interactive debugging mode for lookupd (use tab-completion)
alias http_trace='pkt_trace port 80'                            # to show all HTTP packets
alias ip='curl www.whatismyip.org'
alias ip_info='ipconfig getpacket en1'                          # info on DHCP server, router, DNS server, etc (for en0 or en1)
alias ip_trace='pkt_trace ip'                               # to show all IP packets
alias ipttrans='sudo iptstate -D 51413'                         # iptables state of Transmission-Daemon port (requires iptstate)
alias net1='watch --interval=2 "sudo netstat -apn -l -A inet"'
alias net2='watch --interval=2 "sudo netstat -anp --inet --inet6"'
alias net3='sudo lsof -i'
alias net4='watch --interval=2 "sudo netstat -p -e --inet --numeric-hosts"'
alias net5='watch --interval=2 "sudo netstat -tulpan"'
alias net6='sudo netstat -tulpan'
alias net7='watch --interval=2 "sudo netstat -utapen"'
alias net8='watch --interval=2 "sudo netstat -ano -l -A inet"'
alias netapps="lsof -P -i -n | cut -f 1 -d ' '| uniq | tail -n +2"
alias nethogs='sudo nethogs eth0'                           # start "nethogs" program (sudo apt-get install nethogs)
alias network='sudo lshw -C network'                            # view network device info
alias networkdump='sudo tcpdump not port 22'                        # dump all the network activity except ssh stuff
alias openports='sudo netstat -nape --inet'                         # view open ports
alias oports="echo 'User:      Command:   Port:'; echo '----------------------------' ; lsof -i 4 -P -n | grep -i 'listen' | awk '{print \$3, \$1, \$9}' | sed 's/ [a-z0-9\.\*]*:/ /' | sort -k 3 -n |xargs printf '%-10s %-10s %-10s\n' | uniq"    # lsof (cleaned up for just open listening ports)
alias ports='lsof -i -n -P'                                 # view programs using an internet connection
alias portstats='sudo netstat -s'                           # show statistics for all ports
alias randomip='echo $((RANDOM%256)).$((RANDOM%256)).$((RANDOM%256)).$((RANDOM%256))'   # generate a random IP address
alias randommac='python -c "from itertools import imap; from random import randint; print ':'.join(['%02x'%x for x in imap(lambda x:randint(0,255), range(6))])"'                                       # generate random valid mac addresses
alias website_dl='wget --random-wait -r -p -e robots=off -U mozilla "$1"'       # download an entire website
alias website_images='wget -r -l1 --no-parent -nH -nd -P/tmp -A".gif,.jpg" "$1"'    # download all images from a site
alias whois='whois -H'
alias wscan_='iwlist scan'                              # terminal network scan for wireless signals



######################################################################################################################################################
#----- MY CUSTOM STARTS HERE ------ MY CUSTOM STARTS HERE ------ MY CUSTOM STARTS HERE ------ MY CUSTOM STARTS HERE ------ MY CUSTOM STARTS HERE ------
######################################################################################################################################################


alias sublime='/opt/sublime_text/sublime_text $1'



###### jokes and quotes
alias blondes='shuf -n1 /home/me/.gnome2/nemo-scripts/My_Scripts/Jokes/Blonde-Jokes/.blonde-jokes.txt'
alias chuck-norris='shuf -n1 /home/me/.gnome2/nemo-scripts/My_Scripts/Jokes/Chuck-Norris-Jokes/.chuck-norris-jokes.txt'
alias famous-quotes='shuf -n1 /home/me/.gnome2/nemo-scripts/My_Scripts/Jokes/Famous-Quotes/.famous-quotes.txt'
alias fortune-cookie='shuf -n1 /home/me/.gnome2/nemo-scripts/My_Scripts/Jokes/Fortune-Cookie-Quotes/.fortune-cookie-quotes.txt'
alias fun-facts='shuf -n1 /home/me/.gnome2/nemo-scripts/My_Scripts/Jokes/Fun-Facts/.fun-facts.txt'
alias one-liners='shuf -n1 /home/me/.gnome2/nemo-scripts/My_Scripts/Jokes/One-Liners/.one-liners.txt'
alias yo-mama='shuf -n1 /home/me/.gnome2/nemo-scripts/My_Scripts/Jokes/Yo-Mama-Jokes/.yo-mama-jokes.txt'



##################################################
##################################################
##################################################








######################################################################################################################################################
#----- BASHRC ENDS HERE ------ BASHRC ENDS HERE ------ BASHRC ENDS HERE ------ BASHRC ENDS HERE ------ BASHRC ENDS HERE ------ BASHRC ENDS HERE ------
######################################################################################################################################################








fi  # end interactive check﻿








######################################################################################################################################################
################################### MY BASHRC FILE ################################### MY BASHRC FILE ################################### MY BASHRC FILE
######################################################################################################################################################

# mac-term
👨‍🚀 Basic settings for your terminal take off. 

## ADD GIT BRANCH NAME TO TERMINAL PROMPT (MAC)

1. - Open the Terminal app and if the file ~/.bash_profile does not already exist create it with the following command.
  1.1 touch ~/.bash_profile
2. - Open ~/.bash_profile in your favorite editor and add the following content to the bottom.
```bash
  # Git branch in prompt.

parse_git_branch() {

    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'

}

export PS1="\u@\h \W\[\033[32m\]\$(parse_git_branch)\[\033[00m\] $ "
```
If you are using an existing Terminal session, don’t forget to make the changes take effect by sourcing the file with the command source ~/.bash_profile.

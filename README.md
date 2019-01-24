# Install launch and load PostgreSQL Database Mac-OS
Step-by-step instructions to install, launch and load PostgreSQL on Mac OS 10.3 or later and run it locally.

#### If you don't have brew install
[Install brew](https://brew.sh)

#### If you don't have anaconda install
[Install anaconda](https://www.anaconda.com/download/#macos)

=================================
#### Install postgresql via brew 
`brew install postgresql`
`brew upgrade postgresql`

==================================
#### Verify that anaconda is installed 
`anaconda --version`

#### If not, use the link [install anaconda](https://www.anaconda.com/download/#macos)

==================================
#### Install the dependencies 
`conda install -c anaconda psycopg2`

=================================
#### Start PostgreSQL
`brew tap homebrew/services`
`brew services start postgresql`

=================================
#### cd directory
`cd $PATH/TO/FILE/database_name`

=================================
#### Launch PostgreSQL
`psql`

=================================
#### Create Database
`CREATE DATABASE $database_name;`

=================================
#### List DATABASES
`\l` OR `\list`

=================================
#### Using the Database
`\connect $database_name` OR `\c $database_name`

=================================
#### Load and Execute SQL File
`\i $file_name.sql`

=================================
#### OR THE PAST 2 COMMANDS IN 1
`psql -f $file_name.sql`

=================================
#### Load Database (e.g CSV)
`COPY $table_name 
FROM "$PATH/TO/FILE/$file_name.csv" DELIMITER ',' CSV HEADER;`

##### IF THE ABOVE DOESN'T, THEN USE 
`/COPY $table_name 
FROM "$PATH/TO/FILE/$file_name.csv" DELIMITER ',' CSV HEADER;`

=================================
#### See what's in the table
`\d $database_name;`

done.

==================================
#### NOTE!!!:
If you are using zsh with iTerm2, YOU WILL HAVE TO REDO THE PROCESS AFTER INSTALLATION AS WELL AS SETTING `ANACONDA SCRIPT` IN THE `~/.zshrc` file. 

I always use nano as such and here's a sample of how my `.zshrc` file looks like:

`
#test -e "${HOME}/.iterm2_shell_integration.zsh" && source "${HOME}/.iterm2_shell_integration.zsh"
SHELL="zsh"

# added by Anaconda3 5.3.1 installer
# >>> conda init >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$(CONDA_REPORT_ERRORS=false '/Users/jpro/anaconda3/bin/conda' shell.bash hook 2> /dev/null)"
if [ $? -eq 0 ]; then
    \eval "$__conda_setup"
else
    if [ -f "/Users/jpro/anaconda3/etc/profile.d/conda.sh" ]; then
        . "/Users/jpro/anaconda3/etc/profile.d/conda.sh"
        CONDA_CHANGEPS1=false conda activate base
    else
        \export PATH="/Users/jpro/anaconda3/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda init <<<

test -e "${HOME}/.iterm2_shell_integration.bash" && source "${HOME}/.iterm2_shell_integration.bash"

# added by Anaconda3 2018.12 installer
# >>> conda init >>>

# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$(CONDA_REPORT_ERRORS=false '/anaconda3/bin/conda' shell.bash hook 2> /dev/null)"
if [ $? -eq 0 ]; then
    \eval "$__conda_setup"
else
    if [ -f "/anaconda3/etc/profile.d/conda.sh" ]; then
        . "/anaconda3/etc/profile.d/conda.sh"
        CONDA_CHANGEPS1=false conda activate base
    else
        \export PATH="/anaconda3/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda init <<<

export PATH="/usr/local/sbin:$PATH"`

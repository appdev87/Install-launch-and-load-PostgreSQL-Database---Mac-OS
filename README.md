# Install launch and load PostgreSQL Database Mac-OS
Step-by-step instructions to install, launch and load PostgreSQL on Mac OS 10.3 or later and run it locally.

=================================
#### Install postgresql via brew 
`brew install postgresql`
`brew upgrade postgresql`

==================================
#### Verify that anaconda is installed 
`anaconda --version`

==================================
#### Install the dependencies 
`conda install -c anaconda psycopg2`

=================================
#### Start PostgreSQL
`brew tap homebrew/services`
`brew services start postgresql`

=================================
#### cd directory
`cd $PATH/TO/FILE`

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
`\i file_name.sql`

=================================
#### OR THE PAST 2 COMMANDS IN 1
`psql -f file_name.sql`

=================================
#### Load Database (e.g CSV)
`COPY $database_name 
FROM "$PATH/TO/FILE/$file_name.csv" DELIMITER ',' CSV HEADER;`

##### IF THE ABOVE DOESN'T, THEN USE 
`/COPY $database_name 
FROM "$PATH/TO/FILE/$file_name.csv" DELIMITER ',' CSV HEADER;`

=================================
#### See what's in the table
`\d $database_name;`

done.

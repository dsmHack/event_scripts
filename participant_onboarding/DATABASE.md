## Database.sh

# Requirements
1. jq - jq is a lightweight and flexible command-line JSON processor. [ https://stedolan.github.io/jq/ ]
 It can be installed usually by running 'sudo apt-get install jq', otherwise the binary can be installed from https://stedolan.github.io/jq/download/
2. mysql (the client) obviously.. Though, future versions of the script could be easily adapted for other databases such as postgreSQL
3. shuf - shuffle (its like a random sort) Should come standard other wise 'sudo apt-get install shuf'

#Assumptions
1. MYSQL User 'root' or argument --user has full MYSQL privileges to create/drop databases and users
2. MYSQL client is installed locally to the database server. In otherwords, the script does not pass 'host' to to mysql so 'LOCALHOST' is expected

# Options
1. --user USER : The user that has full database privileges
   You will be prompted for the password of USER for access to the database server..
2. --words WORDFILE : A file containing simple words to be used as easy random 2 word combo for the team_user passwords in the database, the default 'random-words.txt' is expected in the same directory as where you execute the script otherwise..
3. --input INPUTFILE : The path to the 'DATA_CONTRACT.jsona' file that is used as input to drive the script, the default is expected in the same directory as the script.
4. --output OUT : A File/Directory to output the database, user, password of the newly created database, users.. STDOUT is used if no file is specified
5. --action ACTION: Where action is 'setup', 'remove', 'backup'
   setup - Starts fresh, installs to database and users (removing/dropping existing first)
   remove - Removes all databases and users from the server (a backup using 'mysqldump' is performed before deletion
   backup - performs a backup of all Databases using 'mysqldump' and saves each database with timestamp into the directory path OUT. Otherwise it will create a directory called 'backup' in the current directory.



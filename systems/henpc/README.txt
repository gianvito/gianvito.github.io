HENPC
HEterogenous Network Predictive Clustering
-----------------------------------------------------
INSTALLATION
-----------------------------------------------------
HENPC is written in Java and uses postgresql as dbms. 
All you need to do is to download the system that is contained in "henpc.7z"
and unzip it into your favorite folder.
Inside this package there are the following folders and files:
- db: a folder that contains "esiti_empty.backup". This file is the dump of the
empty postgres database that will contain the results of the execution.
- sql_script: this folder contains three ".sql" files used for the creation
of postgresql functions used by the system during the dataset construction phase.
- henpc.jar: this is the runnable jar file of the system HENPC.

-----------------------------------------------------
FILE PREPARATION
-----------------------------------------------------
Before starting the system you need to copy in the henpc folder the following files:
- Move in the "db" subfolder all the database dumps on which you want execute the system.
Postgres Database dumps can be found in the package "databases.7z" with ".backup" extension.
- Move the folds folders in the main folder of henpc if you want to use ours folds.
You can find our folds in the package "folds.7z". They are structured in folders entitled:
"[dbName]_splitARFF_old". You have to move these folders directly into the main folder of "henpc.jar".
- Move configuration files in the main folder of henpc. You can find them in the package
"configurationFiles.7z". In this package there are two subfolders: "henpc" and "mrsbc".
You must move the "config.properties", found in the "henpc" subfolder, into the main directory
of "henpc.jar". You can choose if copy or not the configuration files contained in "mrsbc" folder.
These files are required only if you want to execute MrSBC competitive system.

At the end of this process you should have into a folder the following files and folders:
- db (folder containing "esiti_empty.backup" and "[dbName].backup" files)
- sql_script (folder containing sql files for postgres)
- [dbName]_split_ARFF_old (folder containing folds for k-fold cross validation)
- config.properties (file containing input parameters for HENPC)
- henpc.jar (our system)
- config.ini (configuration file of MrSBC)
- model.dtd (input file for MrSBC)

-----------------------------------------------------
CONFIGURATION
-----------------------------------------------------
Open "config.properties" file and edit the parameters in order to run henpc.
There are a lot of parameters, some of them must be left unchanged. Others can be changed and only some
of them must be edited.
Here you can find a list of paramters that must be changed. The meaning of each parameter is explained in the
config.properties file.

List of parameters you must examine:
- numberthread (if you do not want to exploit all of your CPU cores/threads)
- launchCompetitives (if you want/do not want to execute MrSBC, RelSMO and RelIBk)
- thresholdType and thresholdValue (in order to choose beta value)
- alpha
- gamma
- database (in order to choose the db you want to use)
- createFromDatabase (if you want use/not use your own txt input files)
- dburl (for the database location)
- username (postgres username)
- password (postgres password. pg_restore could not work if you do not leave a blank password and you do not put "trust" everywhere in the "pg_hba.conf" file)
- schema (postgres schema name)

The list of parameters that must be left unchanged is listed at the end of the "config.properties" file.
Please do not change them.

-----------------------------------------------------
EXECUTION
-----------------------------------------------------
Move to the henpc folder and simply run the command:
"java -jar henpc.jar"
We suggest you to add VM parameter -Xmx in order to exploit all your free RAM.
For example if you have 32 GB of RAM and your system and processes are taking 2GB of RAM, run HENPC in this way:
"java -jar henpc.jar -Xmx30G"

-----------------------------------------------------
GATHERING RESULTS
-----------------------------------------------------
You can find the results directly into the database entitled "esiti".
Otherwise at the end of execution you'll see the comma separated results directly on your standard input console.
You can copy and paste them in a csv file!

That's all folks!

*--------------*
| Requirements |
*--------------*
- JVM 1.8 or above
- PostgreSQL 9.3

*---------------------*
| How to run LP-HCLUS |
*---------------------*
1) Edit, if necessary, the configuration file
2) Create a PostgreSQL database.
Please note that the name of the database must be the same used for its backup, without the extension ".backup"
3) Run LP-HCLUS with the following syntax:
java -jar lphclus.jar <pathToConfFile>

We also provide the datasets (datasets.zip) we used fot the experiments reported in the paper.
# PostgreSQL Audit Log Analyzer

The PostgreSQL Audit extension (`pgaudit`) provides detailed session and/or object audit logging via the standard PostgreSQL logging facility.  However, logs are not the ideal place to store audit information.  The PostgreSQL Audit Log Analyzer (`pgaudit_analyze`) reads audit entries from the PostgreSQL logs and loads them into a database schema to aid in analysis and auditing.

## Install

* Install pgaudit following the instructions included with the extension.

* Update the log settings in postgresql.conf as follows:
```
log_destination = csvlog
logging_collector = on
log_connections = on
```
The log files must end with .csv and follow a naming convention that ensures files will sort alphabetically with respect to creation time.  Log location is customizable with calling pgaudit_analyze

* Install `pgaudit_analyze`:

Copy the bin and lib directories to any location you prefer but make sure there are in the same directory.

* Execute audit.sql in the database you want to audit as postgres:
```
psql -U postgres -f sql/audit.sql <db>
```
## Running

./pgaudit_analyze /path/to/log/files

## Caveats

* The pgaudit.

## Authors

The PostgreSQL Audit Log Analyzer was written by David Steele <david.steele@crunchydata.com>.
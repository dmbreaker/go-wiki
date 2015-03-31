## This page has moved: https://golang.org/wiki/SQLDrivers ##
#labels database,sql

# SQL database drivers #

The database/sql and database/sql/driver packages are designed for using databases from Go and implementing database drivers, respectively.

See the design goals doc:

> http://golang.org/src/pkg/database/sql/doc.txt

# Drivers #

Drivers for Go's sql package include:

  * **MySQL**: https://github.com/ziutek/mymysql `[*]`
  * **MySQL**: https://github.com/go-sql-driver/mysql/ `[*]`
  * **Postgres** (pure Go): https://github.com/lib/pq `[*]`
  * **SQLite**: https://github.com/mattn/go-sqlite3 `[*]`
  * **DB2**: https://bitbucket.org/phiggins/db2cli
  * **MS ADODB**: https://github.com/mattn/go-adodb
  * **ODBC**: https://bitbucket.org/miquella/mgodbc
  * **ODBC**: https://code.google.com/p/odbc
  * **Oracle**: https://github.com/mattn/go-oci8
  * **Postgres** (uses cgo): https://github.com/jbarham/gopgsqldriver
  * **QL**: http://godoc.org/github.com/cznic/ql/driver
  * **SQLite**:  https://github.com/mxk/go-sqlite
  * **Sybase SQL Anywhere**: https://github.com/a-palchikov/sqlago
  * **MS SQL Server** (pure go): https://github.com/denisenkom/go-mssqldb
  * **Firebird SQL**: https://github.com/nakagami/firebirdsql

Drivers marked with a `[*]` are both included in and pass the compatibility test suite at https://github.com/bradfitz/go-sql-test
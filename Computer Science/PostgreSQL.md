---
tags:
  - database
  - tool
---

PostgreSQL is an **open-source [[Relational Database Management System]] or RDBMS**.
It is supported on all major [[Operating System]]s.
# Cheat Sheet
## Connection
Make sure your `PGHOST` and `PGPORT` environment variables are set up correctly if you aren't using `-h`.
```sh
# Connect to the server and access the mydb database
psql mydb
# -U allows you to specify a user to connect to the database with
psql -U some-user mydb
# -h allows you to specify a host and -p a port
psql -h 10.0.0.1 -p 5000 -U some-user mydb
```
### Troubleshooting
- If you get an error about a socket not existing, **that's your connection information being incorrect or (most probably) not set up at all**.
  This happens because `psql` is trying to connect to a local socket, a fallback from a network connection.
- If you get an error about a role not existing, **your user account on the database is missing**.
## Database Management
```sh
# Creates a mydb database
createdb mydb
# Removes the mydb database
dropdb mydb
```
# Architecture
PostgreSQL uses a **client/server model**, both of which could be on different hosts.
If this is the case, they communicate over a TCP/IP connection.
## Server
A server process **manages the database** files, accept connections from clients, and **performs actions on the database** on behalf of the clients.
### Connection Management
The main `postgres` process is the **connection manager**, listening for incoming connections.
When they happen, the server **forks a new [[Process]] for every incoming connection**, so that it can be managed independently from the listening process.
## Client
The clients (or *frontend*) is **the application that wants those database operations done**.
This "client" could actually take a myriad of different shapes: a CLI utility, a GUI application, a web server that wants something on the database, or some other tool.
Most of these aren't made in-house, but developed by users of the PostgreSQL.
## Database Cluster
A *database cluster* is a dedicated **storage area for databases, on disk**.
It takes the form of a single directory under which all data will be stored, called the *data directory* or *data area*.
# Installation
Whether you install PostgreSQL through a binary or manually, **you'll need to set it up before using it**.
Use `initdb` to **initialize the data directory**.
## Cheat Sheet
```sh
# Initialize the data directory (need to be logged into the postgres user account)
initdb -D /usr/local/pgsql/data

# Start the server in the foreground
postgres -D /usr/local/pgsql/data
# Start the server in the background
postgres -D /usr/local/pgsql/data >logfile 2>&1 &

# pg_ctl helps simplify some tasks
# Start the server in the background with logfile as the log file
pg_ctl start -l logfile
# 
```
# Configuration
Two configuration files are particularly important for PostgreSQL:
- `postgresql.conf`: Controls server behavior
- `pg_hba.conf`: Controls who can connect, from where, and what they can access
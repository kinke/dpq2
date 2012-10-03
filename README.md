dpq2
====

This is yet another attempt to create a good interface to PostgreSQL from the
D 2.0 programming language.

Features
--------

* LISTEN support
* Sending binary data for type bytea

Building
--------

####Debug version (with debugging symbols)
    make debug

####Unittest version (see below)
    make unittest

####Release version
    make release

or

    make

Unittests
---------

The code contains embedded unittests using a regular functions calls, not using
standard D unittests. It is need because that unittests need to pass parameters
to connect to the database in runtime.

After building dpq2 with unittests file libdpq2 can be executed. Option "--conninfo"
may contains connection string as described in [PostgreSQL documentation]
(http://www.postgresql.org/docs/current/static/libpq-connect.html#LIBPQ-CONNSTRING).

For default connection to DB type:

    $ ./libdpq2 

Connection to usually available database "postgres":

    $ ./libdpq2 --conninfo "dbname=postgres"

Network connection:

    $ ./libdpq2 --conninfo "host=123.45.67.89 dbname=testdb user=testuser password=123123"

TODO
----

* Async queries support
* Binary reading to native D types
* Thread safe behaviour
* Make the code more transparent, CamelCasing and Autodoc
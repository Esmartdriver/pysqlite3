pysqlite3-standalone
====================

This provides a standalone pysqlite3 including a featureful sqlite3 library built
according to
http://charlesleifer.com/blog/compiling-sqlite-for-use-with-python-applications/
.

This repo allows installing via pip

.. code-block:: shell

   $ pip install git+git://github.com/karlb/pysqlite3


or with the following line in requirements.txt:

.. code-block::

   git+git://github.com/karlb/pysqlite3

If you want to use the ICU extension for improved unicode support, you need to set the following environment variables

.. code-block:: shell

   CFLAGS='-DSQLITE_ENABLE_ICU'
   CPPFLAGS=`pkg-config --cflags icu-uc icu-uc icu-i18n`
   LDFLAGS=`pkg-config --libs icu-uc icu-uc icu-i18n`

Which would result in the following command when using pip

.. code-block:: shell

    CFLAGS='-DSQLITE_ENABLE_ICU' CPPFLAGS=`pkg-config --cflags icu-uc icu-uc icu-i18n` LDFLAGS=`pkg-config --libs icu-uc icu-uc icu-i18n` pip install git+git://github.com/karlb/pysqlite3

pysqlite3
=========

This library takes the SQLite module from Python 3.6.4 and packages it as a
separately-installable module.

This may be useful for creating SQLite modules capable of working with other
versions of SQLite (via the amalgamation option).

Additional features:

* Support for user-defined window functions (requires SQLite >= 3.25)
* Support specifying flags when opening connection
* Support specifying VFS when opening connection

Original code (c) Gerhard Häring

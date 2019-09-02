Umbrella repository
-------------------

This is the umbrella repository for SQL parsing related projects. It comprises
of

- SQL parse tree in `lib-sql/ <https://github.com/cviebig/lib-sql>`_
- SQL parser in `lib-sql-text/ <https://github.com/cviebig/lib-sql-text>`_
- Data structure dumper in `lib-dump/ <https://github.com/cviebig/lib-dump>`_
- SQL parse tree dumper `lib-dump-sql/ <https://github.com/cviebig/lib-dump-sql>`_
- Interactive shell for parsing and dumping in `bin-dump-sql-text/
  <https://github.com/cviebig/bin-dump-sql-text>`_

Build time dependencies
-----------------------

- Catch2
- CMake
- Boost

Runtime dependencies
--------------------

- Boost

Docker support
--------------

This project is coming for convenience reasons with Dockerfiles to create a
build and runtime environment. However it's use is only optional. See the
subdirectory `docker/ <https://github.com/cviebig/containers-docker-arch-cpp>`_
for more info.

Example usage from this directory:

.. code-block:: sh

  export PROJECT_NAME=projsql
  export BUILD_DIR=$HOME/tmp/projsql_build
  export OUTPUT_DIR=$HOME/tmp/projsql
  export CXX=/usr/bin/clang++
  export CC=/usr/bin/clang
  docker/setup
  docker/configure Release
  docker/build dump-sql-text
  docker/execute dump-sql-text -i
  docker/execute valgrind --tool=memcheck --leak-check=full /home/user/build/test/dump-sql-text -i
  docker/cleanup
  docker/remove

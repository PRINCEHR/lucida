================================================================================
                      OpenEphyra Question Answering System

                        Nico Schlaefer (nico@cs.cmu.edu)
                           School of Computer Science
                           Carnegie Mellon University
================================================================================
Copyright (C) 2007-2011 Carnegie Mellon University.

OpenEphyra is free software: you can redistribute it and/or modify it under the
terms of the GNU General Public License as published by the Free Software
Foundation, either version 3 of the License, or (at your option) any later
version.

OpenEphyra is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with
OpenEphyra. If not, see <http://www.gnu.org/licenses/>.
================================================================================

Acknowledgements:
-----------------

OpenEphyra was originally developed by Nico Schlaefer, but many others have made
valuable contributions. Special thanks go to:

- Guido Sautter, for his work on definitional QA and the NE recognizer.
- Justin Betteridge, who developed the answer type classifier.

Content of this Distribution:
-----------------------------

bin/           Java class files
cache/         Cache files
conf/          Configuration files
doc/           Javadoc documentation
lib/           Third party libraries
log/           Log files
res/           Resource files
scripts/       Command line scripts
src/           Java source files
build.xml      Ant build file for OpenEphyra
javadoc.xml    Ant build file for the Javadoc documentation
CHANGES        Changes made in new revisions
LICENSE        GNU General Public License
README         This file

Getting Started:
----------------

If you just like to run OpenEphyra in command line mode, try the following:

- Go to the folder 'scripts'.
- Execute OpenEphyra.sh (Unix, Linux, and Mac OS) or OpenEphyra.bat (Windows).
- Type in a factoid question, 'LIST:' followed by a list question, or 'exit'.

The only system requirements are a Java runtime environment (version 1.5 or
later) and about 1 GB of free RAM.

Documentation and Support:
--------------------------

The documentation and a collection of tutorials are hosted on the Ephyra site:
<http://www.ephyra.info/>.

Downloads of new releases and a discussion forum can be found at SourceForge:
<http://sourceforge.net/projects/openephyra/>.

If you would like to be notified of new releases and other important information
regarding OpenEphyra, you can subscribe to our mailing list:
<https://lists.sourceforge.net/lists/listinfo/openephyra-announce/>.

We highly appreciate any feedback, comments, and suggestions for improvements.
Please post to our forum or send an email to nico@cs.cmu.edu.

Sponsors:
---------

The OpenEphyra effort is supported in part by IBM Open Collaboration Agreement
#W0652159.
================================================================================




================================================================================

# Lucida

This following directories are specific to Lucida:

```
OpenEphyra/src/lucida/handler/
OpenEphyra/src/lucida/main/
OpenEphyra/src/lucida/test/
```

- `OpenEphyra/src/lucida/handler/`: Contains code that handles the Lucida services
- `OpenEphyra/src/lucida/main/`: Contains an OpenEphyra wrapper to communicates with Lucida
- `OpenEphyra/src/lucida/test/`: Contains a testing client

## Build

```
$ make
```

## Run and Test

Start the server:

```
$ make start_server (port number of QA) (port number of command center, optional)
```

Note: There are two modes of usage. 
* If the port number of the command center is not provided,
or the command center cannot be connected to,
the server runs as a stand-alone program.
* Otherwise, the server can interact with the command center
and act as its client.

In either case, the server can interact with a testing client.
To run the testing client:

```
$ make start_test (port number of QA)
```

To change the knowledge base or query, you can modify `src/lucida/test/QAClient.java` and rebuild.

## Summary: Example Usage

```
$ make
$ make start_server 8081
$ # Wait until you see "Start listening to requests" in the server terminal.
$ make start_test 8081
```

================================================================================
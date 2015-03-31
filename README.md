SPARTA v1.0.2 BETA (http://sparta.secforce.com)
==

Authors:
----
SECFORCE

  Antonio Quina (@st3r30byt3)

  Leonidas Stavliotis (@lstavliotis)


Description
----

SPARTA is a python GUI application which simplifies network infrastructure penetration testing by aiding the penetration tester in the scanning and enumeration phase. It allows the tester to save time by having point-and-click access to his toolkit and by displaying all tool output in a convenient way. If little time is spent setting up commands and tools, more time can be spent focusing on analysing results. Despite the automation capabilities, the commands and tools used are fully customisable as each tester has his own methods, habits and preferences.



Requirements
----

It is recommended that Kali Linux is used as it already has most tools installed, however SPARTA would most likely also work in Debian based systems.

Kali (preferred):

    apt-get install python-elixir

Ubuntu 12.04+ (untested)

    apt-get install python-elixir python-qt4 xsltproc

Other than these, the following tools are required for SPARTA to have its minimum functionality:
- nmap (for adding hosts)
- hydra (for the brute tab)
- cutycapt (for screenshots)

In Kali Linux these can be installed with:

    apt-get install nmap hydra cutycapt

In Kali, to ensure that you have all the tools used by SPARTA's default configuration use:

    apt-get install ldap-utils rwho rsh-client x11-apps finger

Installation
----

    cd /usr/share/
    git clone https://github.com/secforce/sparta.git

    Place the "sparta" file in /usr/bin/ and make it executable.
    Type 'sparta' in any terminal to launch the application.


Source code
----

The source code is structured in folders as such:

* [app] 			   - Contains the functionality (logic) as well as the models used by both the logic and gui
* [controller]	 - The controller interfaces between the gui and the logic (MVC design)
* [db]			     - Contains everything related to database, database tables, etc
* [doc]             - Contains all SPARTA documentation
* [images] 		   - Icons and images
* [parsers] 		 - Contains nmap xml output parser files
* [scripts]		   - Contains custom scripts used by SPARTA
* [ui] 			     - Contains the gui (.ui and .py generated by Qt Creator). Do not manually edit these.
* [wordlists]		 - Contains wordlists used by SPARTA
* README.txt		 - This file.
* sparta.conf		 - SPARTA's configuration file. Edit it to add custom tools and commands. If deleted, SPARTA will regenerate a new one.
* sparta.py		   - The main program. The one that needs to be executed by the user.


Known issues
----

SPARTA uses a third-party tool called Cutycapt to take screenshots. One of the problems with the version that is currently in Kali's repositories is that it fails to take screenshots of HTTPS pages when self-signed certificates are in use. A way around this is to compile the Cutycapt executable yourself and edit SPARTA's configuration file to specify the path to the compiled executable.

It can be compiled in Kali by following these instructions:

    % sudo apt-get install subversion libqt4-webkit libqt4-dev g++
    % svn co svn://svn.code.sf.net/p/cutycapt/code/ cutycapt
    % cd cutycapt/CutyCapt
    % qmake
    % make
    % ./CutyCapt --url=http://www.example.org --out=example.png


Credits
----

Credits where credits are due. The nmap XML output parsing engine was largely based on code by yunshu, modified by ketchup and modified by us. SPARTA relies heavily on nmap, hydra, cutycapt, python, PyQt, Elixir and many other tools and technologies so we would like to thank all of the people involved in the creation of those. Credits to Bernardo Damele A.G. for the ms08-067_check script used by smbenum.sh. Credit to Diana Guardão (https://www.behance.net/didoquinhasfaaa) for the logo design. Thanks as well to our incredible team at SECFORCE for the countless bug reports and feedback. Last but not least, thank you for using SPARTA. Let us know how we can improve it! Happy hacking!

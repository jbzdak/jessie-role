Jessie Role
===========

Description
-----------

A simple role that updates sources list for debian so, packages are installed 
from stable distribution, while one can install single packages from 
testing. 

1. Jessie is a default distribution
2. Stretch packages are available, but not installed by default 

Note: 

* As of today this has been tested for 0 production systems, use with care. 

Problems: 

1. For now you need to manually install packages by issuing: 

     - name: install foo from testing 
       command: aptitude -t {{debian_distros.testing}} install foo
     

Requirements
------------

None

Role Variables
--------------

You can override following settings:

    debian_distros:
      stable: jessie
      testing: stretch
      areas: main
      mirror: http://ftp.de.debian.org/debian/
      
Where stable is name of ``stable`` distribution and ``testing`` name of testing 
distribution. They are set by name so when debian rolls new stable distro 
nothing expolodes.  

Option ``mirror`` lets you to choose mirror and areas allows you to add 
contrib or non-free area to your project

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

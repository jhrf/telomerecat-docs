.. _install:
Installing telomerecat
======================

These instructions will allow you to install and run telomerecat on your Linux or Mac computer.

Install using pip
+++++++++++++++++

`telomerecat` can be installed on most systems using pip (just like thousands of other python programs).

`pip` is a platform for installing python packages from the Python Package Index. It is widely available and comes as standard with many distribtuions of Mac OSX and Linux. You probably already have this program on your computer. Try typing the following in your console to see if you have `pip` installed:

.. code-block:: shell
  
  pip -V

If pip is installed on your system you should see some text describing the version of pip installed on your system. If your terminal reports that the command is not found you'll have to either install pip (instructions are readily available on the web) or use one of the other installation methods.

If you have root permissions on the machine that you hope to run telomerecat on the following command will install telomerecat and all dependencies:

.. code-block:: shell
  
  pip install telomerecat

If this doesn't work because of a permissions error you will need to either gain root permission (try adding sudo infront of the above command) or use a virtual environment. Virtual environments are a very common way of installing and running python based software. Full instructions on downloading and setting up a `python virtual environment may be found here`_. 

.. _python virtual environment may be found here: http://docs.python-guide.org/en/latest/dev/virtualenvs/).

Install using docker
++++++++++++++++++++

Ensure that docker is installed and working on your computer. `Instructions for docker can be found on the docker website`_.

.. _Instructions for docker can be found on the docker website: https://docs.docker.com/

Telomerecat is then installed as any other with any other docker package:

.. code-block:: shell
  
  docker pull telomerecat
pop_summary
===========

Working on a quick way to summarize the status of a POP deploy, so when the
project manager asks "How's provisioning going?", this project will provide a
quick answer.


LOCAL DEV
=========
To run dev server:

    # assumes you have an active virtualenv in . with the requirements installed
    $ . bin/activate
    $ export FLASK_APP=pop_web.py
    $ export FLASK_DEBUG=1
    $ flask run

It'll run on http://127.0.0.1:5000

POC - temporary setup
=====================

This is the hacked-up POC server.  This is *NOT* a production ready setup, clearly.

To run proof-of-concept server, in screen:

    # ssh to the openstack vm: ubuntu@sysops-jenkins.opn.lc4.d0cdn.net
    # You need the ssh key for that user, see sysops-jenkins in documents in Sysops/Sysops in lighthouse
    # fun fact: The reason jenkins is all over the names is the original VM where this was running
    #           was created to get jlee's Jenkins instance off his desktop box an into a shared env
    # Clone the pop_summary repo, create virtual env, install requirements, then:
    $ export FLASK_APP=pop_web.py
    $ flask run -h 10.81.76.112 -p 8080
    # Detach from screen

To collect the historic data and ship to the flask app (this needs to go somewhere else, opentsb?):
    # ssh to the openstack vm: ubuntu@sysops-jenkins.opn.lc4.d0cdn.net
    # CD to the cloned pop_summary repo, activate the virtual env, then:
    $ ./loop
    # Detach from screen

ADDING HISTORY
==============
To track history for a pop, add it to the list in _loop_.  Again, this clearly is not sustainable or production ready.
# monke

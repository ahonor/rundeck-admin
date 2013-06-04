The *rundeck-admin* commands help you manage your rundecks.

**Requirements**

* [rerun](http://github.com/rerun/rerun)
* [curl](http://curl.haxx.se/docs/manpage.html)
* [xmlstarlet](http://xmlstar.sourceforge.net/)
* [expect](http://en.wikipedia.org/wiki/Expect) (for ssh-copy-id)

**Download**

[![Build Status](https://travis-ci.org/ahonor/rundeck-admin.png?branch=master)](https://travis-ci.org/ahonor/rundeck-admin)

[Download a shell archive from bintray](http://dl.bintray.com/ahonor/rerun-modules). 

Or install it via yum:

    curl -s -f -L -o /etc/yum.repos.d/rerun.repo "https://bintray.com/ahonor/rerun-rpm/rpm"
    yum -y install rerun rerun-rundeck-admin


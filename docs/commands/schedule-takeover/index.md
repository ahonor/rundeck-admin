[rundeck-admin](../../index.html)
# schedule-takeover 

Claim all scheduled jobs from another cluster server.

## SYNOPSIS

    rerun rundeck-admin:schedule-takeover --uuid <> --user <> --url <> --password <>

### OPTIONS

* [    --uuid <>: the cluster server uuid.](../../options/uuid/index.html)
* [    --user <>: the login user name.](../../options/user/index.html)
* [    --url <>: rundeck server url.](../../options/url/index.html)
* [    --password <>: the login password.](../../options/password/index.html)

## README

Use **schedule-takeover** to tell a Rundeck server in 
cluster mode to claim all scheduled jobs from another cluster server.


Example
-------

The UUID option specifies the server uuid from which you want to takeover scheduling jobs.
You can obtain the server uuid from the framework.properties file:

    rundeck1 $ awk -F= '/rundeck.server.uuid/ {print $2}' /etc/rundeck/framework.properties

You should get back one line of output containing the UUID value:    
    
    1d9b13c5-782f-408b-999f-50451d4c5daf

Tell rundeck2 to takeover all jobs managed by rundeck1, using its UUID:

    rundeck2 $ rerun rundeck-admin:schedule-takeover --user admin --password --admin
        --url http://rundeck2:4440 --uuid 1d9b13c5-782f-408b-999f-50451d4c5daf
        
Output will show how many job schedules were taken over:

    Took over schedule for 2 jobs.
        
It is safe to run the command again.

    rundeck2 $ !!

No other jobs to take over.

    Took over schedule for 0 jobs.

## TESTS

Use the `stubbs:test` command to to run test plans.

    rerun stubbs:test -m rundeck-admin -p schedule-takeover

*Test plan sources*

* [schedule-takeover-1](../../tests/schedule-takeover-1.html)
  * it takes over bogus

## SCRIPT

To edit the command script for the rundeck-admin:schedule-takeover command, 
use the `stubbs:edit`
command. It will open the command script in your shell EDITOR.

    rerun stubbs:edit -m rundeck-admin -c schedule-takeover

*Script source*

* [script](script.html): `RERUN_MODULE_DIR/commands/schedule-takeover/script`

## METADATA

* `NAME` = schedule-takeover
* `DESCRIPTION` = "Claim all scheduled jobs from another cluster server."
* `OPTIONS` = "uuid user url password"

----

*Generated by stubbs:docs Mon Jun  3 11:01:12 PDT 2013*

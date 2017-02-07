Gh-ost
======

problem
-------

Most of the tools to migrate SQL databases use triggers.

Triggers are an imperfect solution because it just copy new insert to the ghost
table while the migration is running. You can't pause it, you can't throttle
it.

Solution
--------

Gh-ost use the binary log to replay inserts that happened on the old table
during the migration on the new table.

It parses the logs of insert on the old table, and can do so even from
secondary instance.

With this method, you can stop replaying these logs to reduce workload on the
master instance. You can even totally pause it as long as you keep the logs to
replay them later.

# Puppet-apply repo

This is a repo that contains the framework to get up and running with `puppet apply` against machines you want to manage with puppet consistently.

The important things to note are `bin/apply` wraps the puppet run on the remote machine, and `bin/run` syncs the required bits from your local machine up to the remote machine before invoking the `bin/apply` script.

It works over `ssh` & expects `rsync` to exist on both machines.

# Puppet-apply repo

This is a repo that contains the framework to get up and running with `puppet apply` against machines you want to manage with puppet consistently.

The important things to note are `bin/apply` wraps the puppet run on the remote machine, and `bin/run` syncs the required bits from your local machine up to the remote machine before invoking the `bin/apply` script.

It works over `ssh` & expects `rsync` to exist on both machines.

## Getting Started

* Clone this repo to your workstation & run `bundle install` (requires working ruby environment)

* Add your puppet modules to `modules/` (`role_modules` for any role modules you have!)

* Pull in any external modules via `librarian-puppet` by editing `Puppetfile` and running `bundle exec librarian-puppet install`

* Add your node definitions under `nodes/` & any hiera data you need to files under `hieradata`

* To run puppet on a remote node, call `./bin/run -H HOST_OR_IP -- --noop` to do a noop run. (We expect puppet to already be installed on the remote node.)

* Re-run without `-- --noop` to have puppet apply the changes

* Move onto the next node. (Don't forget to commit your changes into git!)

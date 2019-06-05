---
layout: post
title: "HPCC Systems Internship : Third Week Updates!!"
excerpt_separator:  <!--more-->
tags : internship hpcc 

---

Hi there,

This is a fun week. I wrote finally started writing code. I could get the tests to work correctly. The charm test can now check if the HPCC Systems standalone charm works fine. Writing the tests was a bit difficult for me as Juju does not really provide an efficient debugging method. However, I finally, could get the tests to run.

For those who may need help debugging their charms, here are a few commands which might help you debug the charm. The commands assume you are hacking on the HPCC charm but you may use them for other by making appropriate changes.


1. To see changes to the controller in real time, use

`watch -c juju status --color`

2. To debug the hooks, you can use, 

`juju debug-hook hpcc-platform/`

`juju debug-hook hpcc-platform/ <hook name>`

This would only open a session for the specified hook. If the hook name is not 
specified, all hooks are debugged. Once, debugging is done, you must exit the 
corresponding terminal pane for juju to continue executing.

Juju would retry running a hook automatically for a fixed number of times. If you need the hook to run manually, you can use 

`juju resolved hpcc-platform/1`

However, his only works if the hook failed in execution.

3. To build, you can use the build.sh file provided.

4. To run the tests, goto the built charms location (by default, build/builds/hpcc-platform) and run the test using

`python3 tests/10-deploy`

You may need to adjust the timeouts in the tests if necessary.

5. To test the stop hook, simply run 

`juju remove-application hpcc-platform`

6. To see the logs from your instance, use 

`juju debug-log --include hpcc-platform --level DEBUG --replay`


All things said, the charm can now successfully start, stop and respond to config changes.
I will be spending the next two weeks to get the design of the clustered charm ready. More on that in the coming weeks.

Yash Jain
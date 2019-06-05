---
layout: post
title: "HPCC Systems Internship : Fourth Week Updates!!"
excerpt_separator:  <!--more-->
tags : internship hpcc 

---

Hi there,

As i had mentioned before, I worked on the design part ths week. The clustered HPCC Systems platform has multiple components such as Thor for distributed storage, Roxie for online data processing, Sasha for backups, Dali for File Server and Authorization. These components need to interact with each other for the platform to function as expected. This is what adds to the complexity.

For designing we started with a plan to go and create separate charm for each component. But getting this done during a 12 week inteernship seemed difficult. So we moved to a different plan of creating a admin node which goes and sets up other nodes. But this also became quite complex and unnecessarily added a single point of failure. So we have now decided to create only two charms one for dali and one for other nodes. This seems like a resonable target to achieve during the course of the internship. 

As for storage, I did experiment with AWS EBS for AWS Cloud and lvm for localhost. But incorporating these seems difficult to achieve in 12 weeks so unfortunately, we won't be supporting persistent storage in the final charm.

I would be working on the dali charm for the next 2 weeks. Will be writing another post on that soon. Thanks for reading.

Yash Jain
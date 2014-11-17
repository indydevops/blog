---
layout: post
title:  "Amazon EC2 Networking Deep Dive"
date:   2014-11-12
author: "Chris Chalfant"
---

<iframe src="//www.slideshare.net/slideshow/embed_code/41571893" width="425" height="355" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/AmazonWebServices/sdd419-amazon-ec2-networking-deep-dive-and-best-practices-aws-reinvent-2014" title="(SDD419) Amazon EC2 Networking Deep Dive and Best Practices | AWS re:Invent 2014" target="_blank">(SDD419) Amazon EC2 Networking Deep Dive and Best Practices | AWS re:Invent 2014</a> </strong> from <strong><a href="//www.slideshare.net/AmazonWebServices" target="_blank">Amazon Web Services</a></strong> </div>

Much of this talk was stuff we already knew about placement groups. The more complicated use of ENIs could be something to read up on, though.

Network Perf Concepts
---------------------
* placement groups
* enhanced networking
* vpc (all this stuff req vpc)

Enhanced Networking Instance Families
-------------------------------------
* c3
* r3
* i2

you can put an instance in two different subnets by
using ENIs.

Placement Group Basics
---------
* launch all PG instances at the same time
* use homogeneous instance types

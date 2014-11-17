---
layout: post
title:  "PostgreSQL on RDS Deep Dive"
date:   2014-11-12
author: "Chris Chalfant"
---

<iframe src="//www.slideshare.net/slideshow/embed_code/41571778" width="425" height="355" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/AmazonWebServices/sdd409-amazon-rds-for-postgresql-deep-dive-aws-reinvent-2014" title="(SDD409) Amazon RDS for PostgreSQL Deep Dive | AWS re:Invent 2014" target="_blank">(SDD409) Amazon RDS for PostgreSQL Deep Dive | AWS re:Invent 2014</a> </strong> from <strong><a href="//www.slideshare.net/AmazonWebServices" target="_blank">Amazon Web Services</a></strong> </div>

Dropped into this one before the next session.

Illumina talked about how they use PGSQL for their cloud genomics offering. They are very happy with price & perf.

Definitely ready for production. Multi-AZ w/ read replicas.

Some mention of using bursting class machines (t2) to get awesome price/perf at least until your cpu budget is used up.

Typically much better price/perf when you upgrade to newer instance classes.

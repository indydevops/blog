---
layout: post
title:  "Nike's Journey to Microservices"
date:   2014-11-12
author: "Chris Chalfant"
---

<iframe src="//www.slideshare.net/slideshow/embed_code/41527279" width="425" height="355" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/AmazonWebServices/arc308-nikes-journey-into-microservices-aws-reinvent-2014" title="(ARC308) Nike&#x27;s Journey into Microservices | AWS re:Invent 2014" target="_blank">(ARC308) Nike&#x27;s Journey into Microservices | AWS re:Invent 2014</a> </strong> from <strong><a href="//www.slideshare.net/AmazonWebServices" target="_blank">Amazon Web Services</a></strong> </div>

Nike+ team started with a couple of monolithic apps and migrated to microservice architecture while at the same time modifying org structure to match.

start state:
------------
* 24/7 work cycle
* all releases had bugs
* months to release new feature
* manual testing

2 dev days, 15 days stabilizing per 3wk cycle

9 diff dev teams

2012
----
* moved to startup dev cycle
* started using jmeter/junit

2013
----
* reorged teams
* TDD, paired programming
* 400k LOC/1.5MLOC testing
* pull requests peer-reviewed 100%
* 5-10 days dev/15
* strict deployment and change control
* reduced to 3 dev teams
* tech debt repayment
* stable deployments
* sane work cycle
* weeks to months to deploy
* slow and stable product

Now
---
* "Free your mind" -- management
* db deployments still too manual
* config mngmnt still delays
* small changes have unintended consequences
* "normalization is the root of all evil"
* big org approvals for everything

Microservices (and related org practices)
-----------------------------------------
* phoenix pattern: immutable deployments
* share nothing: cassandra
* continuous delivery: trust your engineers, reduce risk of deploy
* consumer experience flows vs. end-to-end implementations

Life is not perfect
-------------------
* integration w/ legacy systems still hard
* notification pattern through webhooks makes this a bit easier
* break up all that is shared

Patterns (advice)
--------
* get to production fast
* use netflix oss stack extensively (zuul, eureka)
* zuul routes requests to specific services
* CQRS used pervasively
* Notification pattern: use SNS/SQS for universal messaging pattern
* one service controls the sns topic, other services hook up sqs to it
* Nike engaged AWS folks to help architect
* legacy data svcs usually returned lots of extra data unrelated to data requested
* break these into smaller svcs with their own endpoints
* CQRS -- cmd, process and query clusters. sep dbs for reads/writes.

client benefit
--------------
* ask only for the data you need
* client-side caching, compositing
* scaling concerns do not cross functional boundaries

Now
---
* continuous delivery
* much smaller projects (700-2kLOC)
* production release several times/day (dev+quality eng)
* open source feel, pick up an issue and do it
* they use scrum, 1-2 day tasks -- no more
* old 2wk delivery process required 1-2hr downtime
* hours to deliver new feature
* in-house product understanding very high (this was a journey but seems very important to them)
* this gets eng work cycle down to a sane # of hours and eng much more happy

Aggressively moving to microsvcs with strong api contracts, horizontally scaling.

NetflixOSS big jump start for them.

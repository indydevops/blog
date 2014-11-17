---
layout: post
title:  "Gaming DevOps"
date:   2014-11-13
author: "Chris Chalfant"
---

*No slides yet*

Mitch Garnaat, Scopely (also creator of python aws sdk boto library)

Background
----------
* Scopely does ios and android games, 35M users
* Bs of requests
* 100% AWS

"If you have to explain deployment to your customers you have failed."

Modified Blue/Green Deployments
-------------------------------
* Mix of GREEN and BLUE deployment.
* True blue/green has ELB warm-up issues and requires 2x resources.
* Single ELB, no DNS changes, fewer moving pieces.

Preview
-------
1. checkin to develop branch
1. build
1. start preview instance from last baked ami
1. install new version
1. run tests on preview instance
1. merge develop into master
1. build
1. bake new golden ami

They use windows so reducing startup time is important.
They release several times / week, not / day.

Staging
-------
1. create new ASG configured for new ami
1. attach to ELB
1. launch a few instances
1. monitor carefully as prod traffic goes to new instances
1. scale up
1. remove old ASG

They use jenkins, ansible, cloudformation.
They wrote their own automan w/ python configured with yaml.
They use cygwin and ssh on windows (for ansible).

Monitoring
----------
* NewRelic (with annotations for release)
* ElasticSearch for logs
* They push logs into kinesis and then into ElasticSearch
* Keep 1 week of log data
* custom python app to read from kinesis, ship log data to ElasticSearch and alert on stream by sending SNS message

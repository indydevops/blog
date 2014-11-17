---
layout: post
title:  "From Zero to NoSQL Hero: Amazon DynamoDB Tutorial"
date:   2014-11-12
author: "Chris Chalfant"
---

<iframe src="//www.slideshare.net/slideshow/embed_code/41535856" width="425" height="355" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/AmazonWebServices/bdt203-from-zero-to-nosql-hero-amazon-dynamodb-tutorial-aws-reinvent-2014" title="(BDT203) From Zero to NoSQL Hero: Amazon DynamoDB Tutorial | AWS re:Invent 2014" target="_blank">(BDT203) From Zero to NoSQL Hero: Amazon DynamoDB Tutorial | AWS re:Invent 2014</a> </strong> from <strong><a href="//www.slideshare.net/AmazonWebServices" target="_blank">Amazon Web Services</a></strong> </div>

Talk by dynamodb dev and a guy from "Here".

amazon.com composed of results from 1000s of svcs.
Using rdbms for all of these svcs.
Many of these are amenable to k/v store.

max item size incr to 400KB.
attribute datatypes a superset of JSON

cost (in provisioned throughput) is 2x for consistent reads.
now w/ sql-like expressions, atomic counters.
writes can return a read for free.
new document sdks.

[dynamodb local](http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Tools.DynamoDBLocal.html): run local api server backed by sqlite w/ javascript web shell (which has a tutorial). This tool is very useful for exploring dynamodb's features and learning how best to persist your data.

local vs global secondary indexes? read up on this more.

conditional writes: accept a write only if values meet criteria.
using version numbers and conditional writes we can make sure that
writes persist in order even if they come from many different clients at different times.

dynamodb "mapper" (part of sdk) will do item versioning for you.

there is a python tic-tac-toe eg on the dev guide.

HERE.com: location/mapping service.

geolocation of addresses 100s GB in elasticache, 40M transactions/day.

100s of RDBMS for tracking/analytics.

10s of billions of file index records stored in 10TB tables for runtime reads.

Street-level imagery collection.

Used 400 machines for 2 months to move, index, validate 2PB of images.

they glom tons of images together into a binary s3 object and do ranged reads to recreate the jpg. Must be to reduce total number of objects in s3.

DR
--
* hot dynamodb standby (second table) -- never used
* periodic backups to s3
* no production interruption from dynamo or s3


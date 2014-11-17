---
layout: post
title:  "re:Invent re:Cap"
date:   2014-11-17
author: "Chris Chalfant"
---

Slides for sessions are on [slideshare](http://www.slideshare.net/AmazonWebServices/tag/reinvent2014/?adbid=709885272452154&adbpl=fb&adbpr=247010772072942&adbsc=reInvent_20141116_35705947).

Podcasts for sessions are on [iTunes](https://itunes.apple.com/us/podcast/aws-re-invent-2014/id941313180?mt=2&ign-mpt=uo%3D2).

Andrew's Takeaways
------------------
1. If at all possible, have AWS handle your edge. For example using Cognito, Javascript aws-sdk talking to SQS allows you to reliably get your traffic into Amazon with nearly unlimited scalability. The use of the javascript SDK to allow client devices to interact with AWS directly is very prevalent.
2. If generating a VPC, consider building a software-defined network with ENIs automated with a tool such as Ansible. This will make the layout of the environment extremely precise and static. The services/instances can then be swapped out very easily with little impact.
3. When doing blue/green deployments, don’t move the DNS entry with route53. Also, don’t move an elastic IP. Use a second ASG hooked to the original ELB. If required, you can use this to fold in a few “canary” instances before scaling the second ASG up and taking the old ASG out of service.
4. It is possible to leverage Dynamo conditional updates to embed some of the business logic in the DB.  This could be dangerous for the same reason that complicated SPROCs can make an environment harder to support. However, the scalability benefits may make this worthwhile.
5. Docker is happening. We need to learn it along with etcd and/or zookeeper.
6. We are on the right track with Automan.

Chris's Takeaways
-----------------
1. AWS is increasingly used by enterprises, not just startups. See [NYT Article](http://www.nytimes.com/2014/11/17/business/amazon-moves-to-extend-cloud-computing-dominance.html?_r=0). "Two years ago, public clouds were maybe 2 percent of all computing workloads," said Lydia Leong, a senior analyst at Gartner. "Now they are more than 10 percent. By 2018, it will be more than 50 percent."
2. AWS's feature growth rate is unmatched. For most services, over time, the price goes down and the feature set goes up. We heard this in many talks.
3. Nearly every highly-available, highly-scalable architecture we saw was share-nothing, stateless, parallel services on top of quorum-based, multiple-copy/redundant, sharded persistence layers.
4. Very small teams can manage very large environments with the right automation. EA Games has a team of *three* people operating a backend supporting over 6M daily users and 20k requests per second.
5. There are huge cost savings in moving from traditonal relational databases to DynamoDB. EA Games went from a 120 instance MySQL cluster operated by a dedicated DBA team costing over $1M/year to DynamoDB (managed by the dev team) with a 90% cost savings.
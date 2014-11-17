---
layout: post
title:  "So You Think You Can Architect?"
date:   2014-11-13
author: "Andrew Kaczorek"
---

Constantin Gonzalez - Solutions Architect with Amazon Web Services  
Jan Metzner - Solutions Architect with Amazon Web Services  
Michael Sandbichler - CTO with ProSiebenSat.1 Digital GmbH  

TV talent shows with online and mobile voting options pose a huge challenge for architects: How do you handle millions of votes in a very short time, while keeping your system robust, secure, and scalable? Attend this session and learn from AWS customers who have solved the architectural challenges of setting up, testing, and operating mobile voting infrastructures. We will start with a typical, standard web application, then introduce advanced architectural patterns along the way that help you scale, secure, and simplify your mobile voting infrastructure and make it bulletproof for show time! We'll also touch on topics like testing and support during the big event.

* 3 months to deliver solution from scratch
* show concept and voting app were developed in parallel
* casting show in brazil and quiz show in germany ended in disaster after failure of live-voting
* 90% load within seconds
* 500k concurrent users expected, but prepare for 3 mill
* 100% connectivity and availability required, or the show fails
* use amazon cognito, mobile analytics, sns push notifications, amazon mobile SDK
* ELB pre-warming
* conditional updates can allow DynamoDB to do some of the back end functionality
* dynamo conditional updates
* use SQS to throttle DynamoDB throughput

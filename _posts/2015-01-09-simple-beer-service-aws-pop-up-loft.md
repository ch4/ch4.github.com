---
layout: post
title: "Simple Beer Service - AWS Pop-Up Loft 01/09/2015"
modified: 2015-01-12 00:11:07 +0000
tags: [notes, IoT, AWS, kinesis, big data, hardware]
image:
  feature: 
  credit: 
  creditlink: 
comments: "Tips on how to scale large data streams and design for reliability"
share: 
---
The AWS Simple Beer Service team came in and gave tips on how to scale IoT data streams and design hardware for maximum reliability.

- log all device registers, so that big data analytics can be performed later in the cloud

- ack-back to acknowledge commands sent to the device

- structure s3 config/command files so that it's sorted by location/area/type/customer/etc
  - e.g. /:location/:type/:MAC

- anti-pattern: push firmware updates remotely
  - problem: if you kill it, it's dead, nobody's around to fix it
  - use staged rollouts, careful exception management
  - have a fallback mode that is unbreakable

- bootstrapped device setup
  - beer dispenser boots up with wifi in AP mode, then you can connect to it with any device to config new SSID/password/etc, then it restarts into normal mode
 
More info [http://aws.amazon.com/iot/](http://aws.amazon.com/iot)
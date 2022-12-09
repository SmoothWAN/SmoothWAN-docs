1. Visit _Network -> SQM QoS_
1. Set the `Download Speed` and `Upload Speed` to your expected total aggregation speed and **add 20%** (1 Mbit = 1000 Kbit)
1. Choose `connectify0` in `Interface name` and toggle enable
1. Select `Queue Discipline` tab and set discipline/script to `cake/piece-of-cake`
1. Toggle the two `Show and Use Advanced Configuration.` to reveal `Advanced option string to pass to the ingress queueing` & `...egress queueing`
1. In ingress textbox add `diffserv4 nat dual-dsthost ingress` & in egress: `diffserv4 nat dual-srchost ack-filter`
1. _Save & Apply_, changes are effective immediately.

Tip: 
* Reduce the additional 20% added if there is no effect in small increments, test the results by downloading a large file with parallel sockets (download accelerator or speed test) on two clients with a 10 second delay before starting the download on the second client, both should show the speed each at ~50% of the total aggregate speed.   
* Normally, the delayed client will use 1/4th or so without host isolation shaping unless both clients start at the same time.  
* Equal distribution works when all lines are in good conditions or near the speed set in SQM only.

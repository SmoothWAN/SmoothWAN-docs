## Instructions

1. Visit _Network -> SQM QoS_  
2. Set the `Download Speed` and `Upload Speed` to your expected total aggregation speed and **add 20%** (1 Mbit = 1000 Kbit)  
3. Choose `connectify0` in `Interface name` and toggle enable  
4. Select the `Queue Discipline` tab and set the discipline/script to `cake/piece-of-cake`  
5. Toggle the two `Show and Use Advanced Configuration` to reveal `Advanced option string to pass to the ingress queueing` & `...egress queueing`  
6. In the ingress textbox, add `diffserv4 nat dual-dsthost ingress` & in egress: `diffserv4 nat dual-srchost ack-filter`  
7. _Save & Apply_, changes are effective immediately.  

---

## Tips

* Reduce the additional 20% added if there is no effect in small increments. Test the results by downloading a large file with parallel sockets (download accelerator or speed test) on two clients, with a 10-second delay before starting the download on the second client. Both should show the speed, each at ~50% of the total aggregate speed.  

* Without this setup, the delayed client will use about 1/4th of the speed unless both clients (TCP) start at the same time due to bursty throughput. The effect is less noticeable with near servers (less than 30ms delay).  

* Equal distribution works when all lines are in good conditions or near the speed set in SQM only.  

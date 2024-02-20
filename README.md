# cni-perf
Test Container Network Performace Script

# use method

```
./cni-perf {KUBE-OVN/CALICO/OTHER} {node1Name} {node2Name} [caseList]  caseList -- default: 1,2,3
=======================================================================================================
case 1: Pod to Pod in the same Nodes
case 2: Pod to Pod in the different Nodes
case 3: Node to Node
case 4: Pod to the Node where the Pod is located
case 5: Pod to the Node where the Pod is not located
case 6: Pod to the cluster ip service
case 7: Host to the Node port service where the Pod is not located on the target Node
case 8: Host to the Node port service where the Pod is located on the target Node
case 9: Host to the lb service
```

# example

```
[root@localhost cni-perf]# ./cni-perf KUBE-OVN kube-ovn-control-plane kube-ovn-worker 1
=============================== case 1: Pod to Pod in the same Nodes ===============================
============================== Prepareing Performance Test Resources ===============================
pod/1-client unchanged
pod/1-server unchanged
pod/1-client condition met
pod/1-server condition met
====================================================================================================
Size            TCP Latency     TCP Bandwidth   UDP Latency     UDP Lost Rate   UDP Bandwidth
64              14.4 us         247 Mbits/sec   16.3 us         (0%)            43.6 Mbits/sec
128             17.4 us         451 Mbits/sec   16.5 us         (0%)            95.1 Mbits/sec
512             15.6 us         1.19 Gbits/sec  16 us           (0%)            358 Mbits/sec
1k              17.3 us         1.74 Gbits/sec  15.7 us         (0.13%)         808 Mbits/sec
4k              23.6 us         1.75 Gbits/sec  19.2 us         (0.28%)         2.42 Gbits/sec
pod "1-client" deleted
pod "1-server" deleted
```

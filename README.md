pktgen
======

pktgen source as a standalone module from RHEL8.

For some reason RHEL do not provide the binary of this module in RHEL8 series.

samples/pktgen contains all the scripts, plus some extra improvements.

All sources and credits from linux kernel.

Multidev usage features
=======================

```
source ./samples/pktgen/functions.sh
pg_ctrl reset

# add first device
PG_NO_RESET=1 PG_NO_REM_ALL=1 PG_NO_START=1 ./samples/pktgen/pktgen_sample06_numa_awared_queue_irq_affinity.sh -i ens1f0 -s 1000 -m 34:80:0d:a3:fc:c8 -t 8 -x -w 100

# add second device
PG_NO_RESET=1 PG_NO_REM_ALL=1 PG_NO_START=1 ./samples/pktgen/pktgen_sample06_numa_awared_queue_irq_affinity.sh -i ens1f1 -s 1000 -m 34:80:0d:a3:fc:c9 -t 8 -x -w 100

# run joint traffic
pg_ctrl start
```

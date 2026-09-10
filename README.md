# Rateforge

Distributed rate limiter that adapts with TCP Vegas–style delay feedback instead of static quotas.

Fixed windows and token buckets assume you already know the right limit. Rateforge treats admission control as congestion control: it watches latency against a baseline RTT, raises the limit when there is spare capacity, and backs off when queues start to form. The aim is a shared, cluster-wide limiter that stays near the throughput–latency sweet spot as load and backends change.

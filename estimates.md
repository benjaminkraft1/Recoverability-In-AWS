## Minimum RTO for a single AZ outage

| Time  | Description                                                |Time Estimation |
| ----- | ---------------------------------------------------------- |----------------|
| 00:00 | Problem happens                                            | -      |
| 00:05 | An amount of time passes before an alert triggers          | 5 min  |
| 00:06 | Automatically switch to second availability zone           | 1 min  |

**Total time ~ 10 mins**

## Minimum RTO for a single region outage

| Time  | Description                                                                                 | Time Estimation |
| ----- | ------------------------------------------------------------------------------------------- | ----------------|
| 00:00 | Problem happens                                                                             | -               |
| 00:05 | An amount of time passes before an alert triggers                                           | 5 min   |
| 00:06 | Alert triggers on-all staff                                                                 | 1 min   |
| 00:16 | On-call staff may need to get out of bed, get to a computer, log in, log onto VPN           | 10 min  |
| 00:36 | On-call staff starts diagnosing the issue                                                   | 20 min  |
| 00:51 | Root cause is discovered                                                                    | 15 min  |
| 00:56 | Remediation started                                                                         | 5 min   |
| 00:66 | Issue fixed                                                                                 | 10 min  |

**Total time: 66 mins**

## Minimum RPO for a single AZ outage

RDS has point in time recovery available which backs up every 5 minutes. Thus, if this is case then the most data that would be lost would be 5 minutes.

## Minimum RPO for a single region outage

The read replication database keeps always in snyc with the primary DB, so the read replica will have roughly the same RPO as the primary DB. -> ~ 6 min. 
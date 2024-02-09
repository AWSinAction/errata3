+++
date = "2024-02-09"
draft = false
title = "Use IMDSv2 consistently"
section = "15.1"
page = 416
+++

```bash
TOKEN=`curl -X PUT "http://169.254.169.254/[CA]latest/api/token" -H "X-aws-ec2-metadata-token-ttl-seconds: 60"`
AZ=`curl -H "X-aws-ec2-metadata-token: $TOKEN" -v http://169.254.169.254/latest/meta-data/placement/availability-zone`
```

Should be:

```bash
TOKEN=`curl -X PUT -H "X-aws-ec2-metadata-token-ttl-seconds: 60" "http://169.254.169.254/[CA]latest/api/token"`
AZ=`curl -H "X-aws-ec2-metadata-token: $TOKEN" -s -m 60 "http://169.254.169.254/latest/meta-data/placement/availability-zone"`
```

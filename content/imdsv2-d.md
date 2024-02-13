+++
date = "2024-02-09"
draft = false
title = "Use IMDSv2"
section = "13.2.4"
page = 384
+++

```bash
INSTANCE_ID="$(curl -s http://169.254.169.254/latest/meta-data/instance-id)"
```

Should be:

```bash
TOKEN=`curl -X PUT -H "X-aws-ec2-metadata-token-ttl-seconds: 21600" "http://169.254.169.254/latest/api/token"`
INSTANCE_ID=`curl -H "X-aws-ec2-metadata-token: $TOKEN" -s -m 60 "http://169.254.169.254/latest/meta-data/instance-id"`
```

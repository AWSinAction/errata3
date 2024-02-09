+++
date = "2024-02-09"
draft = false
title = "Use IMDSv2 consistently"
section = "5.3.5"
page = 150
+++

```bash
TOKEN=`curl -X PUT "http://169.254.169.254/latest/api/token" -H "X-aws-ec2-metadata-token-ttl-seconds: 21600"`
INSTANCEID=`curl -H "X-aws-ec2-metadata-token: $TOKEN" -s "http://169.254.169.254/latest/meta-data/instance-id"`
```

Should be:

```bash
TOKEN=`curl -X PUT -H "X-aws-ec2-metadata-token-ttl-seconds: 21600" "http://169.254.169.254/latest/api/token"`
INSTANCEID=`curl -H "X-aws-ec2-metadata-token: $TOKEN" -s -m 60 "http://169.254.169.254/latest/meta-data/instance-id"`
```

+++
date = "2024-02-09"
draft = false
title = "Use IMDSv2"
section = "3.8.2"
page = 96
+++

```bash
$ curl http://169.254.169.254/latest/meta-data/spot/instance-action
```

Should be:

```bash
TOKEN=`curl -X PUT -H "X-aws-ec2-metadata-token-ttl-seconds: 21600" "http://169.254.169.254/latest/api/token"`
curl -H "X-aws-ec2-metadata-token: $TOKEN" "http://169.254.169.254/latest/meta-data/spot/instance-action"
```

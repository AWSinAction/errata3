+++
date = "2025-02-26"
draft = false
title = "Prevent AMI name confusion attack"
section = "4.2.4"
page = 108
+++

```bash
$ aws ec2 describe-images --filters \
  "Name=name,Values=amzn2-ami-hvm-2.0.202*-x86_64-gp2"

$ aws ec2 describe-images --filters \
  "Name=name,Values=amzn2-ami-hvm-2.0.202*-x86_64-gp2" \
  --query "Images[0].ImageId" 

$ aws ec2 describe-images --filters \
  "Name=name,Values=amzn2-ami-hvm-2.0.202*-x86_64-gp2" \
  --query "Images[0].ImageId" --output text
```

Should be:

```bash
$ aws ec2 describe-images --owner amazon --filters \
  "Name=name,Values=amzn2-ami-hvm-2.0.202*-x86_64-gp2"

$ aws ec2 describe-images --owner amazon --filters \
  "Name=name,Values=amzn2-ami-hvm-2.0.202*-x86_64-gp2" \
  --query "Images[0].ImageId" 

$ aws ec2 describe-images --owner amazon --filters \
  "Name=name,Values=amzn2-ami-hvm-2.0.202*-x86_64-gp2" \
  --query "Images[0].ImageId" --output text
```

## Listing 4.1

```bash
AMIID="$(aws ec2 describe-images --filters \
  "Name=name,Values=amzn2-ami-hvm-2.0.202*-x86_64-gp2" \
  --query "Images[0].ImageId" --output text)"
```

Should be:

```bash
AMIID="$(aws ec2 describe-images --owner amazon --filters \
  "Name=name,Values=amzn2-ami-hvm-2.0.202*-x86_64-gp2" \
  --query "Images[0].ImageId" --output text)"
```

## Listing 4.2

```ps
$AMIID=aws ec2 describe-images --filters "Name=name,Values=amzn2-ami-hvm-2.0.202*-x86_64-gp2" --query "Images[0].ImageId" --output text
```

Should be:

```ps
$AMIID=aws ec2 describe-images --owner amazon --filters "Name=name,Values=amzn2-ami-hvm-2.0.202*-x86_64-gp2" --query "Images[0].ImageId" --output text
```

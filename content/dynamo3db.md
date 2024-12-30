+++
date = "2024-12-30"
draft = false
title = "Typo in AWS CLI command"
section = "12.8"
page = 349
+++

```
aws dynamo3db execute-statement --statement "SELECT * FROM ""todo-task\""
```

Should be:

```
aws dynamodb execute-statement --statement "SELECT * FROM ""todo-task\""
```
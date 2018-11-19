---
title: MySQL - Manual - SQL Syntax - 13.1.23 - DROP EVENT 语法
categories: 
 - MySQL
 - Manual
tags: 
 - SQL Syntax
 - DDL
 - DROP EVENT
---

MySQL `DROP EVENT` 语法

<!--more-->

```
DROP EVENT [IF EXISTS] event_name
```

This statement drops the event named event_name. The event immediately ceases being active, and is
deleted completely from the server.

If the event does not exist, the error ERROR 1517 (HY000): Unknown event 'event_name' results.
You can override this and cause the statement to generate a warning for nonexistent events instead using
IF EXISTS.

This statement requires the EVENT privilege for the schema to which the event to be dropped belongs.


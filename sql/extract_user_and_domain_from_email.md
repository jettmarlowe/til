# How to extract the user and the domain from an email address 

## In Oracle SQL

```sql
select 
  email
, substr(email, 1, instr(email, '@') - 1) as user_part
, substr(email, instr(email, '@') + 1)  as domain_part 
from email_table
```

Result:

|email|user_part|domain_part|
|---|---|---|
|test_account@gmail.com|test_account|gmail.com |

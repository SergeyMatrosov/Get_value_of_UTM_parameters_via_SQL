```sql
WITH
  UTM_Parameters AS (
  SELECT "this_is_referrer/?utm_source=google&utm_medium=cpc&utm_campaign=TEST" AS referrer)
  
SELECT
REGEXP_EXTRACT(referrer, r"utm_source=([^&]*)") AS source,
REGEXP_EXTRACT(referrer, r"utm_medium=([^&]*)") AS medium,
REGEXP_EXTRACT(referrer, r"utm_campaign=([^&]*)") AS campaign
--FOR postgresql use SUBSTRING(referrer from 'utm_PARAMETER_NAME=([^&]*)') AS smth
FROM 
UTM_Parameters
```

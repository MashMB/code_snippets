### Data Query Language

### Simple SELECT instruction
```
SELECT [table_name].[field_name] AS [custom_column_name_to_display]
FROM [table_name];
```

### Own text in SELECT instruction
```
SELECT 'test' || [rest_of_instruction];
```

### Change NULL to signification value
```
NVL([field_to_convert], [value]);
```

### SELECT without duplicates
```
SELECT DISTINCT [rest_of_instruction];
```

### Condition in SELECT instruction
```
SELECT ... FROM ... WHERE [condition];
```

### Segragate ASCENDING or DESCENDING
```
SELECT ... FROM ... WHERE ... ORDER BY [field_name] ASC_or_DESC;
```

### IN operator
```
SELECT ... FROM ... WHERE [field_name] IN clausule;
```

### BETWEEN operator
```
SELECT ... FROM ... WHERE [field_name] BETWEEN first_clausule AND second_clausule;
```

### Pattern in text
```
--- '_' - any one character ---
--- '%' - any string ---
SELECT ... FROM ... WHERE [field_name] LIKE '[pattern]';
```

### Data conversion
```
--- converting to varchar ---
TO_CHAR([text_or_date], '[pattern]')
```

```
--- converting to date ---
TO_DATE([text], '[pattern]')
```

```
--- converting to number ---
TO_NUMBER([text], '[pattern]')
```

### System functions
```
--- system date ---
SYSDATE
```

```
--- logged in user ---
USER
```

```
--- number of characters in string ---
LENGTH([text])
```

```
--- returns piece of text ---
SUBSTR([text], [start_number], [end_number])
```

```
--- replacing text ---
REPLACE([text], [searched_text], [new_text])
```

```
--- text reversing ---
REVERSE([text])
```

```
--- trimming whitespaces from both sides ---
TRIM([text])
```

```
--- trimming whitespaces from left ---
LTRIM([text])
```

```
--- trimming whitespaces from right ---
RTRIM([text])
```

```
--- returns date 'd' plus 'm' months ---
ADD_MONTHS([d], [m])
```

```
--- returns number between months ---
MONTHS_BETWEEN([first_date], [second_date])
```

```
--- returns choosen part of date ---
EXTRACT([part_of_date] FROM [date])
```

```
--- rounding number x to y places after coma ---
ROUND([x], [y])
```

### Joining one to one
```
SELECT ... FROM ... INNER JOIN [table_name] ON [field_from_first_table] = [field_from_second_table];
```

### Join including NULL
```
SELECT ... FROM ... LEFT OUTTER JOIN [table_name] ON [field_from_first_table] = [field_from_second_table];
```

```
SELECT ... FROM ... LEFT OUTTER JOIN [table_name] ON [field_from_first_table] = [field_from_second_table];
```

```
SELECT ... FROM ... RIGHT OUTTER JOIN [table_name] ON [field_from_first_table] = [field_from_second_table];
```

```
SELECT ... FROM ... FULL OUTTER JOIN [table_name] ON [field_from_first_table] = [field_from_second_table];
```

### Sum of result sets
```
[first_SELECT] UNION/UNION ALL [second_SELECT];
```

### Intersect of result sets
```
[first_SELECT] INTERSECT [second_SELECT];
```

### Except of result sets
```
[first_SELECT] EXCEPT [second_SELECT];
```

### Summary functions
```
--- number of not empty rows in column ---
COUNT([field_name])
```

```
--- number of all rows ---
COUNT(*)
```

```
--- average ---
AVG([field_name])
```

```
--- sum ---
SUM([field_name])
```

```
--- maximal value ---
MAX([field_name])
```

```
--- minimal value ---
MIN([field_name])
```

```
--- variance value ---
VARIANCE([field_name])
```

```
--- variance value ---
VAR([field_name])
```

```
--- standard deviation ---
STDEV([field_name])
```

### Grouping
```
SELECT ... FROM ... GROUP BY [field_name];
```

```
SELECT ... FROM ... GROUP BY [field_name] HAVING clausule;
```

### Subqueries
```
SELECT ... FROM ... WHERE clausule = (second_SELECT);
```

### Quantifiers
```
--- all ---
ALL([SELECT_instruction])
```

```
--- any ---
ANY([SELECT_instruction])
```

```
--- some ---
SOME([SELECT_instruction])
```
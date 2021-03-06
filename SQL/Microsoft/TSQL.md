### Transact SQL

### PRINT function (print any text)
```
PRINT 'Hello world!';
```

### Variable declaration
```
DECLARE @[variable_name] [variable_type];
```

### Variable initialization
```
SET @[variable_name] = [value];
```

### System variables
```
--- number of last error ---
@@ERROR
```

```
--- find if cursor took row (0 if took) ---
@@FETCH_STATUS
```

```
--- returns last value generated by IDENTITY, it creates id automatically: IDENTITY([first_value], [how_much_add_to_previous_value]) ---
@@IDENTITY
```

```
--- returns number of rows on which operated last instruction ---
@@ROWCOUNT
```

```
--- returns information about SQL server ---
@@VERSION
```

### Cursor (processing record by record)
```
DECLARE @[helpful_variable] [data_type];
DECLARE [cursor_name] CURSOR FOR SELECT ... ;
OPEN [cursor_name];
FETCH NEXT FROM [cursor_name] INTO @[helpful_variable];
WHILE @@FETCH_STATUS = 0
BEGIN
	PRINT @[helpful_variable];
	FETCH NEXT FROM [cursor_name]  INTO @[helpful_variable];
END;
CLOSE [cursor_name] ;
DEALLOCATE [cursor_name] ;
```

### Procedure (select, insert, update definition)
```
CREATE PROCEDURE [procedure_name] @[helpful_variable] [data_type]
AS 
BEGIN
	[SELECT or INSERT or UPDATE]
END;
EXEC [procedure_name] [input_data];
```

### Trigger (procedure triggered by event on server)
```
CREATE TRIGGER [trigger_name] ON [table_name].[field_name]
BEFORE/AFTER/FOR [object: SELECT or INSERT or UPDATE or DELETE]
AS
[Transact SQL commands];
```
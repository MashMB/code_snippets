### Procedural SQL

### Turning on messages display
```
SET SERVEROUTPUT ON;
```

### Variable declaration
```
DECLARE [variable_name] [variable_type] := [value];
```

### Printing variables
```
DBMS_OUTPUT.PUT_LINE(variable);
```

### PL/SQL block
```
DECLARE
	[variable_name] [variable_type]
BEGIN
	[instructions]
EXCEPTION
	[exceptions]
END;
```

### Condition block
```
IF [condition] THEN
	[instructions]
ELSE IF [condition] THEN
	[instructions]
ELSE
	[instructions]
END IF;
```

### Raising error
```
RAISE_APPLICATION_ERROR(-20500, '[message]');
```

### Cursor (processing record by record)
```
DECLARE CURSOR [cursor_name] IS [SELECT ... ]
BEGIN
	OPEN [cursor_name];
		LOOP
			FETCH [cursor_name] INTO [helpful_variable];
			EXIT WHEN [cursor_name]%NOTFOUND;
		END LOOP;
	CLOSE [cursor_name];
END;
```

### Procedure (select, insert, update definition)
```
CREATE OR REPLACE PROCEDURE [procedure_name] ([helpful_variable] IN or OUT or INOUT [data_type]) IS
	[variables_declaration]
BEGIN
	[instructions]
END;

EXECUTE [procedure_name] ([parameters]);
```

### Trigger (procedure triggered by event on server)
```
CREATE OR REPLACE TRIGGER [trigger_name]
BEFORE or AFTER (INSERT or DELETE or UPDATE)
ON [table_name]
(FOR EACH ROW)
[PL/SQL_block]
```
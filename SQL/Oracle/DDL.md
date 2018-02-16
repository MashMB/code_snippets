### Data Definition Language

### Creating table
```
CREATE TABLE table_name (field_name data_type NULL_or_NOT NULL);
```

### Crating index
```
CREATE UNIQUE INDEX name ON table_name (field_name);
```

### Creating primary key
```
ALTER TABLE table_name
ADD CONSTRAINT name_for_key PRIMARY KEY (field_name);
```

### Creating foreign key
```
ALTER TABLE table_name
ADD CONSTRAINT name_for_key
FOREIGN KEY (field_name)
REFERENCES table_name (field_name);
```

### Deleting table
```
DROP TABLE table_name;
```
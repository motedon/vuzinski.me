```dataview
    TABLE WITHOUT ID
    file.link AS Note, dateformat(file.mtime, "ff")
    AS Modified 
    FROM "content" 
    SORT file.mtime desc LIMIT 7
```


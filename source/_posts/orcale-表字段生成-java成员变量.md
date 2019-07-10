---
title: 表字段生成 java成员变量
date: 2019-07-10 10:08:52
tags: java
---
## orcale
```sql

select 'private ' || case
         when A.DATA_TYPE = 'NUMBER' and a.DATA_SCALE > 0 then
          'BigDecimal ' || lower(A.COLUMN_NAME) || ';   /* ' ||
          replace(COMMENTS, chr(10), chr(32)) || ' */'
         else
          decode(A.DATA_TYPE,
                 'VARCHAR2',
                 'String ',
                 'NUMBER',
                 'Integer ',
                 'DATE',
                 'Date ') || lower(A.COLUMN_NAME) || ';   /* ' ||
          replace(COMMENTS, chr(10), chr(32)) || ' */'
       end as title
  from user_tab_columns A, user_col_comments B
 where A.TABLE_NAME = 'SB_JLZC'
   AND A.TABLE_NAME = B.table_name(+)
   AND A.column_name = B.column_name(+)
 order by A.COLUMN_ID asc

```
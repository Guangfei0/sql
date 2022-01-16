# sql
This repo mainly on the notes on mysql difference from mssql

1. select only first several rows:
     select *
     from table
     limit n offset m
2. define column name, when name was internal used, quoted such as
     select rank2 as 'rank'
     from table
3. group by does not return unique columns (example table with id, email)
     The following is not right:
     select email, min(id) as id
     from table
     group by email
     
     use the following script:
     delete t1.*
     from table t1
     left join table t2 on t1.id=t2.id
     where t1.id<t2.id and t1.email=t2.email

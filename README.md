# binaryBulkInsertComparison
From question on SO http://stackoverflow.com/questions/41597046/sql-server-performance-50-columns-vs-single-binary-varbinary.


Comparing bulk inserts done as a binary field vs 50 float fields

## How to run
 
 * Run the sql script to create the tables
 * Open up the solution and make sure that it is compiling, you may need to fix the reference to the IDataReaderMock which is included in the thirdpartybinaries folder.
 * Alter the connectionstring in the GetConnectionString function to point to your database server of choice.
 * Run the application. It will exit after about 1 minute.
 
## What it did while running

* For both 50 columns and then 1 binary column:
** Continuously bulk inserted batches of 2000 rows until 30 seconds had passed.

## Results
Do not read to much into these results, the code is probably not optimized equally for both methods.

```
select count(*) from ManyColumns -- 1 677 161 Rows

select count(*) from OneBigBinaryColumn --- 5 949 024 Rows

```

## But how can there be such a big difference between the two methods?

* Good question

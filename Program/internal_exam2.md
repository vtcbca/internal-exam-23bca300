### PROGRAM NO:-8 {Create table cricketer(cid, cname, match, run) and insert 8 players records. Print player records with average.  and 
### write this data into player.csv file. Do all this task from python}.


```python
import csv
```


```python
import sqlite3 as sq
```


```python
con=sq.connect("C:/BCA/sqlite3/database/cricket.db")
```


```python
c=con.cursor()
```

### CREATE TABLE


```python
c.execute("create table if not exists cricketer(cid,cname,matches,run)")
```




    <sqlite3.Cursor at 0x22145e95740>



### INSERT RECORD


```python
c.execute("insert into cricketer values(1,'virat kohli',78,15000),(2,'rohit sharama',56,7800),(3,'kl rahul',45,5000),(4,'sikhar dhawan',55,8000),\
            (5,'suresh raina',57,7800),(6,'sacin tendulkar',89,13000),(7,'david warner',49,12000),(8,'martin guptil',60,13500)")
```




    <sqlite3.Cursor at 0x22145e95740>



### PRINT PLAYERS RECORDS WITH AVERAGE 


```python
c.execute("select * ,run/matches as average from cricketer")
rows=c.fetchall()
for row in rows:
    print(row)
```

    (1, 'virat kohli', 78, 15000, 192)
    (2, 'rohit sharama', 56, 7800, 139)
    (3, 'kl rahul', 45, 5000, 111)
    (4, 'sikhar dhawan', 55, 8000, 145)
    (5, 'suresh raina', 57, 7800, 136)
    (6, 'sacin tendulkar', 89, 13000, 146)
    (7, 'david warner', 49, 12000, 244)
    (8, 'martin guptil', 60, 13500, 225)
    

### WRITTING CRICKETERS DATA INTO PLAYER.CSV:-


```python
with open("C:/BCA/sqlite3/CSV/player.csv","w") as csv_file:
    w=csv.writer(csv_file)
    w.writerow(['cid','cname','matches','run','average'])
    for row in rows:
        w.writerow(row)
```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```

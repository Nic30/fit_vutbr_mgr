## objektove relacni databaze 26.9.2016
vznikly zejmena klvuli tomu ze aplikace potebovaly pracovat se slozitejsimi datovymi strukturami

smery:
* rozsirovani funcionality (uzivatelske datove typy)
* zcela objektovy nahled na databazi (navrat k navigacnimu programovani)
* objektove relacni mapovani (rel. databaze s mezivrstvou nebo rozsirenim, ktera ji interpretuje jako objekty)


Rel. db
* pouze kurzor na navigaci
* SQL

Obj. db
* perzistence objektu, jednoznacny OID
* OQL, ale vetsionou pouzivane primo z oo prog. jazyka

Obj-rel db
* rel. zaklad rozsiren o oo
* sql 1999 - podpora oo
* ADT pro honoty v tabulkach, OID
* vypocetni model: jednoducha nav. po tabulkach i pomoci referenci

SQL-1999
*LOB (large objects), 
* boolean (3 hodnoty)
* array, multiset (v sql 2003, neomeze pole)
* row (slozene sloupce)
* predikat similar (like s regularnim vyrazem)
* vice aktualizovatelne pohledy
* rekurzivni dotazy
* savepoint (pro castecny rollback)
* databazove triggery


Objektove rysy
* strukturovane uzivatelske DT (UDT)
> * obdoba tridty, polymorfizmus, jednoducha dedicnost...
> * pomoci CREATE TYPE ...

* typovana tabulka (tabulka pro UDT), kazdy radek ma REF a jde se na nej odkazovat
* scope pro reference
* UDT se deli na  objektove typy a kolekce

ukazky sql pro praci s UDT v prednasce 
na zkousce co je to obj-rel databaze porovnat, UDT obecne, zadna syntax sql...


* fuze slekce a nasledne spojeni stejnych sousedicich
# Logika

* dukaz = pomoci modus ponens odvodim ze zadanych axiomu formuli, kterou chci dokazat

* kazdy axiom je tautologie, dve tautologie modus ponens = tautologie => kazda tautologike, kdyz je dokazatelna

* nazvy v implikaci:  antecedent -> konsekvent

* je dokazatelna se znaci |-

* dukazy sporem

* pri dukazech T |- A , U |- A->B, TuU |-B

* veta o dedukci na sjednoduseni dukazu 

##priklady
* [[smt_29.9.2016]] 

###axiomy MP
```
A1  a->(b->a)
A2  (a->(b->c)) -> ((a->b)->(a->c))  
A3  otoceni implikace (~b->~a) -> (a->b)
```
axiom dava tvar formule, o kterych se vi, ze jsou dokazatelne

axiom je vzdy potreba pouzit na cely vyraz


pokud plati  <br />
|- a         <br /> 
|- a->b

mp. |-b

```
a   a->b 
\   /
  O
  |
  B
```  

```
axiomy, predpoklady
|     /
|    /
O   / 
\  /
  O mp
  |                               
dokazovana formule
```

pokud vetve obsahuji stejnou formuli staci prirozene dokazat jen jednou

###veta o dedukci
(a pridam do predpokladu) <br />
`p |- a->b  <=>  p,a |- b`



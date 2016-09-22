# Logika

* dukaz = pomoci modus ponens odvodim ze zadanych axiomu formuli, kterou chci dokazat

* kazdy axiom je tautologie, dve tautologie modus ponens = tautologie => kazda tautologike, kdyz je dokazatelna

* nazvy v implikaci:  antecedent -> konsekvent

* je dokazatelna se znaci |-

* dukazy sporem

* pri dukazech T |- A , U |- A->B, TuU |-B

* veta o dedukci na sjednoduseni dukazu 


##prevod na nand

(a and b) -> c

* a->b = ~(a and ~b)

* ~((a nand b) nand true) and ~c

* ((a nand b) nand true) or ~c

* ((a nand b) nand true) nand (c nand true)


##half adder

(s <-> (a xor b)) and (c <-> (a and b))

checme dokazat (s <-> (a xor b)) and (c <-> (a and b)) == 
(~a and ~ b -> ~c) and //b1
(~a and ~ b -> ~c) and //b2
   
(~a and   b ->  s) and //b3
(~a and   b -> ~c) and //b4

( a and  ~b ->  s) and //b5
( a and  ~b -> ~c) and //b6

( a and   b -> ~s) and //b7
( a and   b -> ~c)     //b8
                                                 

                                                 
// prepisu z vrchu
((a and b) -> c)     //a1
and (c-> (a and b))  //a2
and ((a and ~b)->s)  //a3
and ((~a and b)->s)  //a4
and (s-> ((a and ~b) or (~a and b))) //a5

// rozdelim na dve casti, ->, <-

jako x1 and x2 and x3 -> z
x2 -> z
nemusim uvazovat nektere casti a muzu dukaz rozdelit

x -> z1 and z2 ...
si muzu rozlozit na
x-> z1
x-> z2 ...


a4 -> b4, b6, b8  // trivialni dukazy

// z leve strany plyne b1
//chceme dokazat ze 
(c->(b and a)) -> ((~a and ~b) -> ~c)                         
// vybereme si vhodne konjunkty

// nevime co dal, ale otocime implikaci
~((~a and ~b) -> ~c) -> ~(c -> (b and a))       

// prepiseme na konjunkci, na zavorky zvlast
~(~((~a and ~b) and c)) -> ~(~(c and ~(b and a)))                                                 
// odstranim dvojite negace
~a and ~b and c -> c and ~(b and a)

// zjistil jsem ze otoceni implikace nikam nevedlo protoze jsem se dostal dal jeste na horsi formule

//pouziju vetu o dedukci

(c->(b and a)) |- ((~a and ~b)-> ~c)
c-> (b and a) |- ~(a or b) ->~c

// otoceni negace pro odstraneni negaci
c -> (b and a) |- c->(a or b)

|- (c-> (b and a)) -> (c-> (a or b))
// zjednoduseni podle a1 neni mozne, pouzili by jsme neplatnou formuli
// diky a2 budu dokazovat
|- c->((a and a) -> (a or b))
// diky a1 
|- (b and a ) -> (a or b)
	// (pokud se nam podari dokazat (b and a ) -> (a or b))  alias x
	// |- x -> (c -> x) , c-> (b and a) -> (a or b)

// pokud se nam podari dokazat ze plati a i b, (b and a ) -> a
|- ~(b -> ~a) ->~a
// a3 otocim implikaci

|- ~a -> (b -> ~a)
// tim jsem dostal a1 a vim ze je to dokazane


// ted reverzne prepisu postup

a1 : |- ~a ->(b ->~a)
a3 : |- (~a ->(b ->~a)) -> (~(b -> ~a) -> a)
mp : |- ~(b -> ~a) -> a
prepisu : |- (b and a) -> (a or b)     

a1 : |- ((b and a) -> (a or b)) -> (c-> ((b and a) -> (a or b)))         alias x-> (y ->x)

mp : |- c-> ((b and a) -> (a or b))       alias y->x
  
// x->c, y-> b an a, z->a or b
// a2 obecne x-> (y->z) -> ((x->y) -> (x->z))
a2 : (c-> (b and a)-> (a or b)) -> ((c -> (b and a)) ->(c -< (a or b)))

mp: (c-> (b and a)) -> (c->(a or b))

veta o dedukci : c->(b and a) |- c->(a or b)
// (~y -> ~x) -> (x->y), x-> ~(a or b), y-> ~c 
a3 : c->(a or b) -> ~(aor b) -> ~c

c->(b and a) |- (~a and ~b) -> ~c


|- (c->(b and a)) -> ((~a and ~b) -> ~c)





###axiomy MP
A1  a->(b->a)
A2  (a->(b->c)) -> ((a->b)->(a->c))  
A3  otoceni implikace (~b->~a) -> (a->b)

axiom dava tvar formule o kterych se vi ze jsou dokazatelne
axiom je vzdy potreba pouzit na cely vyraz


pokud plati 
|- a
|- a->b

mp. |-b


a   a->b
\   /
  O
  |
  B
  

axiomy, predpoklady
|     /
|    /
O   / 
\  /
  O mp
  |                               
dokazovana formule

pokud vetve obsahuji stejnou formuli staci dokazat jednou

###veta o dedukci
p |- a->b  <=>  p,a |- b //(a pridam do predpokladu)



##priklady

###1
a je dokazatelna
chceme dokazat ze (a or b) je dokazatelna

A1, a->(~b->a)  (subst a-> a, b-> ~b)

mp, ~b->a   (log upravy)
    b or a


###priklad na otoceni imilikace

|-(x->y)

subst b->~x, a->~y

// vim ze je platna formule protoze jsem pouzil formuli A3
|- (x->y) -> (~y -> ~x)
// log. upravim
|- (~y->~x)

###prikald 3
|-a
|-b

dokazuju a and b

// ze skript str8 pr. e drive dokazana formula, po substituci b-> ~b
a-> (b->~(a->~b)) 
//mp na a

|- b -> ~(a->~b)
// mp na b
|- ~(a->~b)
// prepis
|- (a and b)



###priklad 4
|- a->v
|-b->c

chci dokazat (a or b) -> c

//pouziju a3
~c->~a 

// veta o dedukci, leva cast se prevadi na predpoklad
~c |- ~a

|- ~c->~b
// veta o redukci
~c|- ~b

// pouziju ze a and b je dokazatelne
~c |- ~a and ~b

|-~c->(~a and ~b) // veta o dedukci
// otocim implikaci
|-~(~b and ~b) -> c
|- (a or b) -> c


###Priklad z sparnych predpokladu jde dokazat coliki
predpoklady(sporne):
|-a
|-~a

a1: |- ~a -> (~b->~a)
// zadano ~a je platne

mp: |-(~b->~a)
a3: |-(~b->~a)->(a->b)
mp: a -> b 
// predpoklad ~a
|-b // ze spornych predpokladu jsem dokazal b ktere ale vubec platit nemusi





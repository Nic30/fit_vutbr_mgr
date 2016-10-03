#MAT predikatorova logika 26.9.2016
## predikatorova logika 1. radu
(zminena arita, axiom. teorie mnozin, funkcni symboly, )

* kvantifikat, spojky, formule

term vs formule (term nelze rict jestli plati o formuli ano)
* jazyk pred. logiky viz skripta

term:
* promena je term
* funcni vyraz s operandy
* kazdy term vznikne pouzitim predchazejicih kroku

atomicka formule
* termy s rel. operatorem

formule:
* atomicka formule je formule
* log spojky + formule = formule
* kvantifikatory + formule = formule
* kazda formule vznikne z predchazejicich pravidel

vazany/volny vyskyt (v formuli)

formule ktera neobsahuje volnou promenou = vyrok (tvrzeni nezavisle na dosazovani z vnejsku, nesvazane kvantifikatorem)

semantika predikatorove logiky

definice pr. lo. 1. radu
realizace lazyka L romumine algebr. strukturu M ktera se sklada z
1 meprezdne mnoziny M (univerzum)
2 pro kazdy fn. symbol f cetnosti n je dano zobrazenim f_m : M^n-> M
3 predikatorovy symbol p cetnosti n krome rovnosti je dana relace p_M je podmnozina M^n

splnitelnost vs pravdivost


realizace M jazyka L
e ohodnoceni prom.
fi formule

fi pravdiva pri e  (v realizaci M , zapsano M|=fi[e])

pro kazde ohodnoceni e plati  M|=fi[e].....M|=fi (fi splnena v M)

pokud existuje realizace M M|=fi ... fi splnena

pro kazdou realizaci M M|=fi ..... |=fi (fi je log. platna)


Priklady log platnych fomruli 4.2:
not not A -> A
fi1: x < x
fi : not not (x < x) -> (x < x)

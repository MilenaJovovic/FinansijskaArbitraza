# FinansijskaArbitraza


U ovom radu, cilj je predvidjeti vrijednost kursa između dvije države. U kreiranju modela, pored novinskih članaka, za atribute uzimam bruto domaći proizvod i paritet kupovne moći koji predstavljaju značajne makroekonomske veličine. Dakle, pomoću navedenih veličina i već postojećih podataka o vrijednostima kursa, modelom će se predvidjeti vrijednost kursa između 6 parova država. Koriste se regresioni modeli ( konkretno: linearna regresija, grebena regresija, slučajne šume i metod potpornih vektora ) da se predvidi prosječna vrijednost kursa u narednoj godini za određeni par država.

1) Prikupljanje podataka i njihovo sređivanje


Kao što je već gore navedeno, koriste se 3 skupa podataka za ovaj projekat : mjesečne vrijednosti kursa, novinski članci i makroekonomske veličine. Države za koje su prikupljeni podaci su: Kina, Indija, Japan, Velika Britanija, Švajcarska i Kanada. 
Kako želimo da predvidimo godišnji kurs, to smo za već postojeće podatke mjesečnih vrijednosti kursa morali izračunati odgovarajuće godišnje vrijednosti kursa koje su se naknadno koristile u modelu. Godine koje su posmatrane su od 1981-2016. 
Novinski članci se nalaze u folderu Data. Novinske članke smo takođe morali srediti. 
Novinski članci su iz New York Times. Ima oko 2000 članaka po godini, a godine koje su posmatrane su 1981-2015. Novinski članci su većinski ekonomski orijentisani zato što se vodimo pretpostavkom da takvi tekstovi mogu najviše uticati na promjenu kursa.
Što se tiče bruto domaćeg proizvoda i pariteta kupovne moći, te podatke smo skinuli za 6 država koje posmatramo, sa sajta World Bank. Prije primjene modela, i ove podatke smo sredili.

Podaci i njihovo sredjivanje je u:
01 m text preprocessing, preprocessing
sredjivanje kursa da bude godisnji je u 04 m modeli
 

2) Topic modeling


Da bismo generisali atribute iz novinskih članaka, koristimo LDA koji je u nastavku detaljnije objašnjen. Pomoću njega, novinske članke ćemo pretvoriti u klastere. Idealno bi bilo da, za svaki klaster odgovara određena tema. 

02 m lda, 03 m weights

3) Modeli


Za svaku državu smo primjenili 4 već navedena modela i u isto vrijeme prošli za K = [5, 10, 20, 25, 50] – broj klastera koje smo izvlačili. 
Greška koju smo računali za modele je srednja kvadratna greška. Ispostavlja se da je optimalni broj klastera = 5, a model koji najbolje predvidja je model slučajne šume.
 


# Obligatorisk oppgave 2 i Algoritmer og Datastrukturer

Denne oppgaven er en innlevering i Algoritmer og Datastrukturer. 
Oppgaven er levert av følgende studenter:
* Paula Sielawa, s364584
* Suzane Mahmoud Hamze, s364759
* Majda Ivic, s362095
* George Alexander Saavedra, s360536

# Arbeidsfordeling
* Oppgave 1: Suzane, Paula og George
* Oppgave 2: Majda
* Oppgave 3: Suzane, Paula og George
* Oppgave 4: Majda
* Oppgave 5: George
* Oppgave 6: Majda og George
* Oppgave 7: Paula
* Oppgave 8: Suzane
* Oppgave 9: Paula
* Oppgave 10: George

# Oppgavebeskrivelse

* Oppgave 1:

Oppgave 1: Konstruktøren DobbeltLenketListe(T[] a) kastes requireNonNull-metode når tabell a er tom. 

Vi bruker forløkke etterpå for å hoppe over eventuelle nuller (null-verdier tas ikke med).

Da endelig har vi funnet verdi som ikke er null og fortsatt er mindre enn en a-array lengde, 
så setter vi første element som er også et hode på plass. 
Dersom det er flere verdier så det settes andre noder i rekkefølge. 
Her er trikset å legge nye noder bakerst så først vi har hale som er før p (p.forrige= hale). 
Før vi går ut av forløkken vil halen være siste p. Som dermed har en neste peker som peker på null. 


Metodene int antall() og boolean tom():

Den første skal returnere antallet verdier i listen (return antall) og den andre skal returnere true/false avhengig av om listen er tom eller ikke (return antall == 0).

* Oppgave 3: 

a):

finnNode() Er løst med 2 if setninger, for å avgjøre hvor indeksen er ift midten. Den første if setningen flytter seg indeks antall ganger til riktig node, mens den andre som starter fra halen beveger seg (antall-indeks) antall ganger.
Metodene oppdater() og hent() er lånt fra kompendiets programkode 3.3.3 b)


* Oppgave 5:

Løsningen her brukte kompendiets programkode 3.3.2 g) som utgangspunkt. Den ble tilpasset dobbel lenkede lister (bakoverpekere).
Pekerne var følgelig det som gav mest hodebry. Et annet sentralt element var også å skille ut tilfellene der man setter inn en node i en tom tabell, kontra en tabell med innhold.

Ytterligere detaljer er å finne i kildekodekommentarene.

* Oppgave 7:

I oppgave 7 ble vi bedt om å tømme listen på 2 måter og velge den måten som er mest effektivt.
For å registrere tid vi har brukt:

long startTime = System.nanoTime();

long stopTime = System.nanoTime();

System.out.println(stopTime-startTime);

1.måte i utgangspunktet ble tatt fra Kompendiet. Vi har registrert tidsmåling på 6333.

2.måte som går ut på å lage en løkke som inneholder fjern() metode og går inntil listen er tom.
for(int i = antall -1; i >= 0; i--) {
    fjern(i);
}
Vi har registrert tidsmåling på: 23958.

Utifra tidsmåling er det første måte som er mest effektiv og derfor kun første metode ble beholdt i klassen.

* Oppgave 8:

I oppgave 8a ble metoden next() brukt der den reurnerte "denne" veriden. Altså veriden i noden p
og samtidig flytte p til neste node eller til null hvis p var den siste. 

8b lagde instans av iterator klassen

8c lagde konstruktøren. Konstruktøren setter pekeren "denne" til den noden som hører
til den oppgitte indeksen. Konstruktøren her en nesten identisk med dobbeltLenkeListeIterator().

I 8D lages først metoden Iterator <T> iterator(int indeks). Her skjekkes det at indeksen er lovlig
ved bruk av metoden indeksKontroll(). Deretter returnerer metoden en instans av iterator klassen.

* Oppgave 9:
Vi tok utgangspunkt i kompendiets programkode 3.3.4 d). 
Vi måtte innføre en del endringer til for å fungere koden med en slik oppgaven ønsket.
"denne" er fra iteratoren og vil være noden til høyre for den som skal fjernes. Altså p fra oppgaveteksten.

Vi sjekker om de to endringsvariablene (endringer og iteratorendringer) er like. Hvis ikke kastes en
ConcurrentModificationException. På slutten av koden skal begge endringsvariablene økes med 1. 
Dermed vil de fortsatt være like etter et kall på remove. Her sjekker vi også fjernOk hvis  det  ikke  er  tillatt  
å  kalle  denne  metoden,  skal  det  kastes  en  IllegalStateException. Dersom disse hindrene oppe passeres, settes fjernOK til false.

Dersom antall er lik 1 vil den eksisterende noden (som skal fjernes) være både hode og hale samtidig, å nulles begge.
Dersom den første skal fjernes (i en liste med mer enn 1 element) så må hode oppdateres.
Hvis  en  node  inne  i  listen  skal  fjernes så itererer det til riktig plass på listen. 
Dersom det som skal fjernes ikke er halen så må pekerne i nodene på hver side oppdateres. Dersom denne er lik null, 
har "denne" blitt skjøvet ut av listen sine grenser, da vet vi at det som skal fjernes er halen.
# Obligatorisk oppgave 2 i Algoritmer og Datastrukturer

Denne oppgaven er en innlevering i Algoritmer og Datastrukturer. 
Oppgaven er levert av følgende studenter:
* Paula Sielawa s364584
* Suzane Mahmoud Hamze s364759
* Majda Ivic s362095
* George Alexander Saavedra s360536


# Arbeidsfordeling

Vi har hatt følgende arbeidsfordeling:
* Suzane, George og Paula har hatt hovedansvar for oppgave 1 og 3. 
* Majda har hatt hovedansvar for oppgave 2 og 4. 
* George har hatt hovedansvar for oppgave 5. 
* Suzane har hatt hovedansvar for oppgave 8.
* Paula har hatt hovedansvar for oppgave 7 og 9.
* George og Majda har hatt hovedansvar for oppgave 6 og 10.

# Oppgavebeskrivelse

* Oppgave 1:
Konstruktøren DobbeltLenketListe(T[] a) kastes requireNonNull-metode når tabell a er tom. Vi bruker forløkke etterpå for å
hoppe over eventuelle nuller (null-verdier tas ikke med). Da endelig har vi funnet verdi som ikke er null og fortsatt er 
mindre enn en a-array lengde så setter vi første element som er også et hode på plass. Dersom det er flere verdier så 
det settes andre noder i rekkefølge. Her er triksen å legge nye noder bakerst så først vi har hale som er før p (p.forrige=
hale). Før vi går ut av forløkken vil halen være siste p. Som dermed har en neste peker som peker på null.
Metodene int antall() og boolean tom(). Den første skal returnere antallet verdier i listen (return antall) og den andre 
skal returnere true/false avhengig av om listen er tom eller ikke (return antall == 0).

Oppgave 2:
a) Oppgaven går ut på treversere gjennom en lenket liste. Metoden toString() traverserer fra hode til hale ved hjelp av 
neste-pekere. Metoden returnerer [] hvis listen er tom, hvir listen innenholder bare en verdi returener metoden den ene 
verdien i klam parantesene, eller flere verdier i klam parantesene. Metoden omvendtString() gjør det samme som toString(),
men denne gangen traversering skjer fra hale til hode ved hjelp av forrige-pekere.

b) Oppgaven går ut på å legge inn ny node med ny verdi og returnere true hvis inleging var vellykket.
Metoden må oppfylle to hovedkravene. 
1. Hvis det er første node som settes i en tom liste skal både hode og hale sin peker (både forrige og este peker) 
peke til null.
2. I den andre tillfelle legges den nye node bakest i lista, og hale.neste skal peke nå til den nye noden
3. Antall noder økes siden vi har en ny node i lenket liste

Koden er tatt fra kompendie og er veldokkumentert i kommentarene i selve oppgaven. Koden var laget til en løsning til
enkelt lenked liste,men jeg omjorde den til dobell leket liste

* Oppgave 3:
3a:

finnNode() Er løst med 2 if setninger, for å avgjøre hvor indeksen er ift midten.
Den første if setningen flytter seg indeks antall ganger til riktig node, mens den andre som
starter fra halen beveger seg (antall-indeks) antall ganger.

Metodene oppdater() og hent() er lånt fra kompendiets programkode 3.3.3 b)

Oppgave 4:
Oppgaven går ut på å loope gjennom listen. Metoden int indeksTil(T verdi) tar imot en verdi og prøver å finne den i listen.
Looping starter fra hode til lenket liste. I loppen har vi en if settning som sammenligner oppgit verdi med node sin verdi. 
Hvis det stemmer, får vi i retur index av noden der verdien ble funnet, hvis ikke fortsetter vi videre.
Hvis verdien finnes ikke i listen vår returnerer medoden -1.

Metoden public boolean inneholder(T verdi) rett og slett returnerer true hvis verdien er funnet i listen og false hvis ikke.

Koden er også tatt fra kompendiet, og er veldig godt kommentert i selve koden

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


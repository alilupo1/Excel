ROOFSORT: Die Sortierung mit Dach

=LAMBDA(Sortierspalte;[Sortierrichtung];LET(a;SORTIEREN(Sortierspalte;;Sortierrichtung);
b;ZEILEN(a);
c;(REST(SEQUENZ(b);4)+1>2)%;
d;LAMBDA(e;s;INDEX(SORTIERENNACH(a;c);SEQUENZ(b/2;;e;s)));
VSTAPELN(d(1;1);d(b;-1))))

benannt als ROOFSORT.

=ROOFSORT({1;2;3;4;5;6;7;8;9;10;11;12;13;14}) ergibt
1;4;5;8;9;12;13;14;11;10;7;6;3;2 "Dachsort"

=ROOFSORT({1;2;3;4;5;6;7;8;9;10;11;12;13;14};-1) ergibt
14;11;10;7;6;3;2;1;4;5;8;9;12;13 "Grabensort"

Anwendung? =SPALTENUMBRUCH(ROOFSORT(A1:A14;-1);ANZAHL(A1:A14)/2) stellt bei gleichmäßig verteiltem Material jeweils 2 Elemente nebeneinander, mit annähernd gleichbleibender Summe untereinander.

Idee dazu: Sortierung aus der Mitte heraus.
http://office-fragen.de/thread-28753.html

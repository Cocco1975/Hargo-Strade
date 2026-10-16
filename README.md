# Hargo-Strade

Tessere delle strade per **Hargo**, l'app di sicurezza di quartiere in prova a Carbonia.

Qui dentro non c'è l'app: ci sono soltanto i dati stradali che l'app usa per calcolare un percorso
a piedi **sul telefono**, senza mandare da nessuna parte dove parti e dove vai.

## Dati e licenza

Dati stradali derivati da **OpenStreetMap** — © contributori di OpenStreetMap.

I dati di OpenStreetMap sono disponibili sotto la **Open Database License (ODbL) 1.0**:
<https://opendatacommons.org/licenses/odbl/1-0/>

Queste tessere sono un **database derivato** e sono distribuite sotto la **stessa licenza ODbL 1.0**.
Chi le riusa deve attribuire OpenStreetMap e ridistribuire con la stessa licenza.

Il file [`LICENZA`](LICENZA) dice anche da quale estratto vengono e che trasformazione hanno subito,
così chiunque può rifarle da capo e controllare.

Informazioni su licenza e attribuzione: <https://www.openstreetmap.org/copyright>

## Com'è fatto

```
strade/<generazione>/
    166_782.json      una tessera
    167_783.json      ...
    LICENZA
```

Una **generazione** è un estratto OSM in un certo istante, e il suo nome contiene la data
(`20261014-fa389ca7`). Una generazione pubblicata **non cambia mai**: se i dati si rifanno, nasce
una generazione nuova accanto alla vecchia. Serve perché ogni versione dell'app chiede la
generazione con cui è stata costruita, e una tessera che cambia sotto i piedi darebbe percorsi
diversi a telefoni diversi.

Il nome di una tessera sono le sue coordinate in centesimi di grado: `166_782` è la cella che
comincia a 8,30° est e 39,10° nord, larga 0,05°.

Non c'è nessun indice: quello vive dentro l'app. Qui si scarica una tessera per nome, e basta.

## Perché su un host pubblico

Perché scaricare una tessera non deve dire niente su chi la scarica. Un host statico vede un
indirizzo IP e un nome di file, come qualunque sito; non sa chi sei, non ha un account tuo e non
può incrociare le due cose. I server di Hargo, che invece sanno chi sei, queste richieste non le
vedono mai.

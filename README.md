# NormaTEI
NormaTEI è un software per l'analisi del contenuto di uno o più file XML.
NormaTEI è progettato principalmente per due utilizzi:
 - controllo dell'uniformità di codifica: quando un'edizione XML/TEI è formata da più file, NormaTEI permette di controllarli in maniera organica, permettendo di individuare facilmente errori o scelte di codifica difformi;
 - analisi della codifica: ricerche personalizzate e complesse sul corpus selezionato.
Il nome "Norma" richiama sia l'operazione per cui il software è stato sviluppato ("normalizzazione") che la più famosa opera di Vincenzo Bellini: NormaTEI è stato sviluppato infatti durante la realizzazione di Bellini Digital Correspondence, © Cnr Edizioni, 2023 ISBN: 978-88-8080-562-5 (edizione elettronica). 
[Bellini Digital Correspondence, © Cnr Edizioni, 2023 ISBN: 978-88-8080-562-5 (edizione elettronica)](http://bellinicorrespondence.cnr.it "Bellini Digital Correspondence, © Cnr Edizioni, 2023 ISBN: 978-88-8080-562-5 (edizione elettronica)")

## Ambiente
NormaTEI è stato sviluppato utilizzando 4D (https://www.4d.com/).
Tra le molteplici caratteristiche di questa piattaforma sono stati sfruttati il supporto nativo XML con la libreria Xerces di Apache Foundation e l’accesso alla struttura di un XML tramite lo standard DOM (Document Object Model).
NormaTEI è compatibile con Windows 10 – Windows 11 Windows Server 2012 R2 – Windows Server 2022 - macOS Big Sur (11) – macOS Ventura (13) (le ultime release per ogni versione).

## Installazione
Per utilizzare NormaTEI:

### Windows
  - scarica la cartella Windows (scaricando l'intero repository oppure saricando la singola cartella tramite servizi o software di downlaod);
  - estrai i file compressi per ottenere un file zip che puoi estrarre nella cartella che preferisci e poi esegui il file NormaTEI.exe.

### MacOSX 
  - vai su "Impostazioni di sistema -> Privacy e sicurezza" e controlla che sia attiva la voce "Dovunque". Nel caso in cui la voce "Dovunque" non fosse presente la si può abilitare con questo comando dato da Terminale:

```
sudo spctl --master-disable
```

  - scarica la cartella MacOSX (scaricando l'intero repository oppure saricando la singola cartella tramite servizi o software di downlaod);
  - estrai i file compressi per ottenere un file zip che puoi estrarre nella cartella che preferisci e poi esegui il file NormaTEI.app;
  - nota (1): se hai provato ad aprire  NormaTEI.app prima di andare su "Privacy e sicurezza", il sistema operativo ti potrebbe aver restituito un errore, impedendo l'apertura dell'applicazione. In questo caso cancella il file ed effettua nuovamente il download e l'estrazione;
  - nota (2): per abilitare nuovamente Gatekeeper (nel caso lo avessi disattivato) basterà dare lo stesso comando inserendo la parola enable:

```
sudo spctl --master-enable
```

## Modalità d'uso
NormaTEI offre due modalità di ricerca:
  - Standard: per ricerche semplici, consente di trovare rapidamente errori di codifica;
  - Avanzato: per l'analisi e la valutazione approfondita dei corpus.

## Utilizzo standard
Al primo avvio potrebbe compaarire una finestra per la creazione del file di dati. 
![Crea un nuovo file dati](https://github.com/pierpaolosichera/NormaTEI/blob/main/README_images/01_NewDataFile.png)
Scegli "Create" e salvalo dove vuoi, NormaTEI ricorderà il percorso utilizzato.

#### Importazione corpus
![Importazione corpus](https://github.com/pierpaolosichera/NormaTEI/blob/main/README_images/02_Open.gif)
Nella finestra di avvio cliccare su "Cambia...", per scegliere la cartella contenente i file XML, poi premi il tasto "Importa e analizza".
Se hai gia importato dei file, puoi visualizzare i risultati senza eseguire una nuova importazione col pulsante in basso "Apri i file gia caricati".

#### Ricerca
![Ricerca semplice](https://github.com/pierpaolosichera/NormaTEI/blob/main/README_images/03_SimpleSearch.gif)
Al termine dell'operazione scelta, NormaTEI mostrerà i dati, generando una lista che elenca:
  - il file dove è presente quel tag;
  - il percorso completo;
  - il tag;
  - il valore di quel tag;
  - gli attributi di quel tag;
  - i valori degli attributi;
  - il percorso univoco. 
Con "percorso univoco" si intende attribuire un identificativo univoco ad ogni percorso, aggiungendo ad ogni tag del percorso un codicenumerico del tipo "[N]". Ad esempio "/TEI[1]/text[3]/body[2]/" indica che body è il secondo figlio del tag text che è il terzo figlio del tag TEI che è il primo figlio della root.
In alto a sinistra viene mostrato il numero di risultati totale rispetto al corpus preso in esame.
I risultati mostrano:
  - una riga per ogni attributo di un tag: quindi se un tag ha tre attributi l'elenco mostra tre righe, una per ogni attributo;
  - una riga con un valore nella colonna Tag e nessun valore nella colonna Attributo se il tag non ha attributi. 
È possibile effettuare delle ricerche inserendo per ogni colonna una parte del testo da cercare nei riquadri gialli in alto.
Cliccando sul confine tra le intestazioni delle colonne è possibile ridimensionarle.
Se un tag non ha attributi viene mostrata una riga che avrà i dati sugli attributi vuota. Se un tag ha un attributo viene mostrato col suo valore. Se un tag ha più attributi viene mostrata una riga per ogni attributo.
In basso viene mostrato il numero di valori distinti per ogni colonna.

#### Conteggio
![Conteggio per attributo](https://github.com/pierpaolosichera/NormaTEI/blob/main/README_images/04_Count.gif)
Il pulsante "Conteggio" permette di passare ad una finestra riepilogativa rispetto ai dati visualizzati.
Vengono visualizzati:
  - la metrica su cui viene eseguito il conteggio (le colonne della finestra di ricerca);
  - il numero di occorrenze totali di quel fenomeno;
  - in quanti file è presente quel fenomeno almeno una volta;
  - i file in cui quel fenomeno è presente/assente (se la riga ha uno sfondo verde quelli mostrati sono i file del corpus dove quel fenomeno non è presente, se la riga ha sfondo rosso sono i file del corpus dove si trova quel fenomeno);

![Conteggio per tag](https://github.com/pierpaolosichera/NormaTEI/blob/main/README_images/05_CountAll.gif)
Il conteggio può essere effettuato per attributo o per tag. Esempio: per il tag
```xml
 
 
<ab n="ab_02" next="#LL1.10_ab_01_1v" part="I" rend="first_line_indented" type="parag" xml:id="LL1.10_ab_01_1r">


```

effettuando il conteggio sulla metrica "Tag":
  - se il conteggio viene effettuato per Attributo, il valore di ab è 5 (quanti sono gli attributi presenti in questo tag);
  - se il conteggio viene effettuato per Tag, il valore di ab è 1 (perché ab è un singolo tag).

## Utilizzo avanzato
![Ricerca avanzata](https://github.com/pierpaolosichera/NormaTEI/blob/main/README_images/06_AdvancedSearch.gif)
Cliccando in alto a destra su "Avanzato" è possibile attivare la finestra di ricerca avanzata.
Al di sopra della stringa di ricerca è possibile scegliere il criterio da applicare alla stringa di ricerca:
 - Contiene: la stringa è contenuta nel campo (senza distinzione di maiuscole e minuscole);
 - Inizia con: la stringa si trova nella parte iniziale del campo;
 - Finisce con: la stringa si trova nella parte finale del campo;
 - Esatto: il valore esatto della stringa;
 - Non contiene: la stringa nin è presente nel campo;
 - Match RegEx: la stringa di ricerca viene valutata come espressione regolare.
![Ricerca avanzata](https://github.com/pierpaolosichera/NormaTEI/blob/main/README_images/07_AdvancedSearchExample1)
Anche qui è possbile attivare la funzione di conteggio per analizzare i risultati.

#### Ricerca su sottoinsiemi del corpus
![Usa risultati](https://github.com/pierpaolosichera/NormaTEI/blob/main/README_images/08_UseResults.gif)
Cliccando sul pulsante "Usa" è possibile copiare i riultati della ricerca nel parte bassa della finiestra per un uso successivo:
 - Cosa uso:
   _ La selezione: utilizza le righe trovate
   _ I valori della colonna: prende tutti le righe del corpus che hanno quel valore in quella colonna. Il caso più classico è quello in cui ho cercato dove una certa caratteristica è presente mio corpus e vorrei fare delle ricerche successive solo su quei file: in questo caso sceglierò i valori nella colonna "File".

 - Cosa faccio:
   _ Aggiungi: i risultati vengono aggiunti ai risultati nella parte bassa dela finestra;
   _ Togli: i risultati vengono tolti dai risultati nella parte bassa dela finestra;
   _ Prendi i comuni: vengono selezionati i risultati comuni a quelli già presenti nella parte bassa della finestra;
   _ Nuova selezione: vengono utilizzati i risultati selezionati togliendo quelli eventualmente già presenti nella parte bassa della finestra.

![Riusa risultati](https://github.com/pierpaolosichera/NormaTEI/blob/main/README_images/09_SearchResults.gif)
A questo punto è possibile effettuare una nuova ricerca sull'intero corpus oppure premendo "Cerca tra i risultati" può essere effettuata una ricerca tra i dati selezionati nella parte bassa della finestra.
È inoltre possibile effetuare un conteggio sulle righe visualizzate nella parte Superiore o Inferiore della finestra.
![Conta risultati avanzati](https://github.com/pierpaolosichera/NormaTEI/blob/main/README_images/10_SearchResultsCount.gif)




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

#### Windows
  - scarica la cartella Windows (scaricando l'intero repository oppure saricando la singola cartella tramite servizi o software di downlaod);
  - estrai l'archivio compresso nella cartella che preferisci e poi esegui il file NormaTEI.exe.

#### MacOSX 
  - scarica la cartella MacOSX (scaricando l'intero repository oppure saricando la singola cartella tramite servizi o software di downlaod) ma non aprire i file compressi;
  - vai su "Impostazioni di sistema -> Privacy e sicurezza" e attiva la voce "Dovunque". Nel caso in cui la voce "Dovunque" non fosse presente la si può abilitare con questo comando dato da Terminale:

```
sudo spctl --master-disable
```
  - estrai il file che trovi compresso nella cartella che preferisci e poi esegui il file NormaTEI.app;
  - nota (1): se hai provato ad aprire  NormaTEI.app prima di andare su "Privacy e sicurezza", il sistema operativo ti potrebbe aver restituito un errore, impedendo l'apertura dell'applicazione. In questo caso cancella il file ed effettua nuovamente il download e l'estrazione;
  - nota (2): per abilitare nuovamente Gatekeeper (nel caso lo avessi disattivato) basterà dare lo stesso comando inserendo la parola enable:

```
sudo spctl --master-enable
```

## Utilizzo
Al primo avvio ti comparirà una finestra per la creazione del file di dati. 
![Crea un nuovo file dati](https://github.com/pierpaolosichera/NormaTEI/blob/main/README_images/01_NewDataFile.png)
Scegli "Create" e salvalo dove vuoi, NormaTEI ricorderà il percorso utilizzato.


#### Importazione corpus
Nella finestra di avvio cliccare su "Cambia...", per scegliere la cartella contenente i file XML, poi premi il tasto "Importa e analizza".
Se hai gia importato dei file, puoi visualizzare i risultati senza eseguire una nuova importazione col pulsante in basso "Apri i file gia caricati".

#### Ricerca
Al termine dell'operazione scelta, NormaTEI mostrerà i dati, generando una lista che elenca:
  - il file dove è presente quel tag;
  - il percorso completo;
  - il tag;
  - il valore di quel tag;
  - gli attributi di quel tag;
  - i valori degli attributi;
  - il percorso univoco. 
  Con "percorso univoco" intendiamo l'attribuzione di un identificativo unico ad ogni percorso, aggiungendo ad ogni tag del percorso un codice del tipo "[N]". Ad esempio "/TEI[1]/text[3]/body[2]/" indica che body è il secondo figlio del tag text che è il terzo figlio del tag TEI che è il primo figlio della root.
In alto a sinistra viene mostrato il numero di risultati totale rispetto al corpus preso in esame. 
È possibile effettuare delle ricerche inserendo per ogni colonna una parte del testo da cercare nei riquadri gialli in alto.
Se un tag non ha attributi viene mostrata una riga che avrà i dati sugli attributi vuota. Se un tag ha un attributo viene mostrato col suo valore. Se un tag ha più attributi viene mostrata una riga per ogni attributo.
In basso viene mostrato il numero di valori distinti per ogni colonna.

#### Conteggio
Il pulsante "Conteggio" permette di passare ad una finestra riepilogativa rispetto ai dati visualizzati.
Vengono visualizzati:
  - la metrica su cui viene eseguito il conteggio (le colonne della finestra di ricerca);
  - il numero di occorrenze totali di quel fenomeno;
  - in quanti file è presente quel fenomeno almeno una volta;
  - i file in cui quel fenomeno è presente/assente (se la riga ha uno sfondo verde quelli mostrati sono i file del corpus dove quel fenomeno non è presente, se la riga ha sfondo rosso sono i file del corpus dove si trova quel fenomeno);
Il conteggio può essere effettuato per attributo o per tag. Esempio: per il tag
```xml


<ab n="ab_02" next="#LL1.10_ab_01_1v" part="I" rend="first_line_indented" type="parag" xml:id="LL1.10_ab_01_1r">


```

effettuando il conteggio sulla metrica "Tag":
  - se il conteggio viene effettuato per Attributo, il valore di ab è 5 (quanti sono gli attributi presenti in questo tag);
  - se il conteggio viene effettuato per Tab, il valore di ab è 1 (perché ab è un singolo tag).



